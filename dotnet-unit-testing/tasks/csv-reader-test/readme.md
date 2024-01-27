# Write tests for CSV Reader

## Short Description

Create a test project and write tests for simple CSV reader.

## Estimation (h)

8

## Topics

* IO/Streams.
* Work with testing framework: xUnit/NUnit/etc.
* Best practices in unit testing.

## Requirements

* Create CSV reader by TDD approach with constructor that accepts a stream and additional options.
* Create test project that covers main use cases:
  * Reader should be able to parse headers that can be in CSV file.
  * Reader should have method like `ReadRecord` that returns key/value collection and can be used when headers are
    present in file or were provided via optinos.
  * Develop two positive and two negative unit tests
