# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.
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
