### Hi there 👋

<!--
**Enes4xd/Enes4xd** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
git clone https://github.com/Enes4xd/Enes4xd.git
git clone https://github.com/Enes4xd/Enes4xd.git
# **Glassdoor Salary exploration for financial analyst positions in the UK**

## Contributing  Members

#### Team Leads (Contacts) : [Samuel Lawrence]: http://samuel-lawrence.co.uk/

Webscraper adapted from https://towardsdatascience.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905

Inspiration for the project was based on Ken Jee's youtube series 'data science project from scratch'
Major changes include:
* Unique model building approach based on sklearn ensemble module
* The model was deployed to production via streamlit on heroku url: https://glassdoor-fin-analyst.herokuapp.com/
* Updated webcrawler was in need of overall due to glassdoor's updated website 
* Unique field objective

#### -- Project Status: [Complete]
#### Project phases:
- [x] Adapt web scraper for data for model
- [x] Clean data for analysis
- [x] Analyze data
- [x] Submit findings
- [x] Scale and Build Machine Learning Model
- [x] Host product on heroku

## Project Intro
The objective of this project is to further understand what it takes to be a financial analyst in London. This exercise will serve as a gateway to those seeking to become analyst themselves as well as create an entry point adapting a machine learning model in predicting what role may be expected in relation to the different variables. 

### Methods Used
* Inferential Statistics
* Machine Learning
* Data Visualization
* Predictive Modeling

### Technologies
* Python
* Pandas
* Numpy
* Matplotlib
* Nltk
* Wordcloud 
* Seaborn 
* Sklean
* Selenium
* Sklearn

## Project Description
As we move closer to the full cycle of graduates moving into the work force, the question has been posed is what does it take/what is it like to be a financial analyst? Some questions we plan on answering include:

- What kind of salary should be expected?
- What positions are the most popular?
- Types of companies Hiring?
- What industries are the most popular?
- Similarities between different roles?
- Other questions we might want answered as we explore the data some more?

    ### things to note:

* The data was gathered from Glassdoor job postings on 6/7/2020 via web scraper with the use of the Selenium Python library. As such, COVID-19  has remained a constant factor in our lives and should be taken into consideration.
* -1 represents data that wasn't specified in the job posting
* The sample size for this data set was 1,000 entries.
* We ran the web scraper multiple times to get a wider pool of data due to the number of missing data

## Key findings
- Some of the most common words mentioned in the analysis include: 'Problem Solving','Bachelor Degree','team' and 'attention to detail'
- Average salary came out to around 30K depending on the seniority level
- Most big corporations are doing the hiring at the moment

## Use Case
- With more data and better feature selection, users could calculate their exact salary 
# Python Mini Projeler

> Dokumantasyon linki: [https://ozcanyarimdunya.github.io/python_mini_projeler](https://ozcanyarimdunya.github.io/python_mini_projeler)
> 
> Dokumantasyon gelistirme asamasindadir, her turlu yardimlariniz kabul edilir 😊😁❤️

Boş zamanlarımda hobi olarak eğitim serisi tarzında python da yazdığım mini mini projeler bunlar :)

Bütün proje dosyalarına gerekli açıklamaları elimden geldigince yazdım.

Çok az programlama bilgisi olan biri için başlangıç/orta/ileri seviyelerde yararlı olabileceğini düşündüğüm uygulamaları yazdım.

**NOT** 
> Sisteminizde Python3 kurulu olmasi lazim
> 
> Kodları PyCharm Editorünü kullanarak yazdım. 
> 
> Kodları Windowsta hiç denemedim ne sonuçlar vereceğini bilmiyorum, bi hata varsa pull request acin
----

### Kurulum

Oncelikle bir terminal acip repoyu indirin

```bash
git clone https://github.com/ozcanyarimdunya/python_mini_projeler.git python3_projeler
cd python3_projeler/
```

Pesinden isterleri kurunuz

