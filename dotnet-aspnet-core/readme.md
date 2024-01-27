# .NET ASP.NET Core

## Version

2.0.1

## Introduction

After this course you will be able to create APS.NET MVC Core or WebApi applications. You will learn the application
life cycle and configuration. You will know how to create and host complex web applications with authentication,
dependency injection, routing, error handling and logging.

## Table of Contents

* [Theory](./theory/readme.md)
* [Tasks](./tasks/readme.md)
* [Questions](./questions/readme.md)

## Topics

### Beginner

* Fundamentals:
  * ASP.NET Core Overview
  * ASP.NET Core application startup
  * Dependency Injection (DI)
  * ASP.NET Core Pipeline and Middleware
* MVC
  * Overview of ASP.NET Core MVC
  * Controllers in ASP.NET Core
  * Model Binding
  * Views in ASP.NET Core MVC
* Web API
  * ASP.NET Core Web API Overview
  * Action Return Types
* Security and identity
  * Introduction to Identity
  * Authentication samples
* Other
  * Make HTTP Requests

### Intermediate

* Fundamentals:
  * ASP.NET Core Custom Middleware
  * .NET Core Generic Host
  * Configuration in ASP.NET Core
  * Environments in ASP.NET Core
  * Logging in .NET Core and ASP.NET Core
  * Handle errors in ASP.NET Core
  * Static files in ASP.NET Core
  * Session and app state
  * URL Rewriting
* MVC
  * Custom Model Binding
  * Model Validation
  * Partial views
  * Layout in ASP.NET Core
  * Razor syntax
  * Tag Helpers in ASP.NET Core
  * Caching
  * Routing in ASP.NET Core MVC
* Web API
  * Format response data in ASP.NET Core Web API
  * Custom response data formatters
  * Handle errors in ASP.NET Core web APIs
* Security and identity
  * Simple authorization
  * Role-based authorization
  * Claims-based authorization
  * Policy-based authorization
* Other
  * SignalR
  * Razor Pages

### Advanced

* MVC
  * Filters
  * Areas
  * Globalization and Localization
* Web API
  * Web API conventions
* Security and identity
  * Prevent Cross-Site Request Forgery (XSRF/CSRF) attacks
  * Prevent Cross-Site Scripting (XSS)
  * Cross-Origin Requests (CORS)
* Other
  * Blazor
  * gRPC Services
  * ASP.NET Core Performance Best Practices

## Prerequisites

### Technical

* C#
* .NET

### Environment

* Any browser from below
  * Google Chrome
  * Firefox
  * Internet Explorer 11
  * Microsoft Edge
* Recommended IDE
  * Visual Studio 2017
  * Visual Studio 2019
  * JetBrains Rider
  * Visual Studio Code

## Plan

