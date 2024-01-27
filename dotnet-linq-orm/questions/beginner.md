

# Beginner Level Questions

## Table of Contents

### LINQ

<details>
	<summary>1. What is LINQ?</summary>

> #### Answer:
> LINQ (Language Integrated Query) is uniform query syntax in C# and VB.NET to retrieve data from different sources and formats. It provides a single querying interface for different types of data sources. 

</details>

<details>
	<summary>2. What condition must a type meet so that we can write LINQ queries for it?</summary>

> #### Answer:
> We can write LINQ queries for the types that implement `IEnumerable<T>` or `IQueryable<T>` interface.

</details>

<details>
	<summary>3. What are types of LINQ query syntax?</summary>

> #### Answer:
> 1. Query Syntax or Query Expression Syntax
> 2. Method Syntax or Method Extension Syntax or Fluent

</details>

<details>
	<summary>4. What is Deferred Execution of LINQ Query? What benefits can be achived using it?</summary>

> #### Answer:
> 1. Deferred execution means that the evaluation of an expression (materialization and execution) is delayed until its realized value is actually required.
> 2. It greatly improves performance by avoiding unnecessary execution.

</details>

<details>
	<summary>5. What is Immediate Execution of LINQ Query? How can it be achived?</summary>

> #### Answer:
> 1. Immediate Execution forces the LINQ query to execute and gets the result immediately.
> 2. The 'To' conversion operators execute the given query and give the result immediately (`ToList`, `To Array`, `ToDictionary`, `ToLookup`). Aggregation operators  (`Count`, `Max`, ...), element operators (`Single`, `Last`, `FirstOrDefault`). Loop iterations.

</details>

<details>
<summary>6. What types of LINQ do you know?</summary>

>#### Answer:
>* LINQ to objects
>* LINQ to SQL(DLINQ)
>* LINQ to dataset
>* LINQ to XML(XLINQ)
>* LINQ to entities

</details>

<details>
<summary>7. What Third-party LINQ providers do you know?</summary>

>#### Answer:
>* DbLinq
>* LINQ to Excel
>* LINQ to JSON
>* LINQ to Amazon

</details>

<details>
<summary>8. List out the three main components of LINQ.</summary>

>#### Answer:
>* Standard Query Operators
>* Language Extensions
>* LINQ Providers

</details>

### Introduction to ORM

<details>
	<summary>1. What is ORM?</summary>

> #### Answer:
> Object-Relational Mapping is a technique that lets you query and manipulate data from a database using an object-oriented paradigm.

</details>

<details>
	<summary>2. What is micro ORM? What are differences from full ORMs?</summary>

> #### Answer:
> Micro ORMs are useful small ORMs that are lightweight and map between objects and database queries. They have better performance but usually don’t come with any powerful features like full ORMs do (change tracking, concurrency, caching, relationships, migrations).

</details>

<details>
	<summary>3. What full ORMs for .NET do you know?</summary>

> #### Answer:
> EF, EF Core, NHibernate.

</details>

<details>
	<summary>4. What micro ORMs do you know?</summary>

> #### Answer:
> Dapper.

</details>

<details>
<summary>5. When should you use an ORM?</summary>

>#### Answer:
>ORM is useful when you need to work with data stored in the database within your application.

</details>

<details>
<summary>6. Name advantages and disadvantages of using ORMs.</summary>

>#### Answer:
>Advantages:
>* It lets you treat data stored in a database like a usual object;
>* You don't have to write SQL;
>* You write your data model in only one place, and it's easier to update, maintain, and reuse the code;
>* The model is weakly bound to the rest of the application, so you can change it or use it anywhere else;
>* It lets you use OOP.
>
>Disadvantages:
>* You have to learn it, ORM libraries are not lightweight tools;
>* Performance. It's OK for simple queries, but you can have problems with more difficult tasks;
>* Sometimes treating database data like usual objects can affect performance negatively (e.g. a huge for loop).

</details>

### Database modelling with Code First (EF Core)

