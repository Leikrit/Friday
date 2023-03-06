# Lesson 1
40% assignments and experiments + 60% examination

## Introduction

### What is database

- a **collection** of data.

- a database can be of **any size** and of **varying complexity**.

- a **schema** is definition of a database. It defines the meaning of data.

- an **instance** of a database is the collection of data in the database at a particular point of time.

## DBMS
 
 Database Management System

 A DBMS is a collection of software programs to enable users to create, maintain and utilize a database.

 - Insert records
 - Delete records
 - Update records
 - Query records

> neo4j is a graph database

### Drawback of File System

1. Data Redundancy and Inconsistency

2. Difficulty in accessing data

3. Integrity problems (Constraints)

4. Atomicity (原子性) of updates 

5. Concurrent Access by multiple users

6. Security problems

### Advantage of DBMS

- Data independence
- Efficient data access
- Data integrity and security
- Data administration
- Concurrent access and crash recovery

Overall: Reduced application development time.

***

## Data Models

A data model is a collection of tools or concepts for describing data, the meaning of data, data relationships and data constraints.

- Object-based logical models.

### Record-based Logical Models

#### **Entity- Relationship Model (ER Model)**

#### **Relation Model**

Main concept: **relation** ,basically a table with rows and columns. A column is also called a **field** or **attribute**.

Other models such as the Network Model, Hierarchical Model, object-oriented model,objected-relational model.

## Data Abstraction

### Physical level

How and where data are actually stored, low level data structures are specified at this level.

### Conceptual level (Logical level) 

Describes what data should be stored in the database, and relationship and semantics of the data.

### View level

Relevant partial view of the database to be particular type of users.

## Data Independence
- Physical Data Independence

Change of physical database schemas without change of conceptual database schemas or application programs.

- Logical Data Independence

Change of conceptual schemas without change of external views.

## Computer Languages
- Data Definition Language (DDL)

Schemas

- Data Manipulation Language (DML)

Retrieval, update of data

## People deal with database

Database Administrator's tasks:

- Schema definition/modification
- Storage structure deifinition/modification
- Authorization of data access
- Integrity constraint specification
- Monitoring performance
- Responding to changes in requirements





