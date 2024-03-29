# Lesson 1
考核安排：
40% assignments and experiments + 60% examination

## Introduction 简介

### What is database

- a **collection** of data.

- a database can be of **any size** and of **varying complexity**.

## Schema and Instance 模式与实例

- a **schema** is definition of a database. It defines the meaning of data. 数据库的总体设计被称为**模式**。

- an **instance** of a database is the collection of data in the database at a particular point of time. 特定时刻存储在数据库中的信息的集合被称作数据库的一个**实例**。

## Database Management System (DBMS) 数据库管理系统

 A DBMS is a collection of software programs to enable users to create, maintain and utilize a database.

 数据库管理系统由一个互相关联的数据的集合和一组用以访问这些数据的程序组成。这个数据集合通常称为**数据库**。DBMS的基本目标是要提供一个可以**方便地、有效地**存取数据库信息的环境。

 - Insert records 插入记录
 - Delete records 删除记录
 - Update records 更新记录
 - Query records 查询记录

> neo4j is a graph database

### Drawback of File System 文件处理系统的弊端

1. Data Redundancy and Inconsistency 数据的冗余和不一致

2. Difficulty in accessing data 数据访问困难

3. Integrity problems (Constraints) 完整性问题（一致性约束）

4. Atomicity (原子性) of updates 原子性问题

5. Concurrent Access by multiple users 并发访问异常

6. Security problems 安全性问题

### Advantage of DBMS 数据库管理系统的优势

- Data independence 数据独立
- Efficient data access 有效的数据访问
- Data integrity and security 数据一致性与安全性
- Data administration 数据管理员
- Concurrent access and crash recovery 并发访问与冲突恢复

Overall: Reduced application development time.

***

## Data Models 数据模型

A data model is a collection of tools or concepts for describing data, the meaning of data, data relationships and data constraints. A data model provides a way to describe the design of a database at the physical, logical, and view levels.


数据库结构的基础是**数据模型**。数据模型是一个描述数据、数据联系、数据语义以及一致性约束的概念工具的集合。为了阐明数据模型的概念，在这部分主要涉及两种数据模型：实体-联系模型与关系模型。

- Object-based Logical Models 基于对象的逻辑模型

- Record-based Logical Models 基于记录的逻辑模型

### Entity- Relationship Model (ER Model) 实体-联系模型

The entity-relationship (E-R) data model uses a collection of basic objects, called entities, and relationships among these objects. An entity is a “thing” or “object” in the real world that is distinguishable from other objects. The entity-relationship model is widely used in database design.

E-R数据模型基于对现实世界的这样一种认识：现实世界由一组称为**实体**的基本对象以及这些对象间的**联系**构成。实体是现实世界中可区别于其他对象的一个“事件”或一个“物体”。

数据库中实体通过**属性集合**来描述。

**联系**是实体间的相互关系。同一类型的所有实体的集合称为**实体集**，同一类型的所有联系的集合称为**联系集**。

数据库的总体逻辑结构（模式）可以用**E-R图**进行图形表示，E-R图由以下元素构成：

- **矩形**，代表实体集。
- **椭圆**，代表属性。
- **菱形**，代表实体集间的联系。
- **线段**，将属性于实体集相连或将实体集与联系相连。

### Relation Model 关系模型

Main concept: **relation** ,basically a table with rows and columns. A column is also called a **field** or **attribute**.

The relational model uses a collection of tables to represent both data and the relationships among those data. Each table has multiple columns, and each column has a unique name. Tables are also known as **relations**. The relational model is an example of a record-based model.

Record-based models are so named because the database is structured in fixed-format records of several types. Each table contains records of a particular type. Each record type defines a fixed number of **fields(字段)**, or **attributes(属性)**. The columns of the table correspond to the attributes of the record type. The relational data model is the most widely used data model, and a vast majority of current database systems are based on the relational model.

关系模型用表的集合来表示数据和数据间的联系。每个表有多个列，每列有唯一的列名。关系模型是基于记录模型的一种。基于记录模型的名称由来是由于它使用了一些固定格式的记录来描述数据库结构。每张表包含某种特定类型的记录，每个记录类型定义了固定数目的字段或属性。表格的列对应于记录类型的属性。关系数据模型是使用最广泛的数据模型。

