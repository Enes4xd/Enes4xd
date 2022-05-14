#!/bin/bash

### RTKBASE KURULUM Scripti ###
-aDetected_gnss bildir

man_help(){
    Eko '################################'
    echo 'RTKBASE KURULUM YARDIM'
    Eko '################################'
    echo 'Web ön ucu ile basit bir gnss baz istasyonu kurmak için Bash betikleri.'
    Eko ''
    Eko ''
    Eko ''
    echo '* Kurulumdan önce gnss alıcınızı raspberry pi/orange pi/.... usb veya uart ile bağlayın.'
    echo '* Kurulum komut dosyasını sudo ile çalıştırma'
    Eko ''
    yankı ' sudo ./install.sh'
    Eko ''
    echo 'Seçenekler:'
    yankı '--hepsi'
    echo ' Tüm bağımlılıkları yükle, Rtklib, Rtkbase'in son sürümü, hizmetler,'
    echo ' crontab işleri, GNSS alıcınızı tespit edin ve yapılandırın.'
    Eko ''
    echo ' --bağımlılıklar'
    echo ' git build-essential python3-pip gibi tüm bağımlılıkları kurun ...'
    Eko ''
    yankı ' --rtklib'
    echo ' RTKlib 2.4.3'ü github'dan alın ve derleyin.'
    yankı ' https://github.com/tomojitakasu/RTKLIB/tree/rtklib_2.4.3'
    Eko ''
    yankı ' --rtkbase-release'
    echo ' RTKBASE'in son sürümünü alın:'
    yankı ' https://github.com/Stefal/rtkbase/releases'
    Eko ''
    yankı ' --rtkbase-repo'
    echo ' RTKBASE'i github'dan klonla:'
    yankı ' https://github.com/Stefal/rtkbase/tree/web_gui'
    Eko ''
    echo ' --birim dosyaları'
    echo ' Hizmetleri dağıtın.'
    Eko ''
    yankı ' --gpsd-chrony'
    echo 'Tarih ve saati ayarlamak için gpsd ve chrony'yi kurun'
    echo ' gnss alıcısından.'
    Eko ''
    yankı ' --tespit-usb-gnss'
    echo ' GNSS alıcınızı tespit edin.'
    Eko ''
    yankı ' --configure-gnss'
    echo ' GNSS alıcınızı yapılandırın.'
    Eko ''
    echo ' --start-services'
    echo ' Hizmetleri başlat (rtkbase_web, str2str_tcp, gpsd, chrony)'
    0 çıkışı
}

install_dependency() {
    Eko '################################'
    echo 'BAĞIMLILIKLARI YÜKLEME'
    Eko '################################'
      apt-get güncellemesi
      apt-get install -y git build-temel pps-tools python3-pip python3-dev python3-setuptools python3-tekerlek libsystemd-dev bc dos2unix socat zip unzip
}

