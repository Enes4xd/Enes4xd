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
This is Python version 3.11.0 alpha 7
=====================================

.. image:: https://github.com/python/cpython/workflows/Tests/badge.svg
   :alt: CPython build status on GitHub Actions
   :target: https://github.com/python/cpython/actions

.. image:: https://dev.azure.com/python/cpython/_apis/build/status/Azure%20Pipelines%20CI?branchName=main
   :alt: CPython build status on Azure DevOps
   :target: https://dev.azure.com/python/cpython/_build/latest?definitionId=4&branchName=main

.. image:: https://img.shields.io/badge/discourse-join_chat-brightgreen.svg
   :alt: Python Discourse chat
   :target: https://discuss.python.org/


Copyright © 2001-2022 Python Software Foundation.  All rights reserved.

See the end of this file for further copyright and license information.

.. contents::

General Information
-------------------

- Website: https://www.python.org
- Source code: https://github.com/python/cpython
- Issue tracker: https://bugs.python.org
- Documentation: https://docs.python.org
- Developer's Guide: https://devguide.python.org/

Contributing to CPython
-----------------------

For more complete instructions on contributing to CPython development,
see the `Developer Guide`_.

.. _Developer Guide: https://devguide.python.org/

Using Python
------------

Installable Python kits, and information about using Python, are available at
`python.org`_.

.. _python.org: https://www.python.org/

Build Instructions
------------------

On Unix, Linux, BSD, macOS, and Cygwin::

    ./configure
    make
    make test
    sudo make install

This will install Python as ``python3``.

You can pass many options to the configure script; run ``./configure --help``
to find out more.  On macOS case-insensitive file systems and on Cygwin,
the executable is called ``python.exe``; elsewhere it's just ``python``.

Building a complete Python installation requires the use of various
additional third-party libraries, depending on your build platform and
configure options.  Not all standard library modules are buildable or
useable on all platforms.  Refer to the
`Install dependencies <https://devguide.python.org/setup/#install-dependencies>`_
section of the `Developer Guide`_ for current detailed information on
dependencies for various Linux distributions and macOS.

On macOS, there are additional configure and build options related
to macOS framework and universal builds.  Refer to `Mac/README.rst
<https://github.com/python/cpython/blob/main/Mac/README.rst>`_.

On Windows, see `PCbuild/readme.txt
<https://github.com/python/cpython/blob/main/PCbuild/readme.txt>`_.

If you wish, you can create a subdirectory and invoke configure from there.
For example::

    mkdir debug
    cd debug
    ../configure --with-pydebug
    make
    make test

(This will fail if you *also* built at the top-level directory.  You should do
a ``make clean`` at the top-level first.)

To get an optimized build of Python, ``configure --enable-optimizations``
before you run ``make``.  This sets the default make targets up to enable
Profile Guided Optimization (PGO) and may be used to auto-enable Link Time
Optimization (LTO) on some platforms.  For more details, see the sections
below.

Profile Guided Optimization
^^^^^^^^^^^^^^^^^^^^^^^^^^^

PGO takes advantage of recent versions of the GCC or Clang compilers.  If used,
either via ``configure --enable-optimizations`` or by manually running
``make profile-opt`` regardless of configure flags, the optimized build
process will perform the following steps:

The entire Python directory is cleaned of temporary files that may have
resulted from a previous compilation.

An instrumented version of the interpreter is built, using suitable compiler
flags for each flavor. Note that this is just an intermediary step.  The
binary resulting from this step is not good for real-life workloads as it has
profiling instructions embedded inside.

After the instrumented interpreter is built, the Makefile will run a training
workload.  This is necessary in order to profile the interpreter's execution.
Note also that any output, both stdout and stderr, that may appear at this step
is suppressed.

The final step is to build the actual interpreter, using the information
collected from the instrumented one.  The end result will be a Python binary
that is optimized; suitable for distribution or production installation.


Link Time Optimization
^^^^^^^^^^^^^^^^^^^^^^

Enabled via configure's ``--with-lto`` flag.  LTO takes advantage of the
ability of recent compiler toolchains to optimize across the otherwise
arbitrary ``.o`` file boundary when building final executables or shared
libraries for additional performance gains.


What's New
----------

We have a comprehensive overview of the changes in the `What's New in Python
3.11 <https://docs.python.org/3.11/whatsnew/3.11.html>`_ document.  For a more
detailed change log, read `Misc/NEWS
<https://github.com/python/cpython/blob/main/Misc/NEWS.d>`_, but a full
accounting of changes can only be gleaned from the `commit history
<https://github.com/python/cpython/commits/main>`_.

