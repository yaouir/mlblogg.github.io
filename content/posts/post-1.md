---
title: "SQL 101 - A Quick start to Structured Query Language"
date: 2023-01-18T02:01:58+05:30
description: "SQL, or Structured Query Language, is a programming language that is used to communicate with databases. Think of it like a way to talk to a computer and tell it to give you specific information from a big collection of data."
tags: [SQL]
---

SQL, or Structured Query Language, is a programming language that is used to communicate with databases. Think of it like a way to talk to a computer and tell it to give you specific information from a big collection of data.

Let's imagine you have a toy box with many different toy cars. Each toy car has a color and a number on it.

You can use SQL to ask the toy box:
- Give me all the toy cars that are red.
- Give me the number of all the toy cars.
- Give me the red toy cars that have the number 3

The first thing you need to do is to SELECT what you want from the toy box.

### SELECT

```sql 
SELECT color, number
FROM toy_box
```

You can use some conditions like WHERE to filter the result, for example

```sql 
SELECT color,number FROM toy_box WHERE color='red'
```

You can also use aggregate functions like COUNT, SUM, AVG, MAX, MIN to get statistics and summaries of your data

```sql
SELECT COUNT(*) FROM toy_box;
```

You can also combine different clauses to filter and summarize your data for example

```sql
SELECT color, number FROM toy_box WHERE color = 'red' AND number = 3;
```

this query will give you the red toy cars that have the number 3

### INSERT
This command is used to insert new data into a table. For example, if you wanted to add a new toy car to the toy_box table, you could use the following SQL statement:

```sql
INSERT INTO toy_box (color, number) VALUES ('blue', 4);
```

### UPDATE
This command is used to modify existing data in a table. For example, if you wanted to change the color of a toy car in the toy_box table, you could use the following SQL statement:

```sql
UPDATE toy_box SET color = 'green' WHERE number = 4;
```
### DELETE
This command is used to delete data from a table. For example, if you wanted to delete a toy car from the toy_box table, you could use the following SQL statement:

```sql
DELETE FROM toy_box WHERE number = 4;
```

### JOIN
 This command is used to combine data from two or more tables. For example, if you wanted to retrieve information about a toy car and the person who owns it, you could use a join to combine data from the toy_box table and the owner table, like this:

```sql
SELECT toy_box.color, toy_box.number, owner.name
FROM toy_box
JOIN owner ON toy_box.owner_id = owner.id;
```

These are just a few examples of the many SQL commands that you can use to work with a database. Keep in mind that SQL is a standard language, so the syntax may vary slightly depending on the database management system (DBMS) you are using, but the concepts are similar in most SQL implementations.


SQL is a powerful and versatile language that can be used to extract, manipulate, and analyze data in a variety of ways. This tutorial has just scratched the surface of what SQL can do, but I hope it has given you a good introduction to the basics of SQL and how it can be used to work with databases.