install_gpsd_chrony() {
    Eko '################################'
    echo 'GPD + CHRONY KULLANIMI İÇİN YAPILANDIRMA'
    Eko '################################'
      apt-get install chrony -y
      #systemd-timesyncd'yi devre dışı bırakma ve maskeleme
      systemctl systemd-timesyncd'yi durdur
      systemctl systemd-timesyncd'yi devre dışı bırak
      systemctl maskesi systemd-timesyncd
      #Kronya kaynağı olarak GPS ekleme
      grep -q 'GPS'ye izin vermek için daha büyük bir gecikme ayarlayın' /etc/chrony/chrony.conf || echo '# GPS kaynağının diğer kaynaklarla çakışmasına izin vermek ve yanlış etiket durumundan kaçınmak için daha büyük bir gecikme ayarlayın
' >> /etc/chrony/chrony.conf
      grep -qxF 'refclock SHM 0 refid GNSS hassas 1e-1 ofset 0 gecikme 0.2' /etc/chrony/chrony.conf || echo 'refclock SHM 0 refid GNSS hassas 1e-1 offset 0 gecikme 0,2' >> /etc/chrony/chrony.conf
      #Krony için isteğe bağlı bir kaynak olarak PPS ekleme
      grep -q 'refclock PPS /dev/pps0 refid PPS kilidi GNSS' /etc/chrony/chrony.conf || echo '#refclock PPS /dev/pps0 refid PPS kilidi GNSS' >> /etc/chrony/chrony.conf

      #Chrony.service'i özel bağımlılıkla geçersiz kılma
      cp /lib/systemd/system/chrony.service /etc/systemd/system/chrony.service
      sed -is/^After=.*/After=gpsd.service/ /etc/systemd/system/chrony.service

      #Gerekirse, F9P'yi destekleyen bir gpsd sürümü yüklemek için backports deposu ekleme
      lsb_release -c ise | grep -qE 'biyonik|buster'
      o zamanlar
        Eğer ! uygun önbellek politikası | grep -qE 'buster-backports.* armhf'
        o zamanlar
          #Buster-backports ekleme
          echo 'deb http://httpredir.debian.org/debian buster-backports ana katkı' > /etc/apt/sources.list.d/backports.list
          apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 648ACFD622F3D138
          apt-get güncellemesi
        fi
        apt-get -t buster-backports gpsd -y kurulumu
      başka
        #Sürümün buster'dan daha yeni olduğunu ve gpsd 3.20 veya >
        apt-get install gpsd -y
      fi
      #hotplug'ı devre dışı bırak
      sed -i 's/^USBAUTO=.*/USBAUTO="yanlış"/' /etc/default/gpsd
      #gpsd için doğru girişi ayarlama
      sed -i 's/^DEVICES=.*/DEVICES="tcp:\/\/127.0.0.1:5015"/' /etc/default/gpsd
      #pps kullanımı için örnek ekleme
      grep -qi 'DEVICES="tcp:/120.0.0.1:5015 /dev/pps0' /etc/default/gpsd || sed -i '/^DEVICES=.*/a #DEVICES="tcp:\/\/ 127.0.0.1:5015 \/dev\/pps0"' /etc/default/gpsd
      #gpsd her zaman salt okunur modda çalışmalıdır
      sed -i 's/^GPSD_OPTIONS=.*/GPSD_OPTIONS="-n -b"/' /etc/default/gpsd
      #Özel bağımlılıkla gpsd.service'i geçersiz kılma
      cp /lib/systemd/system/gpsd.service /etc/systemd/system/gpsd.service
      sed -i 's/^After=.*/After=str2str_tcp.service/' /etc/systemd/system/gpsd.service
      sed -i '/^# chrony/d' ile gerekli /etc/systemd/system/gpsd.service
      #Yeniden başlatma koşulu ekle
      grep -qi '^Yeniden Başlat=' /etc/systemd/system/gpsd.service || sed -i '/^ExecStart=.*/a Yeniden Başlat=her zaman' /etc/systemd/system/gpsd.service
      grep -qi '^RestartSec=' /etc/systemd/system/gpsd.service || sed -i '/^Restart=always.*/a RestartSec=30' /etc/systemd/system/gpsd.service
      #str2str_tcp çalışmıyorsa gpsd'yi başlatmamak için ExecStartPre koşulu ekleyin. https://github.com/systemd/systemd/issues/1312 adresine bakın.
      grep -qi '^ExecStartPre=' /etc/systemd/system/gpsd.service || sed -i '/^ExecStart=.*/i ExecStartPre=systemctl etkin str2str_tcp.service' /etc/systemd/system/gpsd.service

      #systemd hizmetlerini yeniden yükle ve chrony ve gpsd'yi etkinleştir
      systemctl arka plan programı yeniden yükleme
      systemctl gpsd'yi etkinleştir
      systemctl chrony'yi etkinleştir
      #Enable chrony başarısız olabilir ama çalışıyor, bu yüzden komut dosyasını bozmamak için 0 döndürelim.
      0 döndür
}

