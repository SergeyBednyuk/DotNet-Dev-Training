# .NET Unit Testing

## Version

2.0.0

## Introduction

After this course you will be able to create a test project and use one of existing testing frameworks.

## Table of Contents

* [Theory](./theory/readme.md)
* [Tasks](./tasks/readme.md)
* [Questions](./questions/readme.md)

## Topics

### Beginner

* Levels of testing
  * Unit tests
  * Integration tests
  * System testing
  * Acceptance testing
* Best practices with .NET Core and .NET Standard
  * Naming your tests
  * Arranging your tests
  * Code coverage
  * What logic is covered
* Unit testing tools
  * xUnit
  * NUnit
  * MStest
* Fake/Mock/Stub
  * Understand Stub, Mock and Fake in Unit Testing
  * Understand Mock Object in Unit Testing
* .NET mocking library
  * Moq

### Advanced

* .NET mocking library
  * NSubstitute
* Test Driven Development(TDD) and Behavior Driven Development(BDD)
  * What is TDD?
  * What is BDD?

## Prerequisites

### Technical

* C#
* .NET

## Plan

| Name                                                                                                            | Type          | Short Description                                                                                                                | Level    | Required | Estimation (h) |
|-----------------------------------------------------------------------------------------------------------------|---------------|----------------------------------------------------------------------------------------------------------------------------------|----------|----------|----------------|
| [Levels of Testing](https://reqtest.com/testing-blog/different-levels-of-testing/)                              | article       | Read topics about levels of testing                                                                                              | beginner | required | 1              |
| [.NET Core Guide: Unit testing](https://docs.microsoft.com/en-us/dotnet/core/testing/)                          | documentation | Read topics about unit testing in .NET Core and .NET Standard                                                                    | beginner | required | 1              |
| [Testing Quick Guide](https://www.tutorialspoint.com/software_testing/software_testing_quick_guide.htm)         | article       | Read it to find out what types of tests exist in advance to unit tests                                                           | beginner | required | 3              |
| [Unit Testing Screencast](https://1drv.ms/v/s!As8AujQS8DYUiKxDzJ89D3hCLWCmvQ)                                   | video         | Watch screencasts about unit testing                                                                                             | beginner | required | 3              |
| [Unit testing best practices](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices) | documentation | Read topic about unit testing best practices with .NET Core and .NET Standard                                                    | beginner | required | 3              |
| [xUnit docs](https://xunit.net/#documentation)                                                                  | documentation | Read doc about how to work with xUnit                                                                                            | beginner | required | 8              |
| [xUnit tutorial](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-dotnet-test)            | tutorial      | This tutorial shows how to build a solution containing a unit test project and source code project                               | beginner | required | 4              |
| [xUnit DependencyInjection](https://github.com/pengweiqhca/Xunit.DependencyInjection)                           | documentation | This documentation shows how to using dependency injection in a xUnit test project                                               | beginner | required | 2              |
| [NUnit docs](https://github.com/nunit/docs/wiki)                                                                | documentation | Read doc abot NUnit projects                                                                                                     | beginner | required | 8              |
| [NUnit tutorial](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-nunit)                  | tutorial      | This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts | beginner | required | 4              |
| [MSTest tutorial](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-mstest)                | tutorial      | This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts | beginner | required | 8              |
| [Run selective unit tests](https://docs.microsoft.com/en-us/dotnet/core/testing/selective-unit-tests)           | documentation | This article demonstrates how to filter which tests are run and how to run tests from console                                    | beginner | required | 8              |
| [Fakes, Stubs, and Mocks](https://www.telerik.com/blogs/fakes-stubs-and-mocks)                                  | article       | Read aticle about Fakes, Stubs, and Mocks                                                                                        | beginner | required | 1              |
| [NSubstitute Getting Started](https://nsubstitute.github.io/help/getting-started/)                              | documentation | Read topic about NSubstitute (.NET mocking library)                                                                              | advanced | required | 8              |
| [Moq Quickstart](https://github.com/Moq/moq4/wiki/Quickstart)                                                   | documentation | Read topic about getting started with Moq (mocking library)                                                                      | advanced | required | 8              |
| [TDD on Wiki](https://en.wikipedia.org/wiki/Test-driven_development)                                            | article       | Read about Test-Driven-Development process                                                                                       | advanced | required | 1              |
| [TDD](https://medium.freecodecamp.org/test-driven-development-what-it-is-and-what-it-is-not-41fa6bca02a2)       | article       | Read topic about TDD: what it is, and what it is not                                                                             | advanced | required | 1              |
| [BDD on Wiki](https://en.wikipedia.org/wiki/Behavior-driven_development)                                        | article       | Read about Behavior-Driven-Development process                                                                                   | advanced | required | 1              |
| [BDD](https://specflow.org/bdd/)                                                                                | article       | Read topic about BDD: what it is, and what it is not                                                                             | advanced | required | 1              |
| [TDD vs BDD](https://www.pluralsight.com/blog/software-development/tdd-vs-bdd)                                  | article       | Read the topic of comparison TDD and BDD approach                                                                                | advanced | required | 1              |
| [Write tests for CSV Reader](./tasks/csv-reader-test/readme.md)                                                 | task          | Create a test project and write tests for CSV reader.                                                                            | beginner | required | 8              |
| [Write tests for Round Robin collection](./tasks/round-robin-collection-test/readme.md)                         | task          | Create a test project and write tests for round-robin collection.                                                                | beginner | required | 8              |
