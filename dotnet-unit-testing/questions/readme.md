# Questions

## Beginner

### Levels of testing

<details>
  <summary>1. Have you ever used tests?</summary>

> **Answer:**
> Yes/no

</details>

<details>
  <summary>2. Which testing frameworks have you used?</summary>

> **Answer:**
> xUnit/NUnit/MSTest/etc 

</details>

 <details>
  <summary>3. Why unit test?</summary>

> **Answer:**
> * Less time performing functional tests
> * Protection against regression
> * Executable documentation
> * Less coupled code

</details>

<details>
  <summary>4. What difference between unit tests and integration tests?</summary>

> **Answer:**
>A unit test is a piece of a code (usually a method) that invokes another
>piece of code and checks the correctness of some assumptions afterward.
>If the assumptions turn out to be wrong, the unit test has failed.
>A “unit” is a method or function.
>
>whereas
>
>Integration testing means testing two or more dependent software modules
>as a group.
</details>



### Best practices with .NET Core and .NET Standard

<details>
  <summary>1. What are main characteristics of a good unit test?</summary>

> **Answer:**
> * Fast
> * Isolated
> * Repeatable
> * Self-checking
> * Timely

</details>

<details>
  <summary>2. What are common recommendations for tests structure of a .NET solution?</summary>

> **Answer:**
>1. One test project per tested project.
>2. One test class per tested class.
>3. At least one test method per tested method.
</details>

<details>
  <summary>3. Describe a common structure of a unit test?</summary>

> **Answer:**
>1. Test name and description.
>2. Test cases.
>3. Arrangement section.
>4. Action section.
>5. Assertion section.
</details>


<details>
  <summary>4. What is a common structure of a unit test name?</summary>

> **Answer:**
> [MethodName]\_[StateUnderTest]\_[ExpectedBehavior] or [MethodName]\_[ExpectedBehavior]\_[StateUnderTest]
>Notes:
>
>1. `StateUnderTest` is optional for some cases.
>2. `StateUnderTest` can be very long.
>3. `ExpectedBehavior` is laconic in most of cases (`ReturnsZero`, `ThrowArgNullError`, etc.)
</details>

<details>
  <summary>5. What is a test case? How can we create test cases for a unit test in .NET?</summary>

> **Answer:**
>The test case is a single test scenario with data provided as test method parameters.
>Test cases provided via `[TestCase]` attribute for NUnit and `[InlineData]` or `[ClassData]` attributes for xUnit.
>
>```csharp
>[Theory]
>[InlineData("Foo")]
>[InlineData(9)]
>[InlineData(true)]
>public void Should_be_assigned_different_values(object value)
>{
>    Assert.NotNull(value);
>}
>```
</details>

<details>
  <summary>6. How can we set up and dispose test data for a unit test?</summary>

> **Answer:**
> * `[SetUp]` and `[TearDown]` attributes for NUnit. Also NUnit has `[TestFixtureSetUp]` and `[TestFixtureTearDown]`
>attributes for setting and disposing state once per class run.
> * Constructor and IDisposable interface for xUnit.
</details>

### Unit testing tools

<details>
  <summary>1. Which testing frameworks do you know?</summary>

> **Answer:**
>1. xUnit
>2. NUnit
>3. MSTest 
</details>

<details>
  <summary>2. How can we check expected exceptions? What about exceptions in asynchronous calls?</summary>

> **Answer:**
>NUnit:
>
>* `[ExpectedException(typeof(ExceptionType), ExpectedMessage="message")]`
>* `Assert.Throws<T>(() => ...)`
>* `Assert.ThrowsAsync<T>(async () => ...)`
>
>xUnit:
>
>* `Assert.Throws<T>(() => ...)`
>* `Assert.ThrowsAsync<T>(() => ...)`
</details>


<details>
  <summary>3. How can we ignore broken tests? When is it used?</summary>

