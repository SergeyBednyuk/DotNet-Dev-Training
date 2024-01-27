# Operations Queue

## Short Description

Create stored procedures to work with Operations Queue.

## Estimation (h)

6

## Topics

* Database project
* Transactions
* Locking

## Requirements

Use transaction to get operation and update status. Only one operation can be in InProgress state.
SP can be executed by multiple threads at the same time.
Add appropriate indexes to cover filters, i.e. to avoid index scans.
Test on a large amount of records(for example on 100k).

Create the following table:

```sql
    CREATE TABLE [dbo].[OperationQueue]
    (
        [OperationId] INT PRIMARY KEY IDENTITY NOT NULL,
        [Status] INT NOT NULL, -- 0 - Pending, 1 - InProgress, 2 - Completed
        [CreatedDate] DATETIME NOT NULL,
        [ModifiedDate] DATETIME NULL
    )
```

Create stored procedures:

* AddOperation (no parameters)
* CompleteOperation (accepts OperationId)
* TryGetNextOperation (no parameters, returns next operation from the OperationQueue and sets its state to InProgress)

The result should be a Database project with sql files to create table and stored procedures.