Other models such as the Network Model, Hierarchical Model, object-oriented model,objected-relational model.

## View of Data 数据视图

### Data Abstraction 数据抽象

#### Physical level 物理层

How and where data are actually stored, low level data structures are specified at this level.

抽象的最低层次，描述数据实际上是**怎样**存储的。物理层详细描述复杂的低层数据结构。

#### Conceptual level (Logical level) 逻辑层

Describes what data should be stored in the database, and relationship and semantics of the data.

比物理层稍高的抽象层次，描述数据库中存储**什么**数据以及这些数据间存在什么关系。这样，逻辑层就通过少量相对简单的结构描述了整个数据库。虽然简单的逻辑层结构的实现涉及到复杂的物理层结构，但逻辑层的用户不必知道这样的复杂性。逻辑层抽象是被数据库管理员所使用的，管理员必须确定数据库中应该保存哪些信息。

#### View level 视图层

Relevant partial view of the database to be particular type of users.

抽象的最高层次，只描述整个数据库的某个部分。尽管在逻辑层使用了比较简单的结构，但由于数据库的规模巨大，因此仍存在一定程度的复杂性。数据库系统的很多用户并不需要关心所有的信息，而只需要访问数据库的一部分。视图层抽象的定义正是为了使这样的用户与系统的交互更简单。系统可以为同一数据库提供多个视图。

## Data Independence 数据独立

- Physical Data Independence 物理模式

Change of physical database schemas without change of conceptual database schemas or application programs.

物理模式在物理层描述了数据库的设计。

- Logical Data Independence 逻辑模式

Change of conceptual schemas without change of external views.

逻辑模式在逻辑层描述数据库的设计。

## Database Languages 数据库语言

### Data Definition Language (DDL) 数据定义语言

We specify a database schema by a set of definitions expressed by a special language called a **data-definition language (DDL)**. The DDL is also used to specify additional properties of the data.

我们通过一组定义来指定数据库模式，这些定义是由一种称为数据定义语言(DDL)的特殊语言表示的。DDL还用于指定数据的其他属性。

We specify the storage structure and access methods used by the database system by a set of statements in a special type of DDL called a **data storage and definition** language. These statements define the implementation details of the database schemas, which are usually hidden from the users.
The data values stored in the database must satisfy certain **consistency constraints**. For example, suppose the university requires that the account balance of a department must never be negative. The DDL provides facilities to specify such constraints. The database system checks these constraints every time the database is updated. In general, a constraint can be an arbitrary predicate pertaining to the database. However, arbitrary predicates may be costly to test. Thus, database systems implement integrity constraints that can be tested with minimal overhead:
- **Domain Constraints**. A domain of possible values must be associated with every attribute (for example, integer types, character types, date/time types). Declaring an attribute to be of a particular domain acts as a constraint on the values that it can take. Domain constraints are the most elementary form of integrity constraint. They are tested easily by the system whenever a new data item is entered into the database.
- **Referential Integrity**. There are cases where we wish to ensure that a value that appears in one relation for a given set of attributes also appears in a certain set of attributes in another relation (referential integrity). For example, the department listed for each course must be one that actually exists. More precisely, the dept name value in a course record must appear in the dept name attribute of some record of the department relation. Database modifications can cause violations of referential integrity. When a referential-integrity constraint is violated, the normal procedure is to reject the action that caused the violation.
- **Assertions**. An assertion is any condition that the database must always satisfy. Domain constraints and referential-integrity constraints are special forms of assertions. However, there are many constraints that we cannot express by using only these special forms. For example, “Every department must have at least five courses offered every semester” must be expressed as an assertion. When an assertion is created, the system tests it for validity. If the assertion is valid, then any future modification to the database is allowed only if it does not cause that assertion to be violated.
- **Authorization**. We may want to differentiate among the users as far as the type of access they are permitted on various data values in the database. These differentiations are expressed in terms of authorization, the most common being: read authorization, which allows reading, but not modification, of data; insert authorization, which allows insertion of new data, but not modification of existing data; update authorization, which allows modification, but not deletion, of data; and delete authorization, which allows deletion of data. We may assign the user all, none, or a combination of these types of authorization.

