# Deploy a highly available application

## Short Description

Configure your system to use secondary locations.
[Exercise in sandbox](https://learn.microsoft.com/en-us/training/modules/ha-application-storage-with-grs/5-exercise-deploy-ha-application)

## Estimation (h)

4

## Topics

* Replication
* Locations
* Availability

## Requirements

* Configure Blob Storage to use secondary location or use sandbox configuration from the link above.
* Write an application that will communicate with Azure Blob Storage or you can use application from then link above.
  * Application must create an object
  * Application must force Blob Storage to replicate this object to secondary location.
  * Application must switch between to secondary location if the primary is unreachable and switch back after threshold.
* Use Fiddler or analog to decrypt https traffic and set primary location service unavailable.
* Test availability of secondary location.