<details>
	<summary>1. What is EF?</summary>

> #### Answer:
> Entity Framework is an Object/Relational Mapping (ORM) framework. It is an enhancement to ADO.NET that gives developers an automated mechanism for accessing & storing the data in the database.

</details>

<details>
	<summary>2. What EF Core development approaches do you know?</summary>

> #### Answer:
> 1. Code-First
> 2. Database-First

</details>

<details>
	<summary>3. What are the ways of models configuration in EF Core?</summary>

> #### Answer:
> 1. Fluent API
> 2. Data Annotation Attributes

</details>

<details>
	<summary>4. What is the way of representing relationships between the database entities?</summary>

> #### Answer:
> Navigation properties.

</details>

<details>
<summary>5. What is the data seeding process?</summary>

>#### Answer:
> Data seeding is the process of populating a database with an initial set of data.

</details>

<details>
<summary>6. What are Generated Properties in EF Core? </summary>

>#### Answer:
>A property the value of which is generated either by Entity Framework or the database when the entity is added or updated is known as generated property

</details>

<details>
<summary>7. What are Data Annotations Attributes in EF core? </summary>

>#### Answer:
>Attributes are a kind of tag that you can place on a class or property to specify metadata about that class or property. Entity Framework Core makes use of attributes defined in the System.ComponentModel.DataAnnotations.Schema and System.ComponentModel.DataAnnotations namespaces.
>
```csharp
[MyClassAttribute]
public class MyClass
{
    [MyPropertyAttribute]
    public int MyProperty { get; set; }
    
    ...
}
```
>
>You can apply multiple attributes in one of two ways - separately:
>
```csharp
[MyFirstAttribute]
[MySecondAttribute]
[MyThirdAttribute]
public int MyProperty { get; set; }
...
```
>
>or as a comma-separated list:
>
```csharp
[MyFirstAttribute, MySecondAttribute, MyThirdAttribute]
public int MyProperty { get; set; }
...
```

</details>

<details>
<summary>8. What is Fluent API in EF core? </summary>

>#### Answer:
>EF Core Fluent API is an approach for configuring various aspects of your model(using provided methods) which is based on a Fluent API design pattern (a.k.a Fluent Interface) where the result is formulated by method chaining.

</details>

<details>

<summary>9. What are the advantages of using Data Annotation Attributes instead of Fluent API in EF Core?</summary>

>#### Answer:
>Each entity is configured separately, configuration is not separated from the model.

</details>

<summary>10. What are the advantages of using Fluent API in EF Core?</summary>

>#### Answer:
>Entity Framework Fluent API is used to configure domain classes to override conventions. EF Fluent API is based on a Fluent API design pattern (a.k.a Fluent Interface) where the result is formulated by method chaining.

>Entity Framework Core Fluent API configures the following aspects of a model:

>1) **Model Configuration**: Configures an EF model to database mappings. Configures the default Schema, DB functions, additional data annotation attributes and entities to be excluded from mapping;
>
>2) **Entity Configuration**: Configures entity to table and relationships mapping e.g. PrimaryKey, AlternateKey, Index, table name, one-to-one, one-to-many, many-to-many relationships etc;
>
>3) **Property Configuration**: Configures property to column mapping e.g. column name, default value, nullability, Foreignkey, data type, concurrency column etc.

</details>

### CRUD (EF Core)

<details>
<summary>1. What are Client evaluation commands in EF Core?</summary>

>#### Answer:
> Commands that cannot be converted into SQL, so therefore must be run in software in the application, known as the client.

</details>

<details>
<summary>2. What are Server evaluation commands in EF Core?</summary>

>#### Answer:
> Commands that can be converted into SQL commands and run on the database server.

</details>


<details>
	<summary>3. What are ways to query database?</summary>

> #### Answer:
> 1. LINQ.
> 2. Raw SQL queries.

</details>

<details>
	<summary>4. What are the types of loading related entities and what do they mean?</summary>

> #### Answer:

The difference between loading types is in how EF Core loads related entities from other tables.