我们在一种称为**数据存储和定义**语言的特殊类型的DDL中通过一组语句指定数据库系统使用的存储结构和访问方法。这些语句定义了数据库模式的实现细节，这些细节通常对用户隐藏。

存储在数据库中的数据值必须满足一定的**一致性约束**。例如，假设大学要求一个部门的帐户余额决不能为负。DDL提供了指定此类约束的工具。每次更新数据库时，数据库系统都会检查这些约束。通常，约束可以是属于数据库的任意谓词。然而，任意谓词的测试成本可能很高。因此，数据库系统实现了可以以最小开销进行测试的完整性约束:

- **域约束**。可能值的域必须与每个属性相关联(例如，整数类型、字符类型、日期/时间类型)。将属性声明为特定的域，就像约束它可以接受的值一样。域约束是完整性约束的最基本形式。每当有新的数据项输入数据库时，系统就可以很容易地对它们进行测试。

- **引用完整性**。在某些情况下，我们希望确保出现在给定属性集的一个关系中的值也出现在另一个关系中的特定属性集中(引用完整性)。例如，为每门课程列出的系必须是实际存在的系。更准确地说，课程记录中的部门名值必须出现在部门关系的某些记录的部门名属性中。数据库修改可能会导致违反引用完整性。当引用完整性约束被违反时，通常的程序是拒绝导致违反的操作。

- **断言**。断言是数据库必须始终满足的任何条件。域约束和引用完整性约束是断言的特殊形式。然而，有许多限制条件我们不能仅通过使用这些特殊形式来表达。例如，“每个系每学期必须提供至少五门课程”必须表示为断言。创建断言时，系统会测试它的有效性。如果断言有效，则只有在不违反断言的情况下，才允许对数据库进行任何修改。

- **授权**。我们可能希望根据允许用户访问数据库中各种数据值的类型来区分不同的用户。这些区别在授权方面表示，最常见的是:读取授权，允许读取数据，但不允许修改数据;插入授权，允许插入新数据，但不允许修改现有数据;更新授权，允许修改数据，但不允许删除数据;以及删除授权，允许删除数据。我们可以为用户分配全部授权、不授权或这些类型的组合。

### Data Manipulation Language (DML) 数据操纵语言

A **data-manipulation language (DML)** is a language that enables users to access or manipulate data as organized by the appropriate data model. The types of access are:

- Retrieval of information stored in the database
- Insertion of new information into the database
- Deletion of information from the database
- Modification of information stored in the database

There are basically two types:
- **Procedural DMLs** require a user to specify what data are needed and how to get those data.
- **Declarative DMLs** (also referred to as **nonprocedural DMLs**) require a user to specify what data are needed without specifying how to get those data.

Declarative DMLs are usually easier to learn and use than are procedural DMLs. However, since a user does not have to specify how to get the data, the database system has to figure out an efficient means of accessing data.
A **query** is a statement requesting the retrieval of information. The portion of a DML that involves information retrieval is called a **query language**. Although technically incorrect, it is common practice to use the terms query language and data-manipulation language synonymously.

数据操作语言(DML)是一种允许用户访问或操作由适当的数据模型组织的数据的语言。访问类型包括:

- 检索存储在数据库中的信息
- 将新信息插入数据库
- 从数据库删除信息
- 修改存储在数据库中的信息

基本上有两种类型:

- **过程型DML**要求用户指定需要什么数据以及如何获取这些数据。

- **声明性DML**(也称为**非过程性DML**)要求用户指定需要哪些数据，而不指定如何获取这些数据。

声明式DML通常比过程式DML更容易学习和使用。然而，由于用户不必指定如何获取数据，数据库系统必须找出访问数据的有效方法。

**查询**是请求检索信息的语句。DML中涉及信息检索的部分称为**查询语言**。尽管技术上不正确，但通常将术语查询语言和数据操作语言作为同义词使用。

