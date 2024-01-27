# Adventure Works Inexes

## Short Description

Write sql queries to create indexes for the listed queries

## Estimation (h)

3

## Topics

* Indexes
  * Non-Clustered Index
  * Covering Index
  * Filtered Index

## Requirements

Download and restore backup of AdventureWorks2019 database (OLTP, [Adventure works](https://docs.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver15&tabs=ssms)).

* Create non-clustered index to cover the following query:

```sql
    DECLARE @inputTransactionDate DATETIME = '2013-09-09'

    SELECT *
    FROM [AdventureWorks2019].[Production].[TransactionHistory]
    WHERE TransactionDate > @inputTransactionDate
```

* Create non-clustered covering index to cover the following query:

```sql
    DECLARE @startDate DATETIME = '2013-01-01',
    @endDate DATETIME = '2013-12-31'

    SELECT TransactionType,
    COUNT(*) AS Count
    FROM [AdventureWorks2019].[Production].[TransactionHistory]
    WHERE TransactionDate BETWEEN @startDate AND @endDate
    GROUP BY TransactionType
```

* Create filtered index to cover the following query:

```sql
    SELECT *
    FROM [AdventureWorks2019].[Person].[Person]
    WHERE Title = 'Mr.'
```

The result should be a sql file with requests and comments for each request that it does.