> **Answer:**
> Sometimes you’ll have tests that are broken and you still need
> to check in your code to the main source tree.
> You can ignore a test by the special attribute
>##### NUnit:
>* `[Ignore(message)]`
>##### MSTest:
>* `[Ignore]`
>##### xUnit:
>* `[Fact(Skip="reason")]`
</details>

<details>
  <summary>4. How can we tag tests and split them by categories?</summary>

> **Answer:**
>You can set up your tests to run under specific test categories, such as
>slow tests and fast tests. You do this by using NUnit’s `[Category]` attribute or xUnit's `[Trait(propertyName, value)]`
</details>

### Fake/Mock/Stub

<details>
  <summary>1. What is fake object?</summary>

> **Answer:**
>A fake is a class that you can use instead of actual line of business code.
>Fakes are objects that have working implementations, 
>but not same as production one. Usually they take some shortcut and have simplified version of production code.
</details>

<details>
  <summary>2. What is stub?</summary>

> **Answer:**
>A stub is a controllable replacement for an existing dependency (or collaborator)
>in the system. By using a stub, you can test your code without
>dealing with the dependency directly
</details>

<details>
  <summary>3. What is mock object?</summary>

> **Answer:**
>A mock object is a fake object in the system that decides whether the
>unit test has passed or failed. It does so by verifying whether the object
>under test interacted as expected with the fake object. There’s usually
>no more than one mock per test.
</details>

<details>
  <summary>4. List techniques for breaking dependencies. Explain each of them.</summary>

> **Answer:**
>* Extract an interface to allow replacing underlying implementation.
>* Inject stub implementation into a class under test.
>* Receive an interface at the constructor level.
>* Receive an interface as a property get or set.
>* Get a stub just before a method call.
</details>

<details>
  <summary>5. Why is bad practice to use more than one mock object per test?</summary>

> **Answer:**
>Having more than one mock per test usually
>means you’re testing more than one thing, and this can lead to complicated
>or brittle tests. So should be no more than one mock object. All other
>fake objects will act as stubs.
</details>

<details>
  <summary>6. What is the difference between mock and stub?</summary>

> **Answer:**
> * Mock - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed. A mock starts out as a Fake until it is asserted against.
> * Stub - A stub is a controllable replacement for an existing dependency (or collaborator) in the system. By using a stub, you can test your code without dealing with the dependency directly. By default, a fake starts out as a stub.

</details>


<details>
  <summary>7. What are isolation frameworks?</summary>

> **Answer:**
>An isolation framework is a set of programmable APIs that make creating
>mock and stub objects much easier. Isolation frameworks save the
>developer from the need to write repetitive code to test or simulate
>object interactions.
</details>

<details>
  <summary>8. List advantages and typical mistakes of using isolation frameworks?</summary>

> **Answer:**
>Advantages:
>
>* Easier parameter verification
>* Easier verification of multiple method calls
>* Easier fakes creation
>
>Typical mistakes:
>
>* Unreadable test code
>* Verifying the wrong things
>* Having more than one mock per test
>* Overspecifying the tests
</details>

## Advanced

### .NET mocking library
<details>
  <summary>1. Which mocking libraries do you know?</summary>

> **Answer:**
>1. Moq
>2. NSubstitute
</details>

### Test Driven Development(TDD) and Behavior Driven Development(BDD)

<details>
  <summary>1. What is the main idea of TDD?</summary>

> **Answer:**
> 1. Write test
> 2. Write code that passes tests.
> 3. Refactor code to match other criterias.

</details>

<details>
  <summary>2. What is the main idea of BDD?</summary>

> **Answer:**
> 1. BDD is an agile software engineering practice that supports feature discovery and encourages collaboration among developers, testers and business participants in a software development team.
> 2. BDD describes application behavior from a user’s point of view.
> 3. Overall, the main goal of BDD is to improve the collaboration between all stakeholders involved in developing software and form a shared understanding among them.
> 4. The key to BDD is to get the specifications from the user. In other words, create tests that are not written by developers. This means tests that are not written in a programming language. These tests should be written in a language close to English (or whatever your team speaks.)

</details>