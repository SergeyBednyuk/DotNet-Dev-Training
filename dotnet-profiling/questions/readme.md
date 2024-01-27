# Questions

## Beginner

<details>
  <summary>1. Have you ever used profiling tools for .NET apps?</summary>

> **Answer:**
> Yes/no.

</details>

<details>
  <summary>2. Why do we need profiling tools?</summary>

> **Answer:**
> Profiling and diagnostics tools help you diagnose memory and CPU usage and other application level-issues. With these tools, you can accumulate data (such as variable values, function calls, and events) over the time you run your application in the debugger. You can view the state of your application at different points during the execution of your code.
 
</details>

<details>
  <summary>3. What is the difference between Release and Debug modes?</summary>

> **Answer:**
> Debug and Release are labels for different solution configurations. By default, Debug includes debug information in the compiled files (allowing easy debugging) while Release usually has optimizations enabled.

</details>

<details>
  <summary>4. How to use conditional breakpoint in Visual Studio?</summary>

> **Answer:**
> In the Condition field, enter a conditional expression to be evaluated each time this breakpoint is encountered during program execution. The breakpoint pauses execution when the expression evaluates to True.

</details>

<details>
  <summary>5. What windows for variable inspecting do you know?</summary>

> **Answer:**
>  There are windows for checking variables in VS watch, quick watch, autos, locals.
> The Locals will show local variables of the current scope. The Autos window will show all variables used in the current line and in the previous line.
> The watch window will show the variables and expressions that you have added to it.

</details>

<details>
  <summary>6. What is the callstack?</summary>

> **Answer:**
>  Call Stack Window shows the chain of methods that called one another, up to the the currently debugged method.

</details>

<details>
  <summary>7. What is the pdb file? Do you have to deploy it on production?</summary>

> **Answer:**
>  A PDB file contains information for the debugger to work with, it is special useful for debugging libraries.
> You don't need any debug information on production server, so pdb file should be excluded from deploy.

</details>

<details>
  <summary>8. List profiling and diagnostics tools that can be used for .NET apps profiling?</summary>

> **Answer:**
> * Visual Studio > Profiling Tools
> * dotTrace from JetBrains
> * BenchmarkDotNet
> * dotMonitor

</details>

<details>
  <summary>9. Will it be possible to run VS profiling tools without the debugger or on Release config?</summary>

> **Answer:**
> Yes. CPU Usage and Memory Usage, can run with or without the debugger, and on Release or Debug build configurations. Performance Profiler tools like Application Timeline can run on Debug or Release builds. 

</details>

<details>
  <summary>10. What is the main difference between non-debugger and debugger-integrated tools? Provide examples of such tools in Visual Studio.</summary>

> **Answer:**
> The non-debugger **Performance Profiler** and the debugger-integrated **Diagnostic Tools** provide different information and experiences.
> Debugger-integrated tools show you breakpoints and variable values.
> Non-debugger tools give you results closer to the end-user experience.

</details>

## Intermediate

<details>
  <summary>1. List good practices that should be used during writing benchmarks?</summary>

> **Answer:**
> * Use the Release build without an attached debugger
> * Avoid dead code elimination: You should use the result of calculation.
> * Turn off all of the applications except the benchmark process and the standard OS processes. If you run benchmark and work in the Visual Studio at the same time, it can negatively affect to benchmark results.
> * If you use laptop for benchmarking, keep it plugged in and use the maximum performance mode.

</details>

<details>
  <summary>2. What attribute can be used for classes to display an object in a user-friendly format in VS watch windows?</summary>

> **Answer:**
>  DebuggerDisplay attribute.

</details>

## Advanced

<details>
  <summary>1. What is the main difference between performance profiling modes (sampling, tracing, line-by-line) in dotTrace.</summary>

> **Answer:**
> Sampling mode useful for investigation of call times, tracing - call numbers, line-by-line - narrow down on one method.

</details>
