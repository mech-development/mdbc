---
title: Database Introduction
duration: "3:00"
creator:
    name: Angelo Klin
    city: MEL
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Introduction to Databases
DS | Lesson 17

### LEARNING OBJECTIVES
**After this lesson, you will be able to:**
- Understand the uses and differences of various databases
- Access databases from Pandas
- Navigate Postgres

### STUDENT PRE-WORK
**Before this lesson, you should already be able to:**

- There will be multiple ways to run the exercises:
    - Using Postgres Exercises
    - Setting up local Postgres
        - Install Postgres (more details) below, if `brew` is installed, this should be as simple as `brew install postgres`
    - Using Wagon
        - Create an account at https://www.wagonhq.com/ and download the software

### INSTRUCTOR PREP
**Before this lesson, instructors will need to:**
- Review [Final Project, part 4](../../projects/final-project/part-04/README.md)
- Copy and modify the [lesson slide deck](./assets/slides/slides-17.md)
- Read through data sets and starter/solution code
- Add to the "Additional Resources" section for this lesson
- Decide on an approach to running the SQL/Postgres exercises provided:
    - **Postgres Exercises**
        - You can setup a [local demonstration of the postgres exercises here](https://pgexercises.com/gettingstarted.html)
    - **Local Postgres**
        - Students should first install Postgres
          - If `brew` is installed, this is as simple as `brew install postgres`
    - **Using Wagon**
        - Everyone will need to [create an account and download the software](https://www.wagonhq.com/) to run the sample exercises they provide.
- There is an extra [practice notebook](./code/starter-code/SQL-lab-starter.ipynb) available [solutions](./code/starter-code/SQL-lab-solution.ipynb).

### LESSON GUIDE
| TIMING | TYPE | TOPIC |
|:-:|---|---|
| 5 min | [Opening](#opening) | Lesson Objectives |
| 35 min | [Introduction](#introduction) | Introduction to Databases |
| 20 min | [Demonstration](#demo1) | Demonstration: Accessing Databases from Pandas |
| 60 min | [Demonstration](#demo2) | Demonstration/Codealong: SQL Syntax: SELECT, WHERE, GROUP BY, JOIN |
| 15 min | [Demonstration](#demo3) | Installing Postgres, CREATE TABLE |
| 40 min | [Independent Practice](#ind-practice-pandas) | Pandas and SQL Exercises |
| 5 min | [Conclusion](#conclusion) | |

---
<a name="opening"></a>
## Opening (5 min)
Today's lesson will be on databases and the SQL query language.

Databases are the standard solution for data storage and are much more robust than text or CSV files. Most analyses involve pulling data to and from a resource and in most settings, that means using a database.

Databases can come in many flavors; however, we will explore the most common: relational databases. Relational databases can also come in different varieties, but most of them use the **SQL language** for querying objects.

<a name="introduction"></a>
## Introduction to Databases (35 mins)

Databases are computer systems that manage storage and querying of data sets. Databases provide a way to organise data along with efficient methods to retrieve specific information.

Typically, retrieval is performed using a query language, a mini programming syntax with a few basic operators for data transformation, the most common of which is **SQL**.

Databases allow users to create rules that ensure proper data management and verification.

A **relational database** is a database based on links between data entities or concepts. Typically, a relational database is organised into **tables**. Each table should correspond to one entity or concept. Each **table** is similar to a single CSV file or Pandas dataframe.

For example, let's take a sample application like Twitter. Our two main entities are Users and Tweets. For each of these we would have a table.

A table is made up rows and columns, similar to a Pandas dataframe or Excel spreadsheet. A table also has a **schema** which is a set of rules for what goes in each table, similar to the header in a CSV file. These specify what columns are contained in the table and what **type** those columns are (text, integers, floats, etc.).

The addition of **type** information make this constraint stronger than a CSV file. For this reason and many others, databases allow for stronger data consistency and often are a better solution for data storage.

Each table typically has a **primary key** column. This column is a unique value per row and serves as the identifier for the row.

A table can have many **foreign keys** as well. A **foreign key** is a column that contains values to link the table to the other tables. For example, the tweets table may have as columns:

- tweet_id, the primary key tweet identifier
- the tweet text
- the user id of the member, a foreign key to the users table

These keys that link the table together define the relational database.

MySQL and Postgres are popular variants of relational databases and are widely used. Both of these are open-source so are available for free.

Alternatively, many larger companies may use Oracle or Microsoft SQL databases. While these all offer many of the same features (and use SQL as a query language), the latter also offer some maintenance features that large companies find useful.

### Normalised vs Denormalised data

Once we start organising our data into tables, we will start to separate into **normalised** or **denormalised** setups.

**Normalised** structures have a single table per entity and use many foreign keys or link table to connect the entities.

**Denormalised tables** have fewer tables and may (for example) place all of the tweets and the information on users in one table.

Each style has advantages and disadvantages. **Denormalised** tables duplicate a lot of information. For example, in our combined tweets/users table, we may store the address of each user. Now instead of storing this once per user, we are storing this once per tweet!

However, this makes the data easy to access if we ever need to find the tweet along with the user's location.

**Normalised** tables save the storage space by separating the information. However, if we ever need to access those two pieces of information, we would need to **join** the two tables, which can be a fairly slow operation.

#### Alternative databases
While relational tables are one of the most popular (and broadly useful) database types, specific applications may require different data organisation. While it is not important to know all varieties, it is good to know the overall themes:

#### Key-value stores
Some databases are nothing more than very-large (and very-fast) hash-maps or dictionaries that can be larger than memory. These are useful for storing key based data, i.e. storing the last access or visit time per user or counting things per user or customer.

Every entry in these databases is two values, a key and value and we can retrieve any value based on its key. This is exactly like a python dictionary, but can be much larger than your memory allows and uses smart caching algorithms to ensure frequently or recently accessed items are quickly accessible.

Popular key-value stores include Cassandra or `memcachedb`.

#### NoSQL or Document databases
"NoSQL" databases do not rely on a traditional table setup and are more flexible in their data organisation. Typically they do actually have SQL querying abilities, but simply model their data differently.

Many organise the data on an entity level, but often have denormalised and nested data setups. For example, for each user, we may store their metadata, along with a collection of tweets, each of which has its own metadata. This nesting can continue down encapsulating entities. This data layout is similar to that in JSON documents.

Popular databases of this variety include `mongodb` and `couchdb`.

**Check:** Below are a few examples of data storage. Discuss the best storage or database solution for each scenario:

1. Database for an application with user profiles
2. Database for an online store
3. Storing last visit date of a user
4. Consider the following data set from Uber with the follow fields:

- User ID
- User Name
- Driver ID
- Driver Name
- Ride ID
- Ride Time
- Pickup Longitude
- Pickup Latitude
- Pickup Location Entity
- Drop-off Longitude
- Drop-off Latitude
- Drop-off Location Entity
- Miles
- Travel Time
- Fare
- CC Number

How would you design a relational database to support this data? List the tables you would create, what fields they would contain and how they would like to other tables.

<a name="demo1"></a>
## Demonstration: Accessing Databases from Pandas (20 min)

While databases provide many analytical capabilities, often it is useful to pull the data back into Python for more flexible programming. Large, fixed operations would be more efficient in a database, but Pandas allows for interactive processing.

For example, if you want to aggregate nightly log-ins or sales to present a report or dashboard, this operation is likely not changing and operating on a large data set. This can run very efficiently in a database rather than by connecting to it with Python.

However, if we want to investigate login or sales data further and ask more interactive questions, then Python would be more practical.

```python
import pandas as pd
from pandas.io import sql
```

Pandas can connect to most relational databases. In this demonstration, we will create and connect to a SQLite database.

SQLite creates portable SQL databases saved in a single file. These databases are stored in a very efficient manner and allow fast querying, making them ideal for small databases or databases that need to be moved across machines.

If you are looking to start using a database without the setup of `mysql` or `postgres`, SQLite is a good start!

We can create a SQLite database as follows:
```python
import sqlite3

conn = sqlite3.connect("dat-test.db")
```

This creates a file `dat-test.db` which will act as a relational/SQL database.

### Writing data into a database

Data in Pandas can be loaded into a relational database. For the most part, Pandas can use column information to infer the schema for the table it creates.

Let's return to the Rossmann sales data and load that into the database.

```python
import pandas as pd

data = pd.read_csv("../../../data/rossmann.csv", low_memory = False)
data.head()
```

Data is moved to the database through the `to_sql` command, similar to the `to_csv` command.

`to_sql` takes as arguments:

- `name`, the table name to create
- `con`, a connection to a database
- `index`, whether to input the index column
- `schema`, if we want to write a custom schema for the new table
- `if_exists`, what to do if the table already exists. We can overwrite it, add to it or fail

```python
data.to_sql("rossmann_sales",
            con = conn,
            if_exists = "replace",
            index = False)
```

### Reading data from a database

If we already have data in our database, we can use Pandas to query it. Querying is done through the `read_sql` command in the `sql` module.

```python
import pandas as pd
from pandas.io import sql

sql.read_sql("SELECT * FROM ROSSMANN_SALES LIMIT 10", con = conn)
```

This runs the query passed in and returns a dataframe with the results:

```python
sql.read_sql("SELECT STORE, SUM(CUSTOMERS) FROM ROSSMANN_SALES GROUP BY STORE", con = conn)
```

**Check:** Load the Rossmann Store metadata in `rossmann-stores.csv` and create a table into the database from it.

<a name="demo2"></a>
## Demonstration/Codealong: SQL Syntax (60 mins)

## SQL Operators

### SELECT
Every query should start with `SELECT`. `SELECT` is followed by the names of the columns in the output.

`SELECT` is always paired with `FROM` and `FROM` identifies the table to retrieve data from.

```sql
SELECT <columns>
FROM   <table>
```

`SELECT *` denotes returns **all** of the columns.

Rossmann Stores example:
```sql
SELECT Store, Sales
FROM   rossmann_sales
```

**Check:** Write a query that returns the `Store`, `Date` and `Customers`.

### WHERE
`WHERE` is used to filter table to a specific criteria and follows the `FROM` clause.

```sql
SELECT <columns>
FROM   <table>
WHERE  <condition>
```

Rossman Stores example:
```sql
SELECT Store, Sales
FROM   rossmann_sales
WHERE  Store = 1
```

```sql
SELECT Store, Sales
FROM   rossmann_sales
WHERE  Store = 1 and Open = 1
```

The condition is some filter applied to the rows, where rows that match the condition will be in the output.

**Check:** Write a query that returns the `Store`, `Date` and `Customers` for when the stores were open and running a promotion.

### GROUP BY

`GROUP BY` allows us to aggregate over any field in the table. We identify some key with which want to segment the rows. Then, we roll-up or compute some statistic over all of the rows that match that key.

`GROUP BY` **must be** paired with an aggregate function - the statistic we want to compute in the rows - in the `SELECT` statement.

`COUNT(*)` denotes counting up all of the rows. Other aggregate functions commonly available are `AVG` - average, `MAX`, `MIN` and `SUM`.

If we want an aggregate over the entire table - without results specific to any key, we can use an aggregate function in the `SELECT` statement and ignore the `GROUP BY` clause.

Rossman Stores example:
```sql
SELECT   Store, SUM(Sales), AVG(Customers)
FROM     rossmann_sales
WHERE    Open = 1
GROUP BY Store
```

**Check:** Write a query that returns the total sales on promotion days.

### ORDER BY
Results of a query can be sorted by `ORDER BY`.

If we want to order the states by the number of polls, we would add an `ORDER BY` clause at the end.

Rossman Stores example:
```sql
SELECT   Store, SUM(Sales) as total_sales, AVG(Customers)
FROM     rossmann_sales
WHERE    Open = 1
GROUP BY Store
ORDER BY total_sales desc
```

`COUNT(*) as cnt` renames the `COUNT(*)` value as `cnt` so we can refer to it later in the `ORDER BY` clause.

`desc` tells the result to be in **descending** order as opposed to increasing.

### JOIN
`JOIN` allows us to access data across many tables. We will need to specify how a row in one table links to a row in another.

```sql
SELECT a.Store, a.Sales, s.CompetitionDistance
FROM   rossmann_sales a
JOIN   rossmann_stores s
  ON   a.Store = s.Store
```

Here `ON` denotes an **Inner Join**.

#### Inner Join
By default, most joins are an **Inner Join**, which means only when there is a match in both tables, does a row appear in the result.

#### Outer Join
If we want to keep the rows of one table **even if there is no matching counterpart** we can perform an **Outer Join**. Outer joins can be `LEFT`, `RIGHT` or `FULL` meaning keep all the left rows, all the right rows or **all** the rows, respectively.

<a name="ind-practice"></a>
## Independent Practice: Pandas and SQL (40 mins)

1. Load the Walmart sales and store features data
2. Create a table for each of those data sets
3. Select the store, date and fuel price on days it was over 90 degrees
4. Select the store, date and weekly sales and temperature
5. What were average sales on holiday vs. non-holiday sales
6. What were average sales on holiday vs. non-holiday sales when the temperature was below 32 degrees

## Demonstration: Installing Postgres (15 min)

On a Mac:
```sh
brew install postgres
```

`brew` will provide a few command to make sure postgres runs on startup.

If this is done, you can demonstrate the `postgres` command line.

On Linux (Ubuntu):
```bash
sudo apt-get install postgresql postgresql-client postgresql-contrib
```

Connect to the database with:
```bash
sudo -i -u postgres
psql
```

See these [installation instructions](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04) and [these](https://help.ubuntu.com/community/PostgreSQL) if any issues arise.

#### Demonstration of Postgres Shell
- Starting postgres
```sh
psql
```

- Listing tables
```sh
\dt
```

- Creating a table
```sh
create table example(
    id int,
    name varchar(140),
    value float
);
```

- Inserting a row
```sql
insert into example values(1, "general assembly", 3.14);
```

- Querying it back
```sql
select *
from   example;
```

<a name="independent-practice-sql"></a>
## Independent Practice: SQL (Untimed - Extra)

#### PG-Exercises

[Postgres Exercises]((www.pgexercises.com)):
The data set for these exercises is for a newly created country club, with a set of members, facilities such as tennis courts and booking history for those facilities. Amongst other things, the club wants to understand how they can use their information to analyze facility usage/demand.

Answer 3-5 questions in each of the following categories:

1. [Simple SQL Queries](https://pgexercises.com/questions/basic/)
1. [Aggregation](https://pgexercises.com/questions/aggregates/)
1. [Joins and Subqueries](https://pgexercises.com/questions/joins/)

#### Wagon
This requires signing up for the Wagon service and downloading their application, but it gives access to some sample databases.

The following exercises use the `music_store` database in the Wagon application. We will work 3 tables from it:
- `music_store.artists`
- `music_store.albums`
- `music_store.tracks`

1. Display all tracks on which Jimmy Page was the composer.
1. Who were the top five composers by number of tracks?
1. Who were the top five composers by length of tracks?
1. Select all of the albums from Led Zeppelin
1. Count the number of albums per artist and display the top 10.
1. Display the track name and album name from all Led Zeppelin albums
1. Compute how many songs and how long (in minutes) each Led Zeppelin album was.

##### Wagon Solutions:

1. Display all tracks on which Jimmy Page was the composer:
2. Who were the top five composers by number of tracks?
3. Who were the top five composers by length of tracks?
4. Select all of the albums from Led Zeppelin
5. Count the number of albums per artist and display the top 10.
6. Display the track name and album name from all Led Zeppelin albums
7. Compute how many songs and how long (in minutes) each Led Zeppelin album was.

<a name="conclusion"></a>
## Conclusion (5 mins)
- While this was a brief introduction to databases, they are often at the core of any data analysis. Most data acquisition would start with retrieving data from a database. SQL is a key language that any data scientist should understand and luckily there are only a few key instructions to remember:
    - SELECT: Used in every query to define the resulting rows
    - WHERE: To filter rows based a value in a certain column
    - GROUP BY: Equivalent to the Pandas group by
    - JOIN: Equivalent to the Pandas join

- Pandas can be used to access data from databases as well. The result of the queries will end up in a Pandas dataframe.
- There is much more to learn about query optimisation if one dives further!

***

### UPCOMING PROJECTS
|   |   |
|---|---|
| **Upcoming Projects** | [Final Project, part 4](../../projects/final-project/part-04/README.md)

### ADDITIONAL RESOURCES
- [Pandas: Comparison with SQL](http://pandas.pydata.org/pandas-docs/stable/comparison_with_sql.html)
- [PostgresSQL Exercises](https://pgexercises.com/)
- [SQL Zoo](http://sqlzoo.net/)
