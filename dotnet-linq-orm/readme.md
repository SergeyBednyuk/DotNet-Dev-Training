# .NET LINQ and ORM

## Version

2.0.0

## Introduction

After this course you will be able to create .NET applications that work with
data stored in database using ORM. You will get familiar with LINQ and will learn
how to use it for manipulating data.

## Table of Contents

* [Theory](./theory/readme.md)
* [Tasks](./tasks/readme.md)
* [Questions](./questions/readme.md)

## Topics

### Beginner

* LINQ
  * What is LINQ
  * When you should use LINQ
  * Understanding of main working concepts
  * Types of LINQ
* Introduction to ORM
  * What is ORM
  * When and why ORMs can be useful
  * Known ORMs surface overview
  * What is Entity Framework Core
  * When you should use Entity Framework Core
* Database modelling with Code First (EF Core)
  * DbContext, DbSet
  * Development approaches supported in Entity Framework Core
  * Ways of configuring entities, their properties and relations
  * Navigation properties
  * Relations between entities
* CRUD (EF Core)
  * Select, Insert, Update, and Delete operations
  * Batch operations (Insert, Update, Delete)
* Migrations
  * What is Database Migration
  * When you should use a Database Migration
  * Risks, benefits and challenges
  * How to perform a database migration
* Lighweight ORMs
  * Dapper
    * What is Dapper
    * When and why it can be useful to use Dapper
  * Marten
    * What is Marten
    * When and why it can be useful to use Marten

### Intermediate

* LINQ
  * IQueryable, Expression and query translation
  * Differences between IQueryable\<T\> and IEnumerable\<T\>
  * LINQ and generic types
  * Query syntax and Lambda syntax
  * Advantages of LINQ
  * Anonymous types in LINQ
  * Lazy evaluation
  * Eager evaluation
  * Immediate execution
  * Deferred execution
* Introduction to ORM
  * How ORMs can be differentiated
  * Pros and Cons of using ORMs in general
  * Advanages/disadwantages popular ORMs comparing with each other. e.g. Entity Framework vs NHibernate
* Database modelling with Code First (EF Core)
  * Fluent API
  * Data Annotations
  * Data seeding
  * Shadow Properties
  * Inheritance
* CRUD (EF Core)
  * Server-side and client-side evaluation
  * Change Tracker
  * Disconnected Entity Graphs
  * Tracking Entity Graph
  * Saving Data in Connected Scenario
  * Saving Data in Disconnected Scenario
  * Loading Related Data
* Migrations
  * Migration in Entity Framework Core
  * Package Manager Console Commands for Migrations
  * Command Line Interface Commands for Migrations

### Advanced

* LINQ
  * How LINQ works
  * LINQ Architecture in .NET
  * Difference between LINQ and Stored Procedure
  * Types of operators
  * Iterator methods (yield)
  * LINQ Third-party providers
* CRUD (EF Core)
  * No-tracking queries
  * Cascade Delete
  * Concurrency control
* Lighweight ORMs
  * Dapper
    * Understanding and practical experience of how to use Dapper
  * Marten
    * Understanding and practical experience of how to use Marten

## Prerequisites

### Technical

* C#
* .NET

### Environment

* Visual Studio Code/Visual Studio
* .NET Core SDK

## Plan

