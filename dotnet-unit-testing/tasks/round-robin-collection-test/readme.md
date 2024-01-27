# Write Tests for Round Robin Collection

## Short Description

Create a test project and write tests for round-robin collection.

## Estimation (h)

8

## Topics

* Creating custom collection.
* Work with testing framework: xUnit/NUnit/etc.
* Best practices in unit testing.

## Requirements

* Create readonly [round-robin](https://en.wikipedia.org/wiki/Round-robin_scheduling) collection by TDD approach that
  implements IEnumerable\<T\>.

* This collections has contructor that accepts a sequence of elements. For example List\<int\>.

* GetEnumerator should return items infinitely.

  * Assume collection contains: 1, 2, 3, 4, 5.
  * And we have next pseudo-code:

  ```cs
       var roundRobinList = new RoundRobinList<int>(
            new List<int>{
          1,2,3,4,5
      }
    );

     for (var i = 0; i < 8; i++)
     {
       Write($"{roundRobinList.Next()},");
    }

    //result
    //1,2,3,4,5,1,2,3,
  ```

* Test should validate main scenarios of round-robin collection usage.
