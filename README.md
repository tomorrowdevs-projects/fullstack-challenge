# Fullstack Webapp development

## Specification

You should implement an application for a library to store book, authors data. The application should also track sales and plot statistics in a dashboard with tabular summaries and charts.

**This application must provide an HTTP REST API to attend the requirements.**

### 1. Receive a CSV with books and import to database

Given a CSV file with many books, you need to create an import script. The script should analyze each row, verify if the author exists in the authors table (table created by you) and then insert the book in the books database using the generated author_id.
When importing each book you have to replace the currency field: change SAR to EUR.

Each author record in the database must have the following fields:

* id (self-generated)
* name

You need to store the author's data to complement the book data that will be stored afterward.

When importing the csv, generate synthetic (fake, generated by you) data about purchases of the books. Remember that also a free book should be registered as a purchase. Store also a fake date (date and hour field) of puchase. Save these data in a specific table.


### 2. Expose authors' data in an endpoint

This endpoint needs to return a paginated list with the authors' data. Optionally the authors can be searched by name.

### 3. CRUD (Create, Read, Update and Delete) of books

You need to implement these actions in your API:

* Create a book
* Read book's data
* Update book's data
* Delete book's data

Each book record has the fields as reported in the original csv file. Remember the following notes:

* id field (self-generated)
* authors (more than one author can write a book)

To retrieve a book we can filter by 4 fields (or a composition of these four):

* title
* author
* rating

But these 3 filters are optional. It must be possible to navigate all the books' data without any filter.

To create a book you need to send this payload (in json format). User can use all the fields as reported in csv file. The followings are the mandatory fields:

```
{
 "title": ,
 "price": ,
 "currency": ,
 "publisher": ,
 "page_count": ,
 "authors": // List of author ids, same ids of previous imported data
}
```

### 4. Create a frontend WebApp using React and Typescript

The frontend will have no authentication method.

The webapp should be able to consume all the endpoints. Think about these app as the app used by the manager of a book shop.

Use a nice design/layout/interface (you can use a design/UI library like Bootstrap, Tailwind and others). You can use any styling method you prefer (Scss, Css Modules, Styled Components)

There should also be a "statistics" page where you should report some useful summary and plot some interesting charts with one chart library of your choice.

You don't need to use React for this assignment, you can either use Local Storage or Context API to store the data, if needed.

For the navigation, you should use React Router.

## Project Requirements:

* Provide a working environment with your project using Docker (Docker Compose, with 2 services: web and db)
* The database should be MariaDB
* Application must be written in Python or Node.js.
* Python
    * Choose any Python web framework you want to solve the problem
    * Use PEP-8 for code style
    * [Python Coding Style](http://docs.python-guide.org/en/latest/writing/style/)
* Node.js
    * Use Express or Fastify libraries
    * Use MVC design pattern
* Every text or code must be in English
* Write the project documentation containing:
    * Description;
    * Installing (setup) and testing instructions;
    * If you provide a [docker](https://www.docker.com/) solution for setup, ensure it works without docker too.
    * Brief description of the work environment used to run this project (Computer/operating system, text editor/IDE, libraries, etc).
* Provide API documentation (in English);
* Variables, code and strings must be all in English.

## Recommendations

* Use programming good practices;
* Upload all the codebase in a public repo in your github account
* Use [git best practices](https://www.git-tower.com/learn/git/ebook/en/command-line/appendix/best-practices), with clear messages (written in English);
* Be aware when modeling the database;
* Be careful with REST API details. They can bite you!

**Have fun!**