| Name                                                                                                                                                                       | Type          | Short Description                                                                                              | Level        | Required | Estimation (h) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|----------------------------------------------------------------------------------------------------------------|--------------|----------|----------------|
| [LINQ: Overview](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/index)                                                                     | documentation | Read documentation explaining LINQ concepts                                                                    | beginner     | Yes      | 8              |
| [LINQ: Query and Method syntax](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq)                     | documentation | Read documentation explaining Query Syntax and Method Syntax in LINQ                                           | beginner     | Yes      | 1              |
| [LINQ: Query Operators](https://www.tutorialspoint.com/linq/linq_query_operators.htm)                                                                                      | article       | Read an article describing LINQ operators and their categorizations                                            | beginner     | Yes      | 2              |
| [LINQ: providers, anonymous types, grouping and sorting](https://www.ict.social/csharp/collections-and-linq/linq-providers-anonymous-types-grouping-and-sorting-in-csharp) | article       | Read an article to learn more about LINQ grouping, sorting and connection with anonimous types                 | intermediate | Yes      | 1              |
| [LINQ: execution types](https://dotnettutorials.net/lesson/deferred-execution-vs-immediate-execution-in-linq/)                                                             | article       | Read an article to understand differences between Deferred and Immediate execution in LINQ                     | intermediate | Yes      | 1              |
| [IQueryable VS IEnumerable](https://stackoverflow.com/questions/252785/what-is-the-difference-between-iqueryablet-and-ienumerablet)                                        | article       | Read an article which explaining the differences between IQueryable\<T\> and IEnumerable\<T\>                  | intermediate | Yes      | 1              |
| [Iterators in C# and LINQ](https://www.codeproject.com/Tips/359873/Csharp-Iterator-Pattern-demystified)                                                                    | article       | Read an article that explaining Iterator Pattern and how it connected with LINQ                                | intermediate | No       | 2              |
| [What is ORM?](https://stackoverflow.com/questions/1279613/what-is-an-orm-and-where-can-i-learn-more-about-it/1279678#1279678)                                             | article       | Read an article explaining ORM concept                                                                         | beginner     | Yes      | 1              |
| [ORM introduction and base concepts](https://www.youtube.com/watch?v=dHQ-I7kr_SY)                                                                                          | video         | Watch the video to get acquainted with the main concepts of ORMs                                               | beginner     | Yes      | 1              |
| [EF Core: Documentation](https://docs.microsoft.com/en-us/ef/core/)                                                                                                        | documentation | Read Entity Framework Core overview                                                                            | beginner     | Yes      | 3              |
| [EF Core: Shadow properties](https://www.entityframeworktutorial.net/efcore/shadow-property.aspx/)                                                                         | tutorial      | Read a tutorial describing Entity Framework Core shadow properties                                             | intermediate | No       | 2              |
| [EF Core: Table Per Hierarchy Inheritance](https://www.learnentityframeworkcore.com/inheritance/table-per-hierarchy)                                                       | documentation | Read documentation explaining how Table Per Hierarchy Inheritance work in Entity Framework Core                | intermediate | Yes      | 2              |
| [EF Core: Data Annotations Attributes](https://www.learnentityframeworkcore.com/configuration/data-annotation-attributes)                                                  | documentation | Read documentation explaining Data Annotations Attributes Configuration in Entity Framework Core               | intermediate | Yes      | 3              |
| [EF Core: Fluent API Configuration](https://www.learnentityframeworkcore.com/configuration/fluent-api)                                                                     | documentation | Read documentation explaining Fluent API Configuration in Entity Framework Core                                | intermediate | Yes      | 3              |
| [EF Core: Client vs. Server evaluation](https://www.thereformedprogrammer.net/entity-framework-core-client-vs-server-evaluation/)                                          | article       | Read an article to understand Client and Server evaluation concepts in Entity Framework Core                   | intermediate | Yes      | 3              |
| [EF Core: ChangeTracker](https://www.entityframeworktutorial.net/efcore/changetracker-in-ef-core.aspx)                                                                     | tutorial      | Read a tutorial to learn about ChangeTracker class and it's role in Entity Framework Core                      | intermediate | Yes      | 1              |
| [EF Core: Disconnected Entity Graph](https://www.entityframeworktutorial.net/efcore/working-with-disconnected-entity-graph-ef-core.aspx)                                   | tutorial      | Read a tutorial explains how to work with Disconnected Entity Graph in Entity Framework Core                   | advanced     | No       | 2              |
| [What Is Database Migration?](https://dzone.com/articles/what-is-database-migration)                                                                                       | tutorial      | Read a tutorial to get an understanding of migration process steps                                             | beginner     | No       | 1              |
| [Migrations in Entity Framework Core](https://www.entityframeworktutorial.net/efcore/entity-framework-core-migration.aspx)                                                 | tutorial      | Read a tutorial to learn about migrations in Entity Framework Core                                             | beginner     | Yes      | 2              |
| [Package Manager Console Commands for Migrations in EF Core](https://www.entityframeworktutorial.net/efcore/pmc-commands-for-ef-core-migration.aspx)                       | tutorial      | Read a tutorial to be familiar with package manager console commands for Entity Framework Core Migrations      | intermediate | No       | 2              |
| [Command Line Interface Commands for Migrations in EF Core](https://www.entityframeworktutorial.net/efcore/cli-commands-for-ef-core-migration.aspx)                        | tutorial      | Read a tutorial to be familiar with command line interface commands for Entity Framework Core Migrations       | intermediate | 2        | 2              |
| [Marten documentation](https://martendb.io/documentation/)                                                                                                                 | documentation | Read Marten documentation sections you are interested in                                                       | intermediate | No       | 6              |
| [Dapper documentation](https://github.com/StackExchange/Dapper)                                                                                                            | documentation | Read Dapper documentation                                                                                      | intermediate | Yes      | 2              |
| [Money Manager](./tasks/money-manager/readme.md)                                                                                                                           | task          | Create a data access level and execute database commands and queries using a DB-scheme and code-first approach | beginner     | Yes      | 12             |
| [ShareMe](./tasks/share-me/readme.md)                                                                                                                                      | task          | Implement database schema and data access layer by the provided application thumbnails.                        | beginner     | Yes      | 16             |
| [Marten Crud](./tasks/martendb-crud/readme.md)                                                                                                                             | task          | Implement database and data access layer.                                                                      | intermediate | No       | 16             |

## Additional Materials

* [LINQ Basics tutorial](https://dotnettutorials.net/lesson/introduction-to-linq/)
* [LINQ tutorial](https://www.tutorialsteacher.com/linq/linq-tutorials)
* [Entity Framework Core Tutorial](https://www.entityframeworktutorial.net/efcore/entity-framework-core.aspx)
* [Entity Framework Core documentation made by ZZZ Projects & .NET Community](https://entityframeworkcore.com/)