```bash
pip install --user poetry
poetry install
```
[![Package](https://github.com/adw0rd/instagrapi/actions/workflows/python-package.yml/badge.svg?branch=master)](https://github.com/adw0rd/instagrapi/actions/workflows/python-package.yml)
![PyPI](https://img.shields.io/pypi/v/instagrapi)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/instagrapi)
![Checked with mypy](https://img.shields.io/badge/mypy-checked-blue)

[![Downloads](https://pepy.tech/badge/instagrapi)](https://pepy.tech/project/instagrapi)
[![Downloads](https://pepy.tech/badge/instagrapi/month)](https://pepy.tech/project/instagrapi)
[![Downloads](https://pepy.tech/badge/instagrapi/week)](https://pepy.tech/project/instagrapi)

[![Donate](https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png)](https://www.buymeacoffee.com/adw0rd)

## If you are tired of being blocked when receiving data from Instagram, I recommend using our service - [Lamadava SaaS](https://lamadava.com) and [Datalama SaaS](https://datalama.io/)

Features:

* Anonymous getting of user, posts, stories, highlights, followers and following users
* Anonymous getting an email and phone number, if the user specified them in his business profile
* Anonymous getting of post, story, album, Reels, IGTV data and the ability to download content
* Anonymous getting of hashtag and location data, as well as a list of posts for them
* Anonymous getting of all comments on a post and a list of users who liked it
* Management of [proxy servers](https://soax.com/?r=sEysufQI), mobile devices, solving captcha and challenge resolver
* Login by username and password, sessionid and support 2FA
* Managing messages and threads for Direct and attach files
* Download and upload a Photo, Video, IGTV, Reels, Albums and Stories
* Work with Users, Posts, Comments, Insights, Collections, Location and Hashtag
* Insights by account, posts and stories
* Like, following, commenting, editing account (Bio) and much more else

# instagrapi - Unofficial Instagram API for Python

Fast and effective Instagram Private API wrapper (public+private requests and challenge resolver) without selenium. Use the most recent version of the API from Instagram, which was obtained using [reverse-engineering with Charles Proxy](https://adw0rd.com/2020/03/26/sniffing-instagram-charles-proxy/en/) and [Proxyman](https://proxyman.io/).

*Instagram API valid for **3 January 2022** (last reverse-engineering check)*

Support **Python >= 3.6**, recommend 3.8+

For any other languages (e.g. C++, C#, F#, D, [Golang](https://github.com/adw0rd/instagrapi-rest/tree/main/golang), Erlang, Elixir, Nim, Haskell, Lisp, Closure, Julia, R, Java, Kotlin, Scala, OCaml, JavaScript, Crystal, Ruby, Rust, [Swift](https://github.com/adw0rd/instagrapi-rest/tree/main/swift), Objective-C, Visual Basic, .NET, Pascal, Perl, Lua, PHP and others), I suggest using [instagrapi-rest](https://github.com/adw0rd/instagrapi-rest) or [Lamadava SaaS](https://lamadava.com)

[Support Chat in Telegram](https://t.me/instagrapi)
![](https://gist.githubusercontent.com/m8rge/4c2b36369c9f936c02ee883ca8ec89f1/raw/c03fd44ee2b63d7a2a195ff44e9bb071e87b4a40/telegram-single-path-24px.svg) and [GitHub Discussions](https://github.com/adw0rd/instagrapi/discussions)


## Features

1. Performs [Public API](https://adw0rd.github.io/instagrapi/usage-guide/fundamentals.html) (web, anonymous) or [Private API](https://adw0rd.github.io/instagrapi/usage-guide/fundamentals.html) (mobile app, authorized) requests depending on the situation (to avoid Instagram limits)
2. [Login](https://adw0rd.github.io/instagrapi/usage-guide/interactions.html) by username and password, including 2FA and by sessionid (and uses Authorization header instead Cookies)
3. [Challenge Resolver](https://adw0rd.github.io/instagrapi/usage-guide/challenge_resolver.html) have Email and SMS handlers
4. Support [upload](https://adw0rd.github.io/instagrapi/usage-guide/media.html) a Photo, Video, IGTV, Reels, Albums and Stories
5. Support work with [User](https://adw0rd.github.io/instagrapi/usage-guide/user.html), [Media](https://adw0rd.github.io/instagrapi/usage-guide/media.html), [Comment](https://adw0rd.github.io/instagrapi/usage-guide/comment.html), [Insights](https://adw0rd.github.io/instagrapi/usage-guide/insight.html), [Collections](https://adw0rd.github.io/instagrapi/usage-guide/collection.html), [Location](https://adw0rd.github.io/instagrapi/usage-guide/location.html) (Place), [Hashtag](https://adw0rd.github.io/instagrapi/usage-guide/hashtag.html) and [Direct Message](https://adw0rd.github.io/instagrapi/usage-guide/direct.html) objects
6. [Like](https://adw0rd.github.io/instagrapi/usage-guide/media.html), [Follow](https://adw0rd.github.io/instagrapi/usage-guide/user.html), [Edit account](https://adw0rd.github.io/instagrapi/usage-guide/account.html) (Bio) and much more else
7. [Insights](https://adw0rd.github.io/instagrapi/usage-guide/insight.html) by account, posts and stories
8. [Build stories](https://adw0rd.github.io/instagrapi/usage-guide/story.html) with custom background, font animation, link sticker and mention users
9. In the next release, account registration and captcha passing will appear

## Examples of apps that use instagrapi

* [Lamadava SaaS](https://instagrapi.com) - trouble-free SaaS for providing data from IG (anonymously) and automate publications, stories, direct and much more else
* [Web-service for Download Posts, Stories and Highlights](https://igdl.club/)
* [Instagram Bot for Download Posts, Stories and Highlights](https://www.instagram.com/fetch_story/)
* [Telegram Bot for Download Posts, Stories and Highlights](https://t.me/instagram_load_bot)

### Basic Usage

``` python
from instagrapi import Client

cl = Client()
cl.login(ACCOUNT_USERNAME, ACCOUNT_PASSWORD)

user_id = cl.user_id_from_username("adw0rd")
medias = cl.user_medias(user_id, 20)
```

<details>
    <summary>Additional example</summary>

```python
from instagrapi import Client
from instagrapi.types import StoryMention, StoryMedia, StoryLink, StoryHashtag

cl = Client()
cl.login(USERNAME, PASSWORD, verification_code="<2FA CODE HERE>")

media_pk = cl.media_pk_from_url('https://www.instagram.com/p/CGgDsi7JQdS/')
media_path = cl.video_download(media_pk)
adw0rd = cl.user_info_by_username('adw0rd')
hashtag = cl.hashtag_info('dhbastards')

cl.video_upload_to_story(
    media_path,
    "Credits @adw0rd",
    mentions=[StoryMention(user=adw0rd, x=0.49892962, y=0.703125, width=0.8333333333333334, height=0.125)],
    links=[StoryLink(webUri='https://github.com/adw0rd/instagrapi')],
    hashtags=[StoryHashtag(hashtag=hashtag, x=0.23, y=0.32, width=0.5, height=0.22)],
    medias=[StoryMedia(media_pk=media_pk, x=0.5, y=0.5, width=0.6, height=0.8)]
)
```
</details>

## Documentation

* [Index](https://adw0rd.github.io/instagrapi/)
* [Getting Started](https://adw0rd.github.io/instagrapi/getting-started.html)
* [Usage Guide](https://adw0rd.github.io/instagrapi/usage-guide/fundamentals.html)
* [Interactions](https://adw0rd.github.io/instagrapi/usage-guide/interactions.html)
  * [`Media`](https://adw0rd.github.io/instagrapi/usage-guide/media.html) - Publication (also called post): Photo, Video, Album, IGTV and Reels
  * [`Resource`](https://adw0rd.github.io/instagrapi/usage-guide/media.html) - Part of Media (for albums)
  * [`MediaOembed`](https://adw0rd.github.io/instagrapi/usage-guide/media.html) - Short version of Media
  * [`Account`](https://adw0rd.github.io/instagrapi/usage-guide/account.html) - Full private info for your account (e.g. email, phone_number)
  * [`TOTP`](https://adw0rd.github.io/instagrapi/usage-guide/totp.html) - 2FA TOTP helpers (generate seed, enable/disable TOTP, generate code as Google Authenticator)
  * [`User`](https://adw0rd.github.io/instagrapi/usage-guide/user.html) - Full public user data
  * [`UserShort`](https://adw0rd.github.io/instagrapi/usage-guide/user.html) - Short public user data (used in Usertag, Comment, Media, Direct Message)
  * [`Usertag`](https://adw0rd.github.io/instagrapi/usage-guide/user.html) - Tag user in Media (coordinates + UserShort)
  * [`Location`](https://adw0rd.github.io/instagrapi/usage-guide/location.html) - GEO location (GEO coordinates, name, address)
  * [`Hashtag`](https://adw0rd.github.io/instagrapi/usage-guide/hashtag.html) - Hashtag object (id, name, picture)
  * [`Collection`](https://adw0rd.github.io/instagrapi/usage-guide/collection.html) - Collection of medias (name, picture and list of medias)
  * [`Comment`](https://adw0rd.github.io/instagrapi/usage-guide/comment.html) - Comments to Media
  * [`Highlight`](https://adw0rd.github.io/instagrapi/usage-guide/highlight.html) - Highlights
  * [`Story`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - Story
  * [`StoryLink`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - Link Sticker
  * [`StoryLocation`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - Tag Location in Story (as sticker)
  * [`StoryMention`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - Mention users in Story (user, coordinates and dimensions)
  * [`StoryHashtag`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - Hashtag for story (as sticker)
  * [`StorySticker`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - Tag sticker to story (for example from giphy)
  * [`StoryBuild`](https://adw0rd.github.io/instagrapi/usage-guide/story.html) - [StoryBuilder](/instagrapi/story.py) return path to photo/video and mention co-ordinates
  * [`DirectThread`](https://adw0rd.github.io/instagrapi/usage-guide/direct.html) - Thread (topic) with messages in Direct Message
  * [`DirectMessage`](https://adw0rd.github.io/instagrapi/usage-guide/direct.html) - Message in Direct Message
  * [`Insight`](https://adw0rd.github.io/instagrapi/usage-guide/insight.html) - Insights for a post
* [Development Guide](https://adw0rd.github.io/instagrapi/development-guide.html)
* [Handle Exceptions](https://adw0rd.github.io/instagrapi/usage-guide/handle_exception.html)
* [Challenge Resolver](https://adw0rd.github.io/instagrapi/usage-guide/challenge_resolver.html)
* [Exceptions](https://adw0rd.github.io/instagrapi/exceptions.html)
