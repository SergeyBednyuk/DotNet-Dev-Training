# Microsoft SQL Server

## Version

2.0.1

## Introduction

After the course trainees are supposed to have theoretical knowledge and practical experience in Microsoft SQL Server.

## Table of Contents

* [Tasks](./tasks/readme.md)
* [Questions](./questions/readme.md)

## Topics

### Intermediate

* SQL Server Data Tools
  * Database Project
  * Dacpac
  * Backpac
* SQL Query Execution Plan
  * Table Scan
  * Index Scan
  * Index Seek
* Indexes
  * Clustered Index
  * NonClustered Index
  * Covering index
  * Filtered index
* Bulk Load Approaches
  * Basics
  * SqlBulkCopy
  * Table-Valued Parameter
  * Entity Framework Bulk Extension
  * XML
  * Comma Separated String
* SQL Server Extended Events
  * Basics
  * Capturing slow queries
  * Capturing Deadlocks
* Performance tuning
  * Missing indexes
  * SQL query performance optimization
  * N + 1
  * How to identify slow running queries
  * Parameter sniffing
  * Monitoring activities using sp_WhoIsActive
* Sequences
* Database Recovery Models
* MS SQL vs Azure SQL

### Advanced

* Lock Modes
* SqlBulkCopy
  * TableLock
* Partitions
  * Partition functions
  * Limitations
* Deadlocks
  * Deadlock graph
  * How to avoid deadlocks
* Indexes
  * SQL Server Index Architecture and Design Guide
  * Clustered ColumnStore index
  * Non-Clustered ColumnStore index
  * Performance comparison ColumnStore vs RowStore
  * Heap
  * Fragmentation
* Query Hints
* SQL Server Wait Types
* SQL Server Administration
  * Replication
  * Always-On
* SQL Server 2016
  * Always encrypted
  * Row-Level security
  * Dynamic data masking
  * Json Support

## Prerequisites

### Technical

* Intermediate and advanced knowledge of databases principles.

### Environment

* Microsoft SQL Server Developer Edition
* SQL Server Management Studio
* Microsoft Visual Studio
  * SQL Server Data Tools

## Plan