## People deal with database 数据库用户和管理员

Database Administrator's tasks:

- Schema definition/modification 模式定义
- Storage structure deifinition/modification 存储结构定义
- Authorization of data access 数据访问授权
- Integrity constraint specification 完整性约束规范
- Monitoring performance 监控性能
- Responding to changes in requirements 响应需求的变化





# Lesson 2

## Structure of DBMS

## History of DBMS

## ER Diagram ER图

### Entities and attributes 实体与属性

- An **entity** is an object in the real world that is distinguishable from other objects. **实体**是现实世界中可区别于其他对象的“事件”或“物体”。

- An **entity** is describe using a set of  **attributes** whose values are used to distinguish one entity from another of same type.

- An **entity set** is a collection of the entities of the same type. **实体集**是具有相同类型及共享相同性质（或属性）的实体集合。

- All entries in a given entity set have the same attributes (the values may be different).

### ER Diagram

数据库的总体逻辑结构（模式）可以用**E-R图**进行图形表示，E-R图由以下元素构成：

- **矩形**，代表实体集。
- **椭圆**，代表属性。
- **菱形**，代表实体集间的联系。
- **线段**，将属性于实体集相连或将实体集与联系相连。
- **箭头**，指出的一方为唯一关系。 

### Different attributes 属性的分类

#### Simple attributes 单值属性

- contains a single value 
对一个特定实体只有单独的一个值的属性。

> 正常的椭圆，没有再连接到其他椭圆上

#### Composite attribute 复合属性

- contains several components 
可以被划分为更小的部分。

> 正常的椭圆，由其本身又连接出很多具体的椭圆

#### Multi-valued attribute 多值属性

- contains more than one value 
一个属性对应一组值（例如一个人可以有多个电话号码）。

> Represented as double ovals 双椭圆

#### Derived attribute 派生属性

- Computed from other attributes 
这类属性的值可以从其他的相关属性或实体派生出来。

> Represented as dash line 虚线椭圆

### Key attributes 键属性

#### Key 键（码）

- A set of attributes that can **uniquely** identify an entity.
可以唯一标识特定实体的一组属性。
>Represented as underline 下划线

#### Composite Key 组合键

- Two or more attributes are used to serve as a key.
有两个或多个属性需要一起同时被用作键。

An entity may have more than one key.
一个实体可以有多于一个的键。

A **minimal** set of attributes that uniquely identifies an entity is called a **candidate key**.
唯一标识实体的**最小**属性集称为**候选键**。

> 实际上就是这个集合里面的所有的属性不能够被单独或者组合之后作为键。

If there are many candidate keys, we should choose one candidate key as the **primary key**.
如果有很多候选键，我们应该选择一个候选键作为**主键**。

Sometimes, **artificial keys** can be created. 
有时，可以创建人工键。

### Relationship 联系

- A **relationship** is an association among several entities.
**联系**是指多个实体之间的相互关联。

- The **degree** refers to the number of entity sets that participate in a relationship set.
参与联系集的实体集的数目被称为联系集的**度**。

- Relationship sets that involve two entity sets are **binary** (or degree two).
有两个实体集参与的联系集叫**二元集**。

#### Binary relationship 二元联系

- A relationship can also have attributes which are used to describe the record information about the **relationship** (instead of the information of each individual entity).
联系还可以具有用于描述关于**联系**的记录信息的属性(而不是每个单独实体的信息)。这样的属性被称为**描述性属性**。

#### Recursive relationship 递归联系

- Entity sets of a relationship need not be distinct.
联系的实体集是相同的。（实体集自己与自己的联系）

- Sometimes, a relationship might involve two entities in the same entity set.
有时，联系可能涉及同一实体集中的两个实体。

### Constraints 约束

- The model describes data to be stored and the **constraints** over the data.

- The mapping of a binary relationship can be classified into the following case:
[image1]

**映射基数**，或基数比例，指明通过一个联系集能同时与另一实体相联系的实体数目。

#### One-to-many relationship 多对一

- An entity in B can be associated with at most one entity in A.

