# darkrecon-exercises

This repository contains exercises that will be used to evaluate the skills of potential engineers for the `darkrecon` 
team.

## Exercises 📝

- [Exercise 01](#exercise-01)

## Exercise 01

### Intro

Web scraping is the process of automating data collection from the web. The web scraping software may directly access 
the `World Wide Web` using the `Hypertext Transfer Protocol` or a `web browser`. While web scraping can be done manually 
by a software user, the term typically refers to `automated processes` implemented using a `bot` or `web crawler`. It is 
a form of copying in which specific data is gathered and copied from the web, typically into a central local database or 
spreadsheet, for later `retrieval` or `analysis`.

> Source: https://en.wikipedia.org/wiki/Web_scraping

For this exercise you'll have crate a program that will scrape the contents of special website designed as a 
web-scraping sandbox: [books.toscrape.com](http://books.toscrape.com/).

### Important: You can use whichever programming language you are comfortable with to do the job! 

The goal is to create a small `project` (a scraper) that will generate a 
[csv](https://en.wikipedia.org/wiki/Comma-separated_values) with the information about each book that can be found on 
the [book store catalog](http://books.toscrape.com/catalogue/category/books_1/index.html).

You have to `iterate over` each `page` from the `book catalog` starting from 
[page-1](http://books.toscrape.com/catalogue/category/books_1/index.html), 
[page-2](http://books.toscrape.com/catalogue/category/books_1/page-2.html), ..., 
[page-50](http://books.toscrape.com/catalogue/category/books_1/page-50.html). On each of those pages you will see a list
of books - each with an `unique link`. When you `open` those `links` you will see more `detailed information` about each
book. From this information you need to `extract` the following information and store it in the csv.

```csv
title, upc, type, price, availability, reviews, description 
```

### Description of the fields

| Field Name   | Description                         |
|--------------|-------------------------------------|
| title        | the title of the book               |
| upc          | the upc of the book                 |
| type         | the type of the product             |
| price        | the price of the book including tax |
| availability | count of available books            |
| reviews      | count of reviews                    |
| description  | the description of the book         |

For reference the following table contains the information of a specific book - 
[Bright Lines](http://books.toscrape.com/catalogue/bright-lines_11/index.html)

> This book can be found on page 50 - http://books.toscrape.com/catalogue/category/books_1/page-50.html

| Field Name   | Value                                    |
|--------------|------------------------------------------|
| title        | Bright Lines                             |
| upc          | 230ac636ea0ea415                         |
| type         | Books                                    |
| price        | 39.07                                    |
| availability | 1                                        |
| reviews      | 0                                        |
| description  | A vibrant debut novel... (it continuous) |

> Important: the `description` may contain `,` (comma) which will break the csv. You can replace them with a character (like `^`) to keep workaround it

### End goal

The site contains `1000` books so the `csv` is expected to have `1000` (or `1001` - if the header is included) `records` 
(rows). You should save the generated `csv` to a local file named `report.csv` in the `current working directory` (CWD) 
of your main process.

### Q&As

##### What programming language should I use?

You can use whichever programming language you are comfortable with! 

##### How to get the contents of a site?

The first and easiest way is to send an HTTP (`get`) request to the site.

```bash
# bash - this is just for example. You don't have to do the program in bash. You can use other http clients to simulate the same thing - like `postman`
curl http://books.toscrape.com/catalogue/bright-lines_11/index.html
```

This will return the `HTML` (css and js) of the web page. From that `HTML` file you can extract the values you need.

The second way is to use a [headless browser] https://en.wikipedia.org/wiki/Headless_browser like `Puppeteer, Selenium, Playwright and many more` that provides and API that can be used to manipulate actual browsers!

##### More questions?

Feel free to contact me at: `hristiyan.genchev at groupsense.io` 

> replace ` at ` with `@` - prevents scrapers hehe :D
