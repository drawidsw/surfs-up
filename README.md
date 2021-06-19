# Analysis of Hawaii weather to determine whether to surf

## Introduction

In this exercise, we are provided with temperature data from a location in Hawaii over 7 years. The recordings are made by several weather stations. We wish to determine suitability of surfing in the months of June and December.

## Dataset

Data is available in **sqllite** database (*hawaii.sqllite*). A sqllite database is nothing but a flat file, but it behaves much like a database allowing an application/user to execute sql queries against it. Thus, sqllite greatly simplifies database design eliminating the need to set up an actual database using Postgres (or equivalent). However, the disadvantage of sqllite is that it offers none of the advantages of a true relational database such as:
* primary keys for enforcing uniqueness constraints
* referential integrity using foreign keys
* indexes for fast data retrieval
* other advanced database constructs such as materialized views, triggers, stored procedures etc.

### Usage of Sqlalchemy ORM

There are two ways to retrieve data from a relational database in most applications.
* Execute sql queries directly - this can be done by calling the **execute** function on the **engine** object created by sqlalchemy when it connects to the database.
* Use ORM - ORM stands for *Object Relationship mapping*. The advantage of using ORM is that it allows a developer to define schemas, data types and relationships between entities **all within code**. ORM offers equivalent functions such as **query**, and **filter** for SQL clauses allowing the developer to write queries on the entities that represent various tables and columns in the database. In this exercise, ORM framework is used to query the tables.

## Results

### June Temperatures:

To retrieve the temperatures for June, a query was ran to filter out all temperatures with data matching a pattern like "%-06-%". The results are in the table below.

| count	| 1700.000000 |
|mean |	74.944118 |
|std |	3.257417 |
|min |	64.000000 |
|25% |	73.000000 |
|50% |	75.000000 |
|75% |	77.000000 |
|max |	85.000000 |