| Name                                                                                                                                                                            | Type          | Short Description                                                                                    | Level        | Required | Estimation (h) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ---------------------------------------------------------------------------------------------------- | ------------ | -------- | -------------- |
| [Fundamentals: ASP.NET Core Overview](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/?view=aspnetcore-3.0&tabs=windows)                                              | documentation | Read the overview of key topics for understanding how to develop ASP.NET Core apps                   | beginner     | required | 0.2            |
| [Fundamentals: ASP.NET Core application startup](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/startup?view=aspnetcore-3.0)                                         | documentation | Read the topic about configuring services and request pipeline                                       | beginner     | required | 0.2            |
| [Fundamentals: Dependency Injection (DI) in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-3.0)                   | documentation | Read the topic about how the DI is supported in ASP.NET Core applications                            | beginner     | required | 0.3            |
| [Fundamentals: ASP.NET Core Pipeline and Middleware](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/middleware/?view=aspnetcore-3.0)                                 | documentation | Read the topic about ASP.NET Core application request pipeline                                       | beginner     | required | 0.2            |
| [Fundamentals: ASP.NET Core Custom Middleware](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/middleware/write?view=aspnetcore-3.0)                                  | documentation | Read the topic about creating a custom middleware                                                    | intermediate | required | 0.1            |
| [Fundamentals: .NET Core Generic Host](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/host/generic-host?view=aspnetcore-3.0)                                         | documentation | Read the topic about what .NET Core Generic Host is and how to use it                                | intermediate | required | 0.3            |
| [Fundamentals: Configuration in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/configuration/?view=aspnetcore-3.0)                                     | documentation | Read the topic about configuration and configuration providers                                       | intermediate | required | 0.5            |
| [Fundamentals: Environments in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/environments?view=aspnetcore-3.0)                                        | documentation | Read the topic about using multiple environments in ASP.NET Core applications                        | intermediate | required | 0.2            |
| [Fundamentals: Logging in .NET Core and ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0)                                   | documentation | Read the topic about how to use the logging API with built-in providers                              | intermediate | required | 0.5            |
| [Fundamentals: Handle errors in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/error-handling?view=aspnetcore-3.0)                                     | documentation | Read the topic about error handling in ASP.NET Core                                                  | intermediate | required | 0.2            |
| [Fundamentals: Static files in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/static-files?view=aspnetcore-3.0)                                        | documentation | Read the topic about how to use static files serving                                                 | intermediate | required | 0.2            |
| [Fundamentals: Session and app state](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/app-state?view=aspnetcore-3.0)                                                  | documentation | Read the topic about ASP.NET Core application state                                                  | intermediate | required | 0.3            |
| [Fundamentals: URL Rewriting](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/url-rewriting?view=aspnetcore-3.0)                                                      | documentation | Read the topic about URL Rewriting in ASP.NET Core                                                   | intermediate | optional | 0.5            |
| [MVC: Overview of ASP.NET Core MVC](https://docs.microsoft.com/en-us/aspnet/core/mvc/overview?view=aspnetcore-3.0)                                                              | documentation | Read the topic about the MVC design pattern and its implementation in the ASP.NET Core MVC framework | beginner     | required | 0.2            |
| [MVC: Controllers in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/actions?view=aspnetcore-3.0)                                                    | documentation | Read the topic about Controllers in ASP.NET Core framework                                           | beginner     | required | 0.2            |
| [MVC: Views in ASP.NET Core MVC](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/overview?view=aspnetcore-3.0)                                                           | documentation | Read the topic about Views which handle the app's data presentation and user interaction             | beginner     | required | 0.3            |
| [MVC: Partial views](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/partial?view=aspnetcore-3.0)                                                                        | documentation | Read the topic about Partial views and its usage                                                     | intermediate | required | 0.3            |
| [MVC: Layout in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/layout?view=aspnetcore-3.0)                                                                | documentation | Read the topic about how to use Layout in ASP.NET Core MVC                                           | intermediate | required | 0.2            |
| [MVC: Razor syntax](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/razor?view=aspnetcore-3.0)                                                                           | documentation | Read the topic about Razor rendering engine and its syntax                                           | intermediate | required | 0.3            |
| [MVC: Tag Helpers in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/tag-helpers/intro?view=aspnetcore-3.0)                                                | documentation | Read the topic about built-in Tag Helpers and how to create custom ones                              | intermediate | required | 0.2            |
| [MVC: Model Binding](https://docs.microsoft.com/en-us/aspnet/core/mvc/models/model-binding?view=aspnetcore-3.0)                                                                 | documentation | Read the topic about how the Model Binding works                                                     | beginner     | required | 0.2            |
| [MVC: Custom Model Binding](https://docs.microsoft.com/en-us/aspnet/core/mvc/advanced/custom-model-binding?view=aspnetcore-3.0)                                                 | documentation | Read the topic about how to create custom model bindings                                             | intermediate | required | 0.2            |
| [MVC: Model Validation](https://docs.microsoft.com/en-us/aspnet/core/mvc/models/validation?view=aspnetcore-3.0)                                                                 | documentation | Read the topic about model validation                                                                | intermediate | required | 0.3            |
| [MVC: Caching](https://docs.microsoft.com/en-us/aspnet/core/performance/caching/response?view=aspnetcore-3.0)                                                                   | documentation | Read the topic about caching in ASP.NET Core framework                                               | intermediate | required | 0.2            |
| [MVC: Routing in ASP.NET Core MVC](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/routing?view=aspnetcore-3.0)                                                    | documentation | Read the topic about how the Routing works in the ASP.NET Core MVC applications                      | intermediate | required | 0.5            |
| [MVC: Filters](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/filters?view=aspnetcore-3.0)                                                                        | documentation | Read the topic about Filters                                                                         | advanced     | required | 0.3            |
| [MVC: Areas](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/areas?view=aspnetcore-3.0)                                                                            | documentation | Read the topic about Areas concept in ASP.NET Core                                                   | advanced     | required | 0.2            |
| [MVC: Globalization and localization](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/localization?view=aspnetcore-3.0)                                               | documentation | Read the topic about application globalization and localization                                      | advanced     | required | 0.3            |
| [WebAPI: ASP.NET Core WebAPI Overview](https://docs.microsoft.com/en-us/aspnet/core/web-api/?view=aspnetcore-3.0)                                                               | documentation | Read the topic about creating a RESTful web services with ASP.NET Core framework                     | beginner     | required | 0.2            |
| [WebAPI: Action Return Types](https://docs.microsoft.com/en-us/aspnet/core/web-api/action-return-types?view=aspnetcore-3.0)                                                     | documentation | Read the topic about data types which can be returned from controller's actions                      | beginner     | required | 0.2            |
| [WebAPI: Format response data in ASP.NET Core Web API](https://docs.microsoft.com/en-us/aspnet/core/web-api/advanced/formatting?view=aspnetcore-3.0)                            | documentation | Read the topic about response data formatting                                                        | intermediate | required | 0.2            |
| [WebAPI: Custom response data formatters](https://docs.microsoft.com/en-us/aspnet/core/web-api/advanced/custom-formatters?view=aspnetcore-3.0)                                  | documentation | Read the topic about creating custom response data formatters                                        | intermediate | required | 0.2            |
| [WebAPI: Web API conventions](https://docs.microsoft.com/en-us/aspnet/core/web-api/advanced/conventions?view=aspnetcore-3.0)                                                    | documentation | Read the topic about using Web API conventions                                                       | advanced     | optional | 0.2            |
| [WebAPI: Handle errors in ASP.NET Core web APIs](https://docs.microsoft.com/en-us/aspnet/core/web-api/handle-errors?view=aspnetcore-3.0)                                        | documentation | Read the topic about how to handle errors in ASP.NET Core web APIs                                   | intermediate | required | 0.2            |
| [Security and identity: Introduction to Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-3.0&tabs=visual-studio)         | documentation | Read the topic about authentication in ASP.NET Core                                                  | beginner     | required | 0.2            |
| [Security and identity: Authentication samples](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/samples?view=aspnetcore-3.0)                               | documentation | Review authentication samples                                                                        | beginner     | required | 1              |
| [Security and identity: Simple authorization](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/simple?view=aspnetcore-3.0)                                   | documentation | Read the topic about basic authorization                                                             | intermediate | required | 0.1            |
| [Security and identity: Role-based authorization](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/roles?view=aspnetcore-3.0)                                | documentation | Read the topic about role-based authorization                                                        | intermediate | required | 0.1            |
| [Security and identity: Claims-based authorization](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/claims?view=aspnetcore-3.0)                             | documentation | Read the topic about claims-based authorization                                                      | intermediate | required | 0.1            |
| [Security and identity: Policy-based authorization](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/policies?view=aspnetcore-3.0)                           | documentation | Read the topic about policy-based authorization                                                      | intermediate | required | 0.1            |
| [Security and identity: Prevent Cross-Site Request Forgery (XSRF/CSRF) attacks](https://docs.microsoft.com/en-us/aspnet/core/security/anti-request-forgery?view=aspnetcore-3.0) | documentation | Read the topic about preventing Cross-Site Request Forgery                                           | advanced     | required | 0.2            |
| [Security and identity: Prevent Cross-Site Scripting (XSS)](https://docs.microsoft.com/en-us/aspnet/core/security/cross-site-scripting?view=aspnetcore-3.0)                     | documentation | Read the topic about preventing XSS attacks                                                          | advanced     | required | 0.1            |
| [Security and identity: Cross-Origin Requests (CORS)](https://docs.microsoft.com/en-us/aspnet/core/security/cors?view=aspnetcore-3.0)                                           | documentation | Read the topic about Cross-Origin Requests                                                           | advanced     | required | 0.2            |
| [Other: SignalR](https://docs.microsoft.com/en-us/aspnet/core/signalr/introduction?view=aspnetcore-3.0)                                                                         | documentation | Read the topic about SignalR technology                                                              | intermediate | optional | 0.1            |
| [Other: Razor Pages](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/?view=aspnetcore-3.0)                                                                             | documentation | Read the topic about Razor Pages technology                                                          | intermediate | optional | 0.7            |
| [Other: Blazor](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-3.1)                                                                                       | documentation | Read the topic about Blazor technology                                                               | advanced     | optional | 0.1            |
| [Other: gRPC Services](https://docs.microsoft.com/en-us/aspnet/core/grpc/?view=aspnetcore-3.0)                                                                                  | documentation | Read the topic about gRPC Services in ASP.NET Core                                                   | advanced     | optional | 0.1            |
| [Other: ASP.NET Core Performance Best Practices](https://docs.microsoft.com/en-us/aspnet/core/performance/performance-best-practices?view=aspnetcore-3.0)                       | documentation | Read the topic about how performance of the ASP.NET Core app can be increased                        | advanced     | required | 0.2            |
| [Other: Make HTTP Requests](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-3.0)                                                        | documentation | Read the topic about making Http requests in ASP.NET Core applications                               | beginner     | required | 0.7            |
| [Custom Model Binders](./tasks/custom-model-binder/readme.md)                                                                                                                   | task          | Add custom model binders for ASP.NET Core MVC application.                                           | beginner     | required | 8              |
| [Rate Limit](./tasks/rate-limit/readme.md)                                                                                                                                      | task          | Add an attribute to limit the number of concurrent requests to Action.                               | beginner     | required | 32             |
| [Custom Json Formatter](./tasks/custom-json-formatter/readme.md)                                                                                                                | task          | Add custom JSON formatter for ASP.NET Core MVC application.                                          | beginner     | required | 24             |
| [Permissions Attribute](./tasks/permissions-attribute/readme.md)                                                                                                                | task          | Add custom permissions attribute in ASP.NET Core MVC application.                                    | beginner     | required | 32             |
| [Request Time Tracking Middleware](./tasks/request-time-tracking-middleware/readme.md)                                                                                          | task          | Add middleware for the request time tracking.                                                        | beginner     | required | 16             |

## Additional Materials

* [ASP.NET Core - Beginner](https://mva.microsoft.com/en-us/training-courses/asp-net-core-beginner-18153) - Explore
  ASP.NET Core SDK and tooling, look at .NET Core CLI, and learn how to build an ASP.NET Core app with Razor Pages MVC.
  Plus, get the details on logging and diagnostics. Find lots of cross-platform goodness and get .NET ready, as you
  learn more about this framework for building modern cloud-based web apps. Build your first ASP.NET project
* [ASP.NET Core MVC Tutorial](https://asp.mvc-tutorial.com/) - ASP.NET Core MVC tutorial, currently consisting of 42
  articles, where you'll learn to make your own web applications using ASP.NET Core and the MVC framework. Suitable even
  for those, who are brand new to ASP.NET and/or the MVC concept.

## Books

| Title                    | Author        | Edition |
|--------------------------|---------------|---------|
| Programming ASP.NET Core | Dino Esposito | None    |
| ASP.NET Core in Action   | Andrew Lock   | None    |