install_rtklib() {
    Eko '################################'
    echo 'RTKLIB KURULUYOR'
    Eko '################################'
      # str2str zaten var mı?
      Eğer [ ! -f /usr/local/bin/str2str ]
      o zamanlar
        #Rtklib 2.4.3 b34 sürümünü edinin
        sudo -u "$(logname)" wget -qO - https://github.com/tomojitakasu/RTKLIB/archive/v2.4.3-b34.tar.gz | katran -xvz
        #Rtklib uygulamasını yükle
        #TODO makefile'de doğru CTARGET eklensin mi?
        --directory=RTKLIB-2.4.3-b34/app/consapp/str2str/gcc yap
        --directory=RTKLIB-2.4.3-b34/app/consapp/str2str/gcc kurulumu yap
        --directory=RTKLIB-2.4.3-b34/app/consapp/rtkrcv/gcc yap
        --directory=RTKLIB-2.4.3-b34/app/consapp/rtkrcv/gcc kurulumu yap
        --directory=RTKLIB-2.4.3-b34/app/consapp/convbin/gcc yap
        --directory=RTKLIB-2.4.3-b34/app/consapp/convbin/gcc kurulumu yap
        #RTKLIB siliniyor
        rm -rf RTKLIB-2.4.3-b34/
      başka
        echo 'str2str zaten var'
      fi
}

rtkbase_repo(){
    #rtkbase deposunu al
    eğer [[ -n "${1}" ]]; o zamanlar
      sudo -u "$(logname)" git clone --branch "${1}" --single-branch https://github.com/stefal/rtkbase.git
    başka
      sudo -u "$(logname)" git klonu https://github.com/stefal/rtkbase.git
    fi
    sudo -u "$(logname)" rtkbase/settings.conf'a dokunun
    add_rtkbase_path_to_environment

}

rtkbase_release(){
    #rtkbase'in son sürümünü edinin
    sudo -u "$(logname)" wget https://github.com/stefal/rtkbase/releases/latest/download/rtkbase.tar.gz -O rtkbase.tar.gz
    sudo -u "$(logname)" tar -xvf rtkbase.tar.gz
    sudo -u "$(logname)" rtkbase/settings.conf'a dokunun
    add_rtkbase_path_to_environment

}

install_rtkbase_from_repo() {
    Eko '################################'
    echo 'REPO'DAN RTKBASE KURULUM'
    Eko '################################'
      eğer [ -d "${rtkbase_path}" ]
      o zamanlar
        eğer [ -d "${rtkbase_path}"/.git ]
        o zamanlar
          echo "RtkBase deposu: EVET, git çekme"
          git -C "${rtkbase_path}" çekme
        başka
          echo "RtkBase deposu: HAYIR, rm sürümü ve git klon rtkbase"
          rm -r "${rtkbase_path}"
          rtkbase_repo "${1}"
        fi
      başka
        echo "RtkBase deposu: HAYIR, git klon rtkbase"
        rtkbase_repo "${1}"
      fi
}

install_rtkbase_from_release() {
    Eko '################################'
    echo 'RTKBASE'İ YAYINDAN YÜKLENİYOR'
    Eko '################################'
      eğer [ -d "${rtkbase_path}" ]
      o zamanlar
        eğer [ -d "${rtkbase_path}"/.git ]
        o zamanlar
          echo "RtkBase sürümü: HAYIR, rm repo & son sürümü indir"
          rm -r "${rtkbase_path}"
          rtkbase_release
        başka
          echo "RtkBase sürümü: EVET, rm & son sürümü dağıt"
          rtkbase_release
        fi
      başka
        echo "RtkBase sürümü: HAYIR, son sürümü indir ve dağıt"
        rtkbase_release
      fi
}

add_rtkbase_path_to_environment(){
    Eko '################################'
    echo 'ÇEVREYE RTKBASE YOLU EKLEME'
    Eko '################################'
    eğer [ -d rtkbase ]
      o zamanlar
        if grep -q '^rtkbase_path=' /etc/environment
          o zamanlar
            #Yolu ayırıcı olarak @ kullanarak değiştirin çünkü $(pwd) çıktısında / var
            sed -i "s@^rtkbase_path=.*@rtkbase_path=$(pwd)\/rtkbase@" /etc/environment
          başka
            #Yolu ekle
            echo "rtkbase_path=$(pwd)/rtkbase" >> /etc/environment
        fi
    fi
    rtkbase_path=$(pwd)/rtkbase
    rtkbase_path'i dışa aktar
}