| Name                                                                                                                                                            | Type          | Short Description                                             | Level        | Required | Estimation (h) |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------------------------------- | ------------ | -------- | -------------- |
| [SSDT Database Project](https://www.mssqltips.com/sqlservertutorial/9000/overview-of-ssdt-sql-project-tutorial/)                                                | article       | Database project overview                                     | intermediate | required | 4              |
| [Dacpac / Backpac](https://www.sqlshack.com/an-introduction-to-data-tier-applications-in-sql-server/)                                                           | article       | An introduction to Data-Tier applications                     | intermediate | required | 2              |
| [SQL Query Execution Plan](https://www.sqlshack.com/execution-plans-in-sql-server/)                                                                             | article       | Execution Plans in SQL Server                                 | intermediate | required | 2              |
| [Clustered Indexes](https://www.sqlshack.com/overview-of-sql-server-clustered-index/)                                                                           | article       | Clustered indexes overview                                    | intermediate | required | 3              |
| [Non-Clustered Indexes](https://www.sqlshack.com/overview-of-non-clustered-indexes-in-sql-server/)                                                              | article       | Non-clustered indexes overview                                | intermediate | required | 2              |
| [Covering Index](https://www.red-gate.com/simple-talk/sql/learn-sql-server/using-covering-indexes-to-improve-query-performance/)                                | article       | Using Covering Indexes to Improve Query Performance           | intermediate | required | 2              |
| [Filtered Index](https://www.red-gate.com/simple-talk/sql/performance/introduction-to-sql-server-filtered-indexes/)                                             | article       | Filtered Indexes overview                                     | intermediate | required | 1              |
| [Adventure Works Inexes](./tasks/adventure-works-indexes/readme.md)                                                                                             | task          | Adventure Works Inexes                                        | intermediate | required | 3              |
| [SqlBulkCopy](https://programmingwithmosh.com/net/using-sqlbulkcopy-for-fast-inserts/)                                                                          | article       | Using SqlBulkCopy for fast inserts                            | intermediate | required | 1              |
| [Table-Valued Parameter](https://www.sqlshack.com/table-valued-parameters-in-sql-server/)                                                                       | article       | Table-Valued Parameters in SQL Server                         | intermediate | required | 2              |
| [Entity Framework Bulk Extension](https://github.com/borisdj/EFCore.BulkExtensions)                                                                             | article       | Entity Framework extension for bulk operations                | intermediate | optional | 2              |
| [XML Parameter, Comma-separated string parameter](https://www.red-gate.com/simple-talk/blogs/using-xml-to-pass-lists-as-parameters-in-sql-server/)              | article       | Using XML to pass lists as parameters in SQL Server           | intermediate | optional | 2              |
| [Sql Server Profiler](https://www.mssqltips.com/sqlservertutorial/3500/introduction-to-sql-server-profiler/)                                                    | article       | Introduction to SQL Server Profiler(Deprecated)               | intermediate | optional | 3              |
| [Extended Events](https://www.mssqltips.com/sqlservertutorial/9194/sql-server-extended-events-tutorial/)                                                        | article       | SQL Server Extended Events Tutorial(Sql Profiler replacement) | intermediate | required | 4              |
| [Extended Event Session for Long Running Queries](https://www.mssqltips.com/sqlservertutorial/9212/sample-sql-server-extended-events-sessions-templates/)       | article       | Sample of extended event session for long running queries     | intermediate | required | 2              |
| [Capturing Deadlocks using Extended Events](https://www.mssqltips.com/sqlservertip/5658/capturing-sql-server-deadlocks-using-extended-events/)                  | article       | Using extended events to capture deadlocks                    | intermediate | required | 2              |
| [Extended Events](./tasks/extended-events/readme.md)                                                                                                            | task          | Create extended events sesstion to handle deadlock graph      | intermediate | required | 3              |
| [Missing Indexes](https://blog.sqlauthority.com/2011/01/03/sql-server-2008-missing-index-script-download/)                                                      | article       | Missing Index Script                                          | intermediate | required | 1              |
| [SQL query performance optimization](https://solutioncenter.apexsql.com/how-to-optimize-sql-server-query-performance/)                                          | article       | How to optimize SQL Server query performance                  | intermediate | required | 4              |
| [N+1](https://medium.com/@sakibnajmus030/n-1-selects-problem-in-orm-object-relational-mapping-and-what-laravel-offers-to-fix-it-2cb24e48373e)                   | article       | N+1 selects ORM problem overview                              | intermediate | optional | 1              |
| [Slow running queries in SQL Server](https://www.sqlshack.com/how-to-identify-slow-running-queries-in-sql-server/)                                              | article       | How to identify slow running queries in SQL Server            | intermediate | optional | 2              |
| [Parameter sniffing](https://blog.sqlauthority.com/2019/12/19/sql-server-parameter-sniffing-simplest-example/)                                                  | article       | Parameter Sniffing Simplest Example                           | intermediate | optional | 1              |
| [sp_WhoIsActive](https://www.sqlshack.com/monitoring-activities-using-sp_whoisactive-in-sql-server/)                                                            | article       | Monitoring activities using sp_WhoIsActive                    | intermediate | required | 1              |
| [Sequences](https://docs.microsoft.com/en-us/sql/t-sql/statements/create-sequence-transact-sql?view=sql-server-ver15)                                           | documentation | Sequences documentation                                       | intermediate | required | 1              |
| [Recovery models](https://www.sqlshack.com/understanding-database-recovery-models/)                                                                             | article       | SQL Server database recovery models overview                  | intermediate | required | 2              |
| [MS SQL vs Azure SQL](https://www.sqlshack.com/azure-sql-database-vs-sql-server-on-azure-vms/)                                                                  | article       | Comparison of Sql Server and Azure Sql                        | intermediate | optional | 2              |
| [Lock modes](https://www.sqlshack.com/locking-sql-server/)                                                                                                      | article       | Lock modes overview                                           | advanced     | required | 2              |
| [BulkCopy Lock Configuration](https://www.sqlshack.com/lock-configurations-with-sql-bulk-insert/)                                                               | article       | Lock Configurations with SQL Bulk Insert                      | advanced     | required | 1              |
| [Partitions](https://www.sqlshack.com/how-to-automate-table-partitioning-in-sql-server/)                                                                        | article       | Partitions in Sql Server                                      | advanced     | required | 2              |
| [Deadlock graph](https://www.sqlshack.com/understanding-graphical-representation-sql-server-deadlock-graph/)                                                    | article       | SQL Server Deadlock Graph graphical representation overview   | advanced     | required | 2              |
| [How to avoid deadlocks](https://basitaalishan.com/2012/06/04/tips-to-avoid-deadlocks/)                                                                         | article       | Usefull tips to avoid deadlocks                               | advanced     | required | 2              |
| [SQL Server Index Architecture and Design Guide](https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-index-design-guide?view=sql-server-ver15) | article       | SQL Server Index Architecture and Design Guide                | advanced     | required | 6              |
| [Index Fragmentation](https://www.mssqltips.com/sqlservertip/4331/sql-server-index-fragmentation-overview/)                                                     | article       | SQL Server Index Fragmentation Overview                       | advanced     | required | 2              |
| [Query Hints](https://docs.microsoft.com/en-us/sql/t-sql/queries/hints-transact-sql-query?view=sql-server-ver15)                                                | documentation | Query hints documentation                                     | advanced     | required | 2              |
| [Operations Queue](./tasks/operations-queue/readme.md)                                                                                                          | task          | Create operations queue                                       | advanced     | required | 6              |
| [Wait Stats with SQL Server Execution Plan](https://www.mssqltips.com/sqlservertip/5081/get-detailed-wait-stats-with-sql-server-execution-plan/)                | article       | Get Detailed Wait Stats with SQL Server Execution Plan        | advanced     | required | 3              |
| [Replication](https://www.sqlshack.com/sql-server-replication-overview-of-components-and-topography/)                                                           | article       | SQL Server replication overview                               | advanced     | optional | 2              |
| [Always-On](https://www.mssqltips.com/sqlservertip/4717/what-is-sql-server-alwayson/)                                                                           | article       | What is SQL Server AlwaysOn overview                          | advanced     | optional | 2              |
| [Always encrypted](https://www.red-gate.com/simple-talk/sql/database-administration/sql-server-encryption-always-encrypted/)                                    | article       | SQL Server Encryption: Always Encrypted                       | advanced     | optional | 2              |
| [Row-level security](https://www.sqlshack.com/introduction-to-row-level-security-in-sql-server/)                                                                | article       | Introduction to Row-Level Security in SQL Server              | advanced     | optional | 2              |
| [Json Support](https://www.sqlshack.com/native-json-support-in-sql-server-2016/)                                                                                | article       | Native JSON Support in SQL Server 2016                        | advanced     | required | 2              |
