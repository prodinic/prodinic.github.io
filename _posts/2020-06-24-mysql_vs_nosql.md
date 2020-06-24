---
title: "Why do we need deepcopy in Python project?"
categories:
  - Engineering
tags:
  - MySQL
  - NoSQL

last_modified_at: 2017-03-09T12:25:10-05:00
---

Let take a look at the MySQL and NoSQL. 

SQL Databases
SQL stands for Structured Query Language and it therefore is not a database itself but only a query languange
you can use to interact with a specific type of database.

SQL allows you to store, update, delete and of course retrive data from relational database
management systems.

* Data is stored in database tables by following a strict data schema.
* Data is distributed across multiple tables witch are connected via relations.

NoSQL is named like this becuase it basically follows the opposite approach of SQL databases.

* No schemas
* No relations which allows duplicated data across collections

For example, documents look a bit like JSON data - and as mentioned, you don't need to worry about 
any schema.

Let’s summarize the key advantages of both approaches:

**SQL**
* Clearly defined schema, data integrity is ensured
* Relations allow you to store each data only once - no duplicates

**NoSQL**
* Absence of a schema gives you more flexibility - you can adjust your stored data at any point and introduce new “fields”
* Data is stored in the format your app needs it - this speeds up fetching the data
* Vertical and horizontal scaling is possible, hence your database will be able to handle any amount of read/ write requests your app throws at it

And the disadvantages:

**SQL**
* Less flexibility, data schema needs to be known and planned in advance (adjusting it later is difficult or maybe even impossible)
* Relations can lead to very complex queries with a lot of JOIN statements
* Horizontal scaling is hard, often only vertical scaling is possible - this means that you’ll face some growth limits (regarding throughput you can handle/ performance) at some point

**NoSQL**
* Increased flexibility might lead you to work sloppy and postpone data structure decisions
* Duplicate data means that you have to update multiple collections and documents if that data changes - not just one record in one table as you would do it in the SQL world
So when might SQL be best?
You got related data, used in different “chunks” in different parts of your app, that changes relatively often (you would have to update multiple collections all the time in a NoSQL world)
A clear schema is important to you and your data is unlikely to change (drastically)
When is NoSQL best?
Exact data requirements or the data itself is unknown or subject to change/ expand
You require high (read) throughput but you won’t change your data that often (i.e. you don’t need to update dozens of documents for one change all the time)
You need to scale your database horizontally (i.e. you store enormous amounts of data and have huge read and write throughput)



