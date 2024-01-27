# Create Azure Cosmos DB

## Short Description

Create Azure Cosmos DB resources by using the Azure portal.
[Exercise in sandbox](https://learn.microsoft.com/en-us/training/modules/explore-azure-cosmos-db/8-create-cosmos-db-resources-portal)

## Estimation (h)

2

## Topics

* Azure Cosmos DB
* Databases

## Requirements

* In Azure Portal create Azure Cosmos DB resource with the following properties:
  * Subscription: Select the subscription you want to use.
  * Resource Group: Select Create new, then enter az204-cosmos-rg.
  * Account Name: Enter a unique name to identify your Azure Cosmos account.
  * Location: Use the location that is closest to your users to give them the fastest access to the data.
  * Capacity mode: Select Serverless.
* Add a new container in created database with the following properties:
  * Database ID: Select Create new, and enter ToDoList.
  * Container ID: Enter Items
  * Partition key: Enter /category. The samples in this demo use /category as the partition key.
* Add data to your database:
  * Create new item with your structure.
  * Create another item with the same structure, but unique id.
* Cleanup resources.