#### Many-to-one relationship 一对多

#### Many-to-many relationship 多对多

- There is no restriction in the mapping.

#### One-to-one relationship 一对一

### Participation constraint 参与约束

#### Total 全部

- Each entity in the entity set must be associated in at least one relationship
如果实体集$E$中的每个实体都参与到联系集$R$的至少一个联系中，称实体集$E$**全部**参与联系集$R$。

> double line 双线

#### Partial 部分

- Each entity in the entity set may (or may not) be associated in a relationship.
如果实体集$E$中只有部分实体参与到联系集$R$的联系中，称实体集$E$**部分**参与联系集$R$。

### Weak/Strong entities 弱实体集与强实体集

#### Strong entity 强实体集

An entity can be uniquely identified by some attributes related to this entity.
有主键（primary key）的实体集称为**强实体集**。

#### Weak entity

An entity cannot be uniquely identified by all attributes related to this entity.
没有主键的实体集称为**弱实体集**。

- The set of attributes that uniquely identify a weak entity for a given owner entity is called a **discriminator** or **partial key**.
为给定所有者实体唯一标识弱实体的属性集称为**辨别符**或**部分键**。

- If a weak entity set $W$ is dependent on a strong entity set $E$, we say that $E$ **owns** $W$.
一个弱实体集必须与另一个称为**标识实体集（identifying entity set）**或**属主实体集**关联才有意义。每个弱实体必须与一个标识实体关联。

> 双矩形

### Class Hierarchy

Sometimes, it is natural to classify the entities in an entity set into subclasses.

- Attributes are **inherited** by the entity set in the subclass.

- A class hierarchy can be viewed in one of the two ways:
A class is specialized into subclasses.

The subclasses are generalized by a superclass.

#### Why class hierarchy?
- Add **descriptive attribute** that make sense only for the entities in a subclass.
- Identify the set of entities that participate in some relationships.

#### Overlap constraints

- Determine whether two subclasses are allowed to contain the same entity.

#### Covering constraints

- Determine whether the entities in the subclasses collectively include all entities in the superclass.

### Non-binary relationship

In general, and non-binary relationship can be represented using binary relationships by creating an artificial entity set.

#### Ternary relationship

- A relationship involving 3 entities.



# Lesson 3

## Steps in Relational Model Analysis

1. Strong entity
    - Create the relation schemas
    - If there is a derived attribute: Include this derived attribute or not include this derived attribute. (Might cause data inconsistencies)
    - If there is composite attribute: Include the high-level attribute only or include all low-level attributes. (Reduce redundancy)
    - If there is a multi-valued attribute: Include one attribute only or create another table containing the primary key of the entity set and the multi-valued attribute.
2. Weak entity
    - For each weak entity set W in the ER model:
3. 1-to-1 Relationship
    - Include the primary key as **foreign key** and rename it.
4. 1-to-many Relationship
5. Many-to-many Relationship
    - Create a new table
6. Non-binary Relationship
    - Create a new relation schema S to represent R.
    - Include as foreign key attributes in S the primary keys of the participationg entity sets.
    - Also include any attributes of the non-binary relationship set as attributes of S.

## Translating Class Hierarchy

## Relational Algebra
 - Query languages are specialized languages for asking questions or queries, that involve the data in a database.
 - Queries in terms of operators.

 ### Basic Operators

 #### Projection $\Pi_L(R)$

 - Deletes attributes that are not in *projection list L*.
 - **Schema** of result contains exactly the fields in the projection list, with the same names that they had in the (only) input relation.
 - Projection operator eliminates ***duplicates***.

 #### Selection $\sigma_C(R)$

 - Select rows (records/tuples) that satisfy a *selection condition C*.
 - **Schema** of result identical to schema of (only) input relation.

#### Set Operations

- **Union($\cup$), Intersection($\cap$), Set-Difference($-$)**

#### Cartesian Product $\times$

#### Join $\Join$

- Natural join
Join is a cartesian product follow by a selection:
$$
R_1 \Join R_2=\sigma_{R_1.x = R_2.x}(R_1 \times R_2)
$$
