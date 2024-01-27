# Questions

## Intermediate

### SQL Query Execution Plan

<details>
<summary>1. What is the difference between table scan and index seek?</summary>

>### Answer:
>Index seek is much faster. It uses binary tree search to find the data.
>Table scan is slow because it iterates through all the data.
</details> 

### Indexes

<details>
<summary>1. What are the benefits of filtered index?</summary>

>### Answer:
>It has much less amount of data to cover a particular query filter.
</details> 

### Bulk Load Approaches

<details>
<summary>1. How to efficiently load a set of records?</summary>

>### Answer:
> There are multiple approaches: BulkCopy, Stored procedure with Table-Valued, XML, or comma-separated string parameters.
</details>  


### Performance tuning

<details>
<summary>1. How to find missing indexes for a particular query?</summary>

>### Answer:
>To find a missing index we need to analyze the Query Execution Plan. Usually SQL Servers suggest adding an index. We must avoid table scans and index scans by creating index by fields which are used to join another table and in where clause.
</details>

<details>
<summary>2. How to find what is blocking a particular query?</summary>

>### Answer:
>We can use sp_who2 stored procedure with appropriate filters to find session and query which blocks our particular session/query.
</details> 

### Database Recovery Models

<details>
<summary>1. What is the difference between Simple and Full recovery models?</summary>

>### Answer:
>Simple recovery model will not store all the transactions in logs. It will disallow to recover the database to any point of time, but it will increase performance.
</details> 


### Advanced

### Lock Modes

<details>
<summary>1. Why table lock is used in Bulk Copying? How to avoid table lock for queries?</summary>

>### Answer:
>SQL server optimizer decides to put table lock on a table based on a number of rows which are affected by a particular query. If a query inserts more than 5000 rows then the table will be locked. Usually it gives performance benefits in systems with concurrent rows.

</details>  

### Deadlocks

<details>
<summary>1. How to prevent deadlocks?</summary>

>### Answer:
>The most important points are:
> 1. Use the same order to access data for the table for all the queries.
> 2. Transactions must be short and fast.

</details>  

### Indexes

<details>
<summary>3. When column-store indexes should be used?</summary>

>### Answer:
>>Column-store indexes should be used for large tables with large insert and select operations.

</details>  
