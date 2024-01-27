# Exam questions

## Principles

<details>
<summary>1. What ACID-transaction is?</summary>

> **Answer:**
>In the context of databases, a sequence of database operations that satisfies the ACID properties (and these can be perceived as a single logical operation on the data) is called a transaction.
>* `Atomicity` guarantees that each transaction is treated as a single "unit", which either succeeds completely, or fails completely: if any of the statements constituting a transaction fails to complete, the entire transaction fails and the database is left unchanged. An atomic system must guarantee atomicity in each and every situation, including power failures, errors and crashes.
>* `Consistency` ensures that a transaction can only bring the database from one valid state to another, maintaining database invariants: any data written to the database must be valid according to all defined rules. This prevents database corruption by an illegal transaction, but does not guarantee that a transaction is correct. 
>* `Isolation` ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially. Isolation is the main goal of concurrency control; depending on the method used, the effects of an incomplete transaction might not even be visible to other transactions.
>* `Durability` guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure (e.g., power outage or crash). This usually means that completed transactions (or their effects) are recorded in non-volatile memory.

</details>

<details>
<summary>2. Could you explain CAP theorem?</summary>

> **Answer:**
>CAP Theorem is a concept that a distributed database system can only have 2 of the 3: Consistency, Availability and Partition Tolerance
>
>* Consistency: Every read receives the most recent write or an error
>* Availability: Every request receives a (non-error) response – without the guarantee that it contains the most recent write
>* Partition tolerance: The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes

</details>

<details>
<summary>3. Could you explain PACELC theorem?</summary>

> **Answer:**
>In a system that replicates data:
>
>* If there is a partition (P), how does the system trade off availability and consistency (A and C)
>* else (E), when the system is running normally in the absence of partitions, how does the system trade off latency (L) and consistency (C)?
>
>The whole thesis is assuming we maintain high availability by replication. So when there is failure, CAP theorem prevails. But if not, we still have to consider the tradeoff between consistency and latency of a replicated system.

</details>

<details>
<summary>4. Could you explain BASE?</summary>

> **Answer:**
>* Basically available: This constraint states that the system does guarantee the availability of the data as regards CAP Theorem; there will be a response to any request. But, that response could still be ‘failure’ to obtain the requested data or the data may be in an inconsistent or changing state, much like waiting for a check to clear in your bank account.
>* Soft-state: The state of the system could change over time, so even during times without input there may be changes going on due to ‘eventual consistency,’ thus the state of the system is always ‘soft.’
>* Eventual consistency: The system will eventually become consistent once it stops receiving input. The data will propagate to everywhere it should sooner or later, but the system will continue to receive input and is not checking the consistency of every transaction before it moves onto the next one.
>
>Rather than requiring consistency after every transaction, it is enough for the database to eventually be in a consistent state. (Accounting systems do this all the time. It’s called “closing out the books.”) It’s OK to use stale data, and it’s OK to give approximate answers.

</details>

## Basic of database

<details>
<summary>5. Which layers does a database consist of?</summary>

> **Answer:**
>* `data access` which should be convenient to be used from a programming language.
>* `storage or keeping` How data is kept in RAM.
>* `equipment` A layer where data is stored on a disk.

</details>

<details>
<summary>6. What the main advantage do transactions provide?</summary>

> **Answer:**
> Transactions allow performing operations concurrently saving data consistency.

</details>

<details>
<summary>7. What write-ahead log is?</summary>

> **Answer:**
>In computer science, write-ahead logging (WAL) is a family of techniques for providing atomicity and durability (two of the ACID properties) in database systems. The changes are first recorded in the log, which must be written to stable storage, before the changes are written to the database.
>In a system using WAL, all modifications are written to a log before they are applied. Usually both redo and undo information is stored in the log.

</details>

## Database types 

<details>
<summary>8. What is used in relational databases to represent relations?</summary>

> **Answer:**
>Ids.

</details>

<details>
<summary>9. Enumerate types of relations?</summary>

> **Answer:**
>One to One, One to Many, Many to Many.

</details>

<details>
<summary>10. Enumerate base Redis types?</summary>

> **Answer:**
>Binary-safe strings, Lists, Sets, Sorted sets, Hashes

</details>

<details>
<summary>11. Provide some usecases for key-value databases?</summary>

> **Answer:**
>Session information, Cache, User profiles

</details>

<details>
<summary>12. Can you store documents with different schemas in the same collection in a document-oriented database?</summary>

> **Answer:**
>Yes

</details>

<details>
<summary>13. Do document-oriented databases have foreign keys?</summary>

> **Answer:**
>As a rule, no

</details>

<details>
<summary>14. Can you compare document-oriented databases and relational databases from scaling perspective?</summary>

> **Answer:**
>Document-oriented databases are more suitable for horizontal scaling.

</details>

<details>
<summary>15. Explain the main idea of column databases?</summary>

> **Answer:**
>Columns store databases use a concept called a keyspace. A keyspace is kind of like a schema in the relational model. The keyspace contains all the column families (kind of like tables in the relational model), which contain rows, which contain columns.
>
>A column family consists of multiple rows. Each row can contain a different number of columns to the other rows. And the columns don’t have to match the columns in the other rows.
>Each column is contained to its row. It doesn’t span all rows like in a relational database. Each column contains a name/value pair, along with a timestamp. 

</details>

<details>
<summary>16. Enumerate some benefits of column databases?</summary>

> **Answer:**
>Some key benefits of columnar databases include:
>
>* Compression. Column stores are very efficient at data compression and/or partitioning.
>* Aggregation queries. Due to their structure, columnar databases perform particularly well with aggregation queries (such as SUM, COUNT, AVG, etc).
>* Scalability. Columnar databases are very scalable. They are well suited to massively parallel processing (MPP), which involves having data spread across a large cluster of machines – often thousands of machines.
>* Fast to load and query. Columnar stores can be loaded extremely fast. A billion row table could be loaded within a few seconds. You can start querying and analysing almost immediately.

</details>

<details>
<summary>17. What parts do graph databases consist of?</summary>

> **Answer:**
>Nodes, relations.

</details>

<details>
<summary>18. When is querying data faster via graph databases vs relational databases?</summary>

> **Answer:**
>When we need to join many big tables.

</details>

<details>
<summary>19. What can a graph database be used for?</summary>

> **Answer:**
>Social networks, Network diagrams, Graph based search of digital assets

</details>

<details>
<summary>20. What are some reasons to use traditional RDBMS over NoSQL?</summary>

> **Answer:**
>* Relational database normalization means that each fact in your data is stored only once, so you shouldn't get data anomalies.
>* Relational schema means you always know what columns (i.e. attributes) exist for a given row.
>* Data types help to ensure data in a given column is well-formed. CHECK constraints can further validate data.
>* Enforcement of declarative constraints, such as NOT NULL, UNIQUE KEY, or FOREIGN KEY.
>* Authentication and access privileges are handled better in SQL.
>* SQL is the dominant query language for relational databases. SQL is an industry standard, interoperable between platforms and application programming languages, well-documented, and stable.
>* Many RDBMS exist that have solved the ACID requirement with a good balance between durability and performance.
</details>

**[⬆ back to top](#exam-questions)**