For example, if class <code>Person</code> has property <code>Pet[] Pets</code>:

> 1. **Eager** loading means that related data from table Pets will be loaded only if you add a call to Include(x => x.Pets). Otherwise, the data from table Persons will be loaded, but property Pets will be null
> 2. **Explicit** loading means that the related data will be loaded when you explicitly request it in a separate query:
    - First, you get the required Person data: var person = dbContext.Persons.First();
    - Then, you load related data in a separate request via Entry API: var pets = dbContext.Entry(person).Collection(x => x.Pets).Load();
> 3. **Lazy** loading can be enabled when configuring dbContext. If it is enabled, all related data will be loaded automatically. This is not a recommended approach, because it will increase the response time and often load unnecessary data.

</details>

<details>
	<summary>5. How to perform CUD (create, update, delete) operation using EF Core?</summary>

> #### Answer:
> Methods of `DbSet` and `DbContext` (`Add`, `Remove`). Update properties of a model.

</details>

<details>
	<summary>6. How can you insert related entities of a newly created object into a database? For example, you have a <code>Blog</code> class object that you have just created and initialzied its navigation property <code>Posts</code> with the collection of objects.</summary>

> #### Answer:
> When you insert `Blog` class object its related `Post` entities will be automatically inserted into a database.

</details>

<details>
	<summary>7. What’s happening when you perform CUD operations using methods of <code>DbSet</code> or <code>DbContext</code>? Are updates reflected in a database?</summary>

> #### Answer:
> `DbContext` keeps track of updates, `EntityState` is updated. There is no updates in a database.

</details>

<details>
	<summary>8. When does EF Core perform actual updates in database?</summary>

> #### Answer:
> After calling the method `SaveChanges` of a `DbContext` object.

</details>

### Migrations

<details>
<summary>1. What is Database Migration?</summary>

>#### Answer:
> Database migration is management of incremental, reversible changes to relational database schemas. This is a complex, multiphase process, which usually includes assessment, database schema conversion (if you are changing engines), script conversion, data migration, functional testing, performance tuning, and many other steps. In the context of enterprise applications — Database migration means moving your data from one platform to another. 

</details>

<details>
<summary>2. What are the common reasons for database migration.</summary>

>#### Answer:
>
>1) Upgrading to the latest version of the database software to improve security and compliance;
>
>2) Moving existing data to a new database to reduce cost, improve performance, and achieve scalability;
>
>3) Moving from an on-premise database to a cloud-based database for better scalability and lower costs;
>
>4) Merge data from several databases into a single database for a unified data view post-merger.

</details>

<details>
<summary>3. How is database migration done in general?</summary>

>#### Answer:
>Database migration is a multiphase process that involves some or all the following steps:
>
>1) **Assessment** : At this stage, you'll need to gather business requirements, assess the costs and benefits, and perform data profiling. Data profiling is a process by which you get to know your existing data and database schema. You'll also need to plan how you will move the data — will you use an ETL (Extraction, Transformation, and Loading) tool, scripting, or some other tool to move the data?
>
>2) **Database schema conversion** : The schema is a blueprint of how the database is structured, and it varies based on the rules of a given database. When you move data from one system to another, you'll need to convert the schemas so that the structure of the data works with the new database;
>
>3) **Data migration** : After you have completed all the preliminary requirements, you'll need to actually move the data. This may involve scripting or using an ETL tool or some other tool to move the data. During the migration, you will likely transform the data, normalize data types, and check for errors;
>
>4) **Testing and tuning** : Once you've moved the data, you need to verify that the data was moved correctly, is complete, isn't missing values, doesn't contain null values, and is valid.

</details>

### Lighweight ORMs

<details>
<summary>1. Please describe, in which cases better using micro ORM (e.g. Dapper) instead of EF core?</summary>

>#### Answer: 
>* You need to excellent raw execution performance with minimal overheads;
>* You need to retain control over your SQL;
>* You don't need the object-tracking features of a full-weight ORM.

</details>