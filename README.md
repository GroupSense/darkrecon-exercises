# darkrecon-exercises

This repository contains exercises that will be used to evaluate the skills of potential engineers for the `darkrecon` team.

## Exercises 📝

- [Exercise 01](exercise-01)

## Exercise 01

#### Intro

Web scraping is the process of automating data collection from the web. The web scraping software may directly access the `World Wide Web` using the `Hypertext Transfer Protocol` or a `web browser`. While web scraping can be done manually by a software user, the term typically refers to `automated processes` implemented using a `bot` or `web crawler`. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later `retrieval` or `analysis`.

Source: https://en.wikipedia.org/wiki/Web_scraping

For this exercise you'll have to scrape the contents of special website designed as a web-scraping sandbox: [books.toscrape.com](http://books.toscrape.com/).

Create a `program` (project, script) that will create a [csv](https://en.wikipedia.org/wiki/Comma-separated_values) with the following information about each book found on the [store catalog](http://books.toscrape.com/catalogue/category/books_1/index.html).

---

title, upc, type, price, availability, reviews, description 

---

> price - including tax
> 
> availability - count of avilable books

You can find `this information` for each book when you open the specific link to that book.

#### Example

On each page of the book [store catalog](http://books.toscrape.com/catalogue/category/books_1/index.html) you can see a list of `book`s. If you go on the [next page](http://books.toscrape.com/catalogue/category/books_1/page-2.html) you can find more books! The catalog has a total of [50](http://books.toscrape.com/catalogue/category/books_1/page-50.html) pages.

If you go to a random page - for example `50` of the book catalog: http://books.toscrape.com/catalogue/category/books_1/page-50.html on of the books there is [Bright Lines](http://books.toscrape.com/catalogue/bright-lines_11/index.html)

For this specific book the needed values are as follows:

- `title` - Bright Lines
- `upc` - 230ac636ea0ea415
- `type` - Books
- `price` - 39.07
- `availability` - 1
- `reviews` - 0
- `description` - A vibrant debut novel...

> Important: the description may contain `,` (comma) which will break the csv. You can replace them with a character (like `^`) to keep workaround it

#### Goal

The main goal is to iterate all `50 pages` of the [book store catalog](http://books.toscrape.com/catalogue/category/books_1/index.html) and for each found book (you might have to scrape each page independently) add a record to the `csv`. At the end of the iteration save the result csv into `result.csv` at the `CWD`.
