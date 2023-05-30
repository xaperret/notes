# INTRODUCTION TO DATABASES
## INTRODUCTION TO DATABASES

### WHAT IS A DATABASE ?

- When asked this question an engineer answered 

> I immediately think of my mother's recipe book, which is a spiral notebook. 
> She keeps her recipes in a spiral notebook, every page of the number, and she keeps an index at the beginning of that note books so she can easily find the recipe. 
> Well, that's a database. My mom is a database engineer

- In a way a database is just of **way to held data** in an **organized** manner. The earlier form of databases used [[File System]]. This meant that the most basic component of such system was contained in a [[File]] and named **data item**.

- Data was organized into text files.

```ad-important
title: Definition

- A **database** is a form of electronic storage in which data is held in an **organized** manner
```

A more formal definition would be 

```ad-important
title: Definition

- A **database** is a collection of interrelated stored data that serves the needs of multiple users within one or more organizations. 
```

### HOW TO MANAGE DATABASES ?

The way we manage database is by using a [[Database management system]], *DBMS*.

```ad-important
title: Definition

- A database management system is a generalized software system for manipulating databases.

```

A DBMS serves as an interface between the database and its end users or programs, allowing users to retrieve, update, and manage how the information is organized and optimized. It provides

- logical view
- physical view
- data definition language
- data manipulation language
- database utilities

[[Relational Database]] provides a better **data independence** than the older way of storing data (CODASYL database management system).

```ad-important
title: Definition

- **Data independence** is the ability to make changes in either the logical or physical structure of the database without requiring reprogramming of application programs.

```

**Data independence** makes database conversion and reorganization much easier.

### DATABASE TASKS

A database task is to

- store data
- form relationships
- filter data
- search data
- perform CRUD operations

### WHAT IS DATA ?

In basic terms, data is facts and figures about anything. All data contains elements or features and attributes by which they can be identified. For example, a person can be identified by attributes like their age, height, or hair color. 

This data is separated and stored in what's known as **entities** that represent those elements.

```ad-important
title: Definition

- An **entity** is like a table.
```

![[Pasted image 20230513155634.png]]

An entity is composed of 

- attributes (e.g. in the example above : first name, last name, date of birth and email)

There are many ways to **organize** data :

- [[Relational Database]] : used for storing structured data in tabular format
- [[Object-Oriented Database]] : information in an object-oriented database is represented in the form of objects, as in object-oriented programming.
- [[Distributed Database]] : distributed database consists of two or more files located in different sites. The database may be stored on multiple computers, located in the same physical location, or scattered over different networks.
- [[Data warehouse]] : central repository for data, a data warehouse is a type of database specifically designed for fast query and analysis.
- [[Graph Oriented Database]] : a graph database stores data in terms of entities and the relationships between entities.
- **OLTP databases.** An OLTP database is a speedy, analytic database designed for large numbers of transactions performed by multiple users.
- [[Document Database]] : designed for storing, retrieving, and managing document-oriented information, [document databases](https://www.oracle.com/uk/autonomous-database/autonomous-json-database/) are a modern way to store data in JSON format rather than rows and columns.
- [[NoSQL Database]] : provide a flexible structure for storing and scaling data
- [[Self-driving databases]] : The newest and most groundbreaking type of database, self-driving databases (also known as autonomous databases) are cloud-based and use machine learning to automate database tuning, security, backups, updates, and other routine management tasks traditionally performed by database administrators.

The database could be stored :

- locally
- on the cloud

Other types of data :

- [[Big Data]] : Big data contains a wide variety of data, arriving in increasing volumes and at high velocity.

## REFERENCES

- [Database Management Systems / Ramakrishnan](http://library.epfl.ch/en/beast?isbn=9780072465631)
- https://www.coursera.org/learn/introduction-to-databases/home/week/1
- https://www.oracle.com/uk/database/what-is-database/
- https://www.javatpoint.com/types-of-databases
- https://www.ibm.com/topics/relational-databases
- https://www.tutorialspoint.com/Types-of-databases
- http://graphdatamodeling.com/GraphDataModeling/History.html