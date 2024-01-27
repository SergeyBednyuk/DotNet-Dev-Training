# .NET Profiling

## Version

2.0.0

## Introduction

After this course you will be able to profile .NET applications.

## Table of Contents

* [Theory](./theory/readme.md)
* [Tasks](./tasks/readme.md)
* [Questions](./questions/readme.md)

## Topics

### Beginner

* Visual Studio
  * Debugging
    * Release and debug modes
    * Running, debugging, attaching to process
    * Breakpoints, run code to specific line of code
    * Breakpoints with conditions, break when variable was changed
    * Watch, quick watch, locals, autos windows using
    * Step into/over/out debugging
    * Callstack and threads windows using
    * Hints for variables using
    * Variable description decoration with DebuggerDisplay attribute
    * Dll debugging, pdb files
  * Profiling with Diagnostic tools
    * Events checking (exceptions, sql queries)
    * CPU usage
    * CPU profile recording and analizing
    * Memory usage
    * Memory Snapshot creating, comparing, analizing

### Intermediate

* BenchmarkDotNet
* dotnet monitor

### Advanced

* dotTrace
  * Timeline profiling
  * Profiling modes (sampling, tracing, line-by-line)
  * Performance Viewer
  * Unit tests profiling
  * Remote app profiling

## Prerequisites

### Technical

* C#
* .NET

### Environment

* Visual Studio
* .NET Core SDK
* dotTrace
* BenchmarkDotNet
* dotnet monitor

## Plan

| Name                                                                                                                         | Type          | Short Description                                         | Level        | Required | Estimation (h) |
|------------------------------------------------------------------------------------------------------------------------------|---------------|-----------------------------------------------------------|--------------|----------|----------------|
| [Debugging with VS part 1](https://www.youtube.com/watch?v=u-HdLtqEOog)                                                      | video         | Watch screencast about debugging in VS                    | beginner     | required | 0.5            |
| [Debugging with VS part 2](https://www.youtube.com/watch?v=lgKInHJ-tcg)                                                      | video         | Watch screencast about debugging in VS                    | beginner     | required | 0.5            |
| [Profiling Feature Tour in VS](https://docs.microsoft.com/en-us/visualstudio/profiling/profiling-feature-tour)               | documentation | Read articles about quickstart with profiling tools in VS | beginner     | required | 4              |
| [Measure CPU usage in VS](https://docs.microsoft.com/en-us/visualstudio/profiling/beginners-guide-to-performance-profiling)  | article       | Read article about measuring CPU usage in VS              | beginner     | required | 1              |
| [Measure Memory usage in VS](https://docs.microsoft.com/en-us/visualstudio/profiling/memory-usage?view=vs-2019)              | article       | Read article about measuring memory usage in VS           | beginner     | required | 1              |
| [BenchmarkDotNet Articles](https://benchmarkdotnet.org/)                                                                     | documentation | Read documentation about benchmarking C# code in .NET     | intermediate | required | 4              |
| [dotTrace Overview](https://www.youtube.com/playlist?list=PLQ176FUIyIUbfsTxYqjlAMTm8JAYZKNGu)                                | video         | Watch screencast about dotTrace profiler                  | advanced     | required | 1              |
| [Profiling Concepts in dotTrace](https://www.jetbrains.com/help/profiler/Basic_Concepts.html)                                | article       | Read article about profiling concepts in dotTrace         | advanced     | required | 1              |
| [Performance Viewer in dotTrace](https://www.jetbrains.com/help/profiler/Get_Started_with_Performance_Viewer.html)           | documentation | Read article about performance viewer in dotTrace         | advanced     | required | 1              |
| [Timeline Profiling in dotTrace](https://www.jetbrains.com/help/profiler/Get_Started_with_Timeline_Profiling_\(Basic\).html) | documentation | Read article about timeline profiling with dotTrace       | advanced     | required | 1              |
| [Debugging](./tasks/debugging/readme.md)                                                                                     | tasks group   | Investigate debugging process with VS.                    | beginner     | required | 16             |
| [Profiling with VS](./tasks/vs-profiling/readme.md)                                                                          | task          | Investigate profiling process with VS.                    | beginner     | required | 8              |
| [Profiling with dotTrace](./tasks/dot-trace-profiling/readme.md)                                                             | task          | Investigate profiling process with dotTrace.              | advanced     | required | 8              |
| [Tour of dotnet monitor](https://devblogs.microsoft.com/dotnet/introducing-dotnet-monitor)                                   | article       | Read article about diagnostics with dotnet monitor.       | intermediate | required | 1              |
| [dotnet monitor in .NET 6](https://devblogs.microsoft.com/dotnet/announcing-dotnet-monitor-in-net-6)                         | article       | Read article about dotnet monitor in .NET 6.              | intermediate | required | 1              |