rtkbase_requirements(){
    Eko '################################'
    echo 'RTKBASE GEREKSİNİMLERİNİN YÜKLENMESİ'
    Eko '################################'
      #web sunucusunu root olarak çalıştırmamız gerektiğinden, gereksinimleri ile birlikte yüklememiz gerekiyor.
      #aynı kullanıcı
      # Bu arada armv7 platformu için pystemd dev Wheel kurulumu yapıyoruz.
      platform=$(isim -m)
      if [[ $platform =~ 'aarch64' ]] || [[ $platformu =~ 'x86_64' ]]
      o zamanlar
        # Piwheels.org'da önceden oluşturulmuş bir tekerlek olmadığından aarch64 için daha fazla bağımlılık gerekir
        apt-get kurulumu -y libssl-dev libffi-dev
      fi
      python3 -m pip kurulumu --upgrade pip kurulum araçları tekerleği --extra-index-url https://www.piwheels.org/simple
      python3 -m pip kurulumu -r "${rtkbase_path}"/web_app/requirements.txt --extra-index-url https://www.piwheels.org/simple
      #web sunucusunu root olmadan açabileceğimiz zaman, kullanacağız
      #sudo -u $(logname) python3 -m pip kurulumu -r gereksinimleri.txt --kullanıcı.
}

install_unit_files() {
    Eko '################################'
    echo 'BİRİM DOSYALARI EKLEME'
    Eko '################################'
      eğer [ -d "${rtkbase_path}" ]
      o zamanlar
        #Birim dosyalarını yükle
        "${rtkbase_path}"/copy_unit.sh
        systemctl rtkbase_web.service'i etkinleştir
        systemctl rtkbase_archive.timer'ı etkinleştir
        systemctl arka plan programı yeniden yükleme
        #Kullanıcıya çevirme grubu ekle
        usermod -a -G araması "$(logname)"
      başka
        echo 'RtkBase kurulu değil, --rtkbase-release seçeneğini kullanın'
      fi
}

