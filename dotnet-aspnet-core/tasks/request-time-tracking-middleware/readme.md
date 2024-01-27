# Request Time Tracking Middleware

## Short Description

Add middleware for the request time tracking.

## Estimation (h)

16

## Topics

* ASP.NET Core
* WebApi
* App configuration
* Middleware
* Hosting
* Logging

## Requirements

* Implement `ProfileController` with several actions:
  * Action that will return one profile by user Id
  * Action that will return a collection of profiles
  * Action that will add user profile to the collection
  * Action that will update user profile in the collection
  * Action that will delete user profile from collection
* Implement middleware that will track time when the request started and finished.
* Write the request timing information to logs using [NLog](https://nlog-project.org/) or using
  [Serilog](https://serilog.net/).