If you want to install multiple versions of Python, see the section below
entitled "Installing multiple versions".


Documentation
-------------

`Documentation for Python 3.11 <https://docs.python.org/3.11/>`_ is online,
updated daily.

It can also be downloaded in many formats for faster access.  The documentation
is downloadable in HTML, PDF, and reStructuredText formats; the latter version
is primarily for documentation authors, translators, and people with special
formatting requirements.

For information about building Python's documentation, refer to `Doc/README.rst
<https://github.com/python/cpython/blob/main/Doc/README.rst>`_.


Converting From Python 2.x to 3.x
---------------------------------

Significant backward incompatible changes were made for the release of Python
3.0, which may cause programs written for Python 2 to fail when run with Python
3.  For more information about porting your code from Python 2 to Python 3, see
the `Porting HOWTO <https://docs.python.org/3/howto/pyporting.html>`_.


Testing
-------

To test the interpreter, type ``make test`` in the top-level directory.  The
test set produces some output.  You can generally ignore the messages about
skipped tests due to optional features which can't be imported.  If a message
is printed about a failed test or a traceback or core dump is produced,
something is wrong.

By default, tests are prevented from overusing resources like disk space and
memory.  To enable these tests, run ``make testall``.

If any tests fail, you can re-run the failing test(s) in verbose mode.  For
example, if ``test_os`` and ``test_gdb`` failed, you can run::

    make test TESTOPTS="-v test_os test_gdb"

If the failure persists and appears to be a problem with Python rather than
your environment, you can `file a bug report <https://bugs.python.org>`_ and
include relevant output from that command to show the issue.

See `Running & Writing Tests <https://devguide.python.org/runtests/>`_
for more on running tests.

Installing multiple versions
----------------------------

On Unix and Mac systems if you intend to install multiple versions of Python
using the same installation prefix (``--prefix`` argument to the configure
script) you must take care that your primary python executable is not
overwritten by the installation of a different version.  All files and
directories installed using ``make altinstall`` contain the major and minor
version and can thus live side-by-side.  ``make install`` also creates
``${prefix}/bin/python3`` which refers to ``${prefix}/bin/pythonX.Y``.  If you
intend to install multiple versions using the same prefix you must decide which
version (if any) is your "primary" version.  Install that version using ``make
install``.  Install all other versions using ``make altinstall``.

For example, if you want to install Python 2.7, 3.6, and 3.11 with 3.11 being the
primary version, you would execute ``make install`` in your 3.11 build directory
and ``make altinstall`` in the others.


Issue Tracker and Mailing List
------------------------------

Bug reports are welcome!  You can use the `issue tracker
<https://bugs.python.org>`_ to report bugs, and/or submit pull requests `on
GitHub <https://github.com/python/cpython>`_.

You can also follow development discussion on the `python-dev mailing list
<https://mail.python.org/mailman/listinfo/python-dev/>`_.


Proposals for enhancement
-------------------------

If you have a proposal to change Python, you may want to send an email to the
`comp.lang.python`_ or `python-ideas`_ mailing lists for initial feedback.  A
Python Enhancement Proposal (PEP) may be submitted if your idea gains ground.
All current PEPs, as well as guidelines for submitting a new PEP, are listed at
`peps.python.org <https://peps.python.org/>`_.

.. _python-ideas: https://mail.python.org/mailman/listinfo/python-ideas/
.. _comp.lang.python: https://mail.python.org/mailman/listinfo/python-list


Release Schedule
----------------

See :pep:`664` for Python 3.11 release details.


Copyright and License Information
---------------------------------


Copyright © 2001-2022 Python Software Foundation.  All rights reserved.

Copyright © 2000 BeOpen.com.  All rights reserved.

Copyright © 1995-2001 Corporation for National Research Initiatives.  All
rights reserved.

Copyright © 1991-1995 Stichting Mathematisch Centrum.  All rights reserved.

See the `LICENSE <https://github.com/python/cpython/blob/main/LICENSE>`_ for
information on the history of this software, terms & conditions for usage, and a
DISCLAIMER OF ALL WARRANTIES.

This Python distribution contains *no* GNU General Public License (GPL) code,
so it may be used in proprietary projects.  There are interfaces to some GNU
code but these are entirely optional.

All trademarks referenced herein are property of their respective holders.