algılama_usb_gnss() {
    Eko '################################'
    echo 'GNSS ALICI TESPİTİ'
    Eko '################################'
      #Bu işlev, (USB) algılanan gnss alıcı bilgilerini algılanan_gnss içine yerleştirir.
      #Birden fazla alıcı varsa, değişkende yalnızca sonuncusu bulunacaktır.
      $(find /sys/bus/usb/devices/usb*/ -name dev) içindeki sysdevpath için; yapmak
          ID_SERIAL=''
          syspath="${sysdevpath%/dev}"
          devname="$(udevadm info -q name -p "${syspath}")"
          if [[ "$devname" == "bus/"* ]]; sonra devam et; fi
          eval "$(udevadm info -q özelliği --export -p "${syspath}")"
          if [[ -z "$ID_SERIAL" ]]; sonra devam et; fi
          if [[ "$ID_SERIAL" =~ (u-blox|skytraq) ]]
          o zamanlar
            algılanan_gnss[0]=$devname
            algılanan_gnss[1]=$ID_SERIAL
            echo '/dev/'"${detected_gnss[0]}" ' - ' "${detected_gnss[1]}"
          fi
      tamamlamak
      if [[ ${#detected_gnss[*]} -ne 2 ]]; o zamanlar
          satıcı_and_product_ids=$(lsusb | grep -i "u-blox" | grep -Eo "[0-9A-Za-z]+:[0-9A-Za-z]+")
          if [[ -z "$vendor_and_product_ids" ]]; sonra dön; fi
          devname=$(get_device_path "$vendor_and_product_ids")
          algılanan_gnss[0]=$devname
          algılanan_gnss[1]='u-blox'
          echo '/dev/'${detected_gnss[0]} ' - ' ${detected_gnss[1]}
      fi
}

get_device_path() {
    id_Vendor=${1%:*}
    id_Product=${1#*:}
    $(find /sys/devices/ -name idVendor | rev | cut -d/ -f 2- | rev); içindeki yol için; yapmak
        if grep -q "$id_Vendor" "$path"/idVendor; o zamanlar
            if grep -q "$id_Product" "$path"/idProduct; o zamanlar
                bul "$path" -name 'cihaz' | devir | kes -d / -f 2 | devir
            fi
        fi
    tamamlamak
}


configure_gnss(){
    Eko '################################'
    echo 'GNSS ALICININ YAPILANDIRILMASI'
    Eko '################################'
      eğer [ -d "${rtkbase_path}" ]
      o zamanlar
        eğer [[ ${#detected_gnss[*]} -eq 2 ]]
        o zamanlar
          echo 'GNSS ALICI ALGILANDI: /dev/'${detected_gnss[0]} ' - ' ${detected_gnss[1]}
          if [[ ${detected_gnss[1]} =~ 'u-blox' ]]
          o zamanlar
            gnss_format='ubx'
          fi
          if [[ -f "${rtkbase_path}/settings.conf" ]] && grep -E "^com_port=.*" "${rtkbase_path}"/settings.conf # settings.conf olup olmadığını kontrol edin
          o zamanlar
            # settings.conf içindeki com bağlantı noktası değerini değiştirin
            sudo -u "$(logname)" sed -is/^com_port=.*/com_port=\'${detected_gnss[0]}\'/ "${rtkbase_path}"/settings.conf
            #add seçeneği -TADJ=1 rtcm/ntrip/seri çıktılarda
            sudo -u "$(logname)" sed -is/^ntrip_receiver_options=.*/ntrip_receiver_options=\'-TADJ=1\'/ ${rtkbase_path}/settings.conf
            sudo -u "$(logname)" sed -is/^local_ntripc_receiver_options=.*/local_ntripc_receiver_options=\'-TADJ=1\'/ ${rtkbase_path}/settings.conf
            sudo -u "$(logname)" sed -is/^rtcm_receiver_options=.*/rtcm_receiver_options=\'-TADJ=1\'/ ${rtkbase_path}/settings.conf
            sudo -u "$(logname)" sed -is/^rtcm_serial_receiver_options=.*/rtcm_serial_receiver_options=\'-TADJ=1\'/ ${rtkbase_path}/settings.conf

          başka
            #create settings.conf com_port ayarı ve str2str_tcp'yi başlatmak için gereken ayarlarla
            #as web sunucusu settings.conf.default ve settings.conf birleştirmeden önce başlayabilir
            sudo -u "$(logname)" printf "[main]\ncom_port='"${detected_gnss[0]}"'\ncom_port_settings='115200:8:n:1'\nreceiver_format='"${gnss_format}" '\ntcp_port='5015'\n" > "${rtkbase_path}"/settings.conf
            #add seçeneği -TADJ=1 rtcm/ntrip/seri çıktılarda
            sudo -u "$(logname)" printf "[ntrip]\nntrip_receiver_options='-TADJ=1'\n[local_ntrip]\nlocal_ntripc_receiver_options='-TADJ=1'\n[rtcm_svr]\nrtcm_receiver_options='-TADJ=1 '\n[rtcm_serial]\nrtcm_serial_receiver_options='-TADJ=1'\n" >> "${rtkbase_path}"/settings.conf

          fi
        başka
          echo 'GNSS ALICI ALGILANMADI, YAPILANDIRAMAZ'\''BUNU YAPAMAZ!'
        fi
        #alıcı bir U-Blox ise, set_zed-f9p.sh'yi başlatın. Bu komut dosyası F9P'yi sıfırlayacak ve rtkbase için düzeltici ayarlarla yapılandıracaktır.
        if [[ ${detected_gnss[1]} =~ 'u-blox' ]]
        o zamanlar
          "${rtkbase_path}"/tools/set_zed-f9p.sh /dev/${detected_gnss[0]} 115200 "${rtkbase_path}"/receiver_cfg/U-Blox_ZED-F9P_rtkbase.cfg
        fi
      başka
        echo 'RtkBase kurulu değil, --rtkbase-release seçeneğini kullanın'
      fi
}

start_services() {
  Eko '################################'
  echo 'HİZMETLERİ BAŞLATMA'
  Eko '################################'
  systemctl arka plan programı yeniden yükleme
  systemctl rtkbase_web.service'i başlat
  systemctl str2str_tcp.service'i başlat
  systemctl gpsd.service'i yeniden başlat
  systemctl chrony.service'i yeniden başlat
  systemctl rtkbase_archive.timer'ı başlat
  Eko '################################'
  echo 'KURULUM SONU'
  echo 'Tarayıcınızı http://'"$(hostname -I)" olarak açabilirsiniz.
  #Kullanıcı zaten arama grubunda değilse, yeniden başlatma
  /dev/tty*'ye erişebilmek için #zorunlu
  gruplar "$(logname)" | grep -q "çevirme" || echo "Ama önce lütfen YENİDEN BAŞLATIN!!!"
  Eko '################################'
  
}
ana() {
  #görüntüleme parametreleri
  echo 'Kurulum seçenekleri:' "$@"
  dizi=("$@")
  # hiçbir parametre yardım göstermiyorsa
  if [ -z "$dizi" ] ; sonra man_help ;fi
  # rtkbase kuruluysa ancak işletim sistemi yeniden başlatılmamışsa, sistem genelinde
  # rtkbase_path değişkeni geçerli kabukta ayarlanmadı. kaynak yapmalıyız
  # /etc/environment'tan veya varsayılan "rtkbase" değerine ayarlayın:
  eğer [[ -z ${rtkbase_path} ]]
  o zamanlar
    if grep -q '^rtkbase_path=' /etc/environment
    o zamanlar
      kaynak /etc/ortam
    başka
      dışa aktar rtkbase_path='rtkbase'
    fi
  fi
  # günlük adının boş bir değer döndürüp döndürmediğini kontrol edin
  if [[ -z $(logname) ]]
  o zamanlar
    echo 'logname komutu boş bir değer döndürür. Lütfen yeniden başlatın ve yeniden deneyin.'
    çıkış 1
  fi
  # yeterli alan olup olmadığını kontrol edin
  if [[ $(df -kP ~/ | grep -v '^Filesystem' | awk '{ print $4 }') -lt 300000 ]]
  o zamanlar
    echo 'Kullanılabilir alan 300MB'den az.'
    echo 'Çıkış...'
    çıkış 1
  fi
  # tüm seçenekleri çalıştır
  "${dizi[@]}" içindeki i için
  yapmak
    if [ "$1" == "--help" ] ; sonra man_help ;fi
    if [ "$i" == "--bağımlılıklar" ] ; sonra install_dependencies ;fi
    if [ "$i" == "--rtklib" ] ; sonra install_rtklib ;fi
    if [ "$i" == "--rtkbase-release" ]; sonra install_rtkbase_from_release && \
					     rtkbase_requirements ;fi
    if [ "$i" == "--rtkbase-repo" ] ; sonra install_rtkbase_from_repo && \
					     rtkbase_requirements ;fi
    if [ "$i" == "--birim-dosyaları" ] ; sonra install_unit_files ;fi
    if [ "$i" == "--gpsd-chrony" ] ; sonra install_gpsd_chrony ;fi
    if [ "$i" == "--detect-usb-gnss" ]; sonra algılama_usb_gnss ;fi
    if [ "$i" == "--configure-gnss" ] ; sonra configure_gnss ;fi
    if [ "$i" == "--start-services" ] ; sonra start_services ;fi
    if [ "$i" == "--alldev" ] ; sonra install_dependencies && \
                                      	     install_rtklib && \
                                      	     install_rtkbase_from_repo dev && \
                                      	     rtkbase_requirements && \
                                      	     install_unit_files && \
                                      	     install_gpsd_chrony && \
                                      	     algılama_usb_gnss && \
                                      	     configure_gnss && \
                                      	     start_services ;fi
    if [ "$i" == "--all" ] ; sonra install_dependencies && \
                                      	     install_rtklib && \
                                      	     install_rtkbase_from_release && \
                                      	     rtkbase_requirements && \
                                      	     install_unit_files && \
                                      	     install_gpsd_chrony && \
                                      	     algılama_usb_gnss && \
                                      	     configure_gnss && \
                                      	     start_services ;fi
  tamamlamak
}

ana "$@"
0 çıkışı
