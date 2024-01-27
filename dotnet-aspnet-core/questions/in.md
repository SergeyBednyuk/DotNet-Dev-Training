# Interview Questions

## Fundamentals

<details>
  <summary>1. What is .NET Core?</summary>

> **Answer:**
> .NET Core is a newer version of .NET, which is cross-platform, supporting Windows, MacOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios. 
> .NET Core is compatible with .NET Framework, Xamarin and Mono, via the .NET Standard Library.

</details>

<details>
  <summary>2. Explain Middleware in ASP.NET Core?</summary>
  
> **Answer:**
> Middleware is software that application assembles into the pipeline to handle requests and responses. 
> Each part chooses to pass the request on to the next part in the pipeline, and can do certain actions before and after application invokes the next part in the pipeline. 
> In ASP.NET we had modules, handlers, web.config and other things that we used to deal with requests. In ASP.NET Core we have middleware.

</details>

## MVC

<details>
  <summary>1. What does MVC mean?</summary>

> **Answer:**
> Model-View-Controller is an architectural pattern. The main idea is to separate business logic from an application’s UI. 
> Application logic is located in controllers.
> Views are responsible for the UI rendering. 
> Models are usually used for data transfer back and forth between controllers and views.

</details>

<details>
  <summary>2. What basic folders do we have in an ASP.NET Core project using the MVC template without Areas? What are they for?</summary>

> **Answer:**
> wwwroot: The root folder of a site, publicly accessible, contains subfolders for static files (CSS, images, JS, etc.).
> Controllers: A default folder for application controllers.
> Views: It contains a folder for every controller, plus a special folder Shared for views used by multiple views/controllers. 

</details>

<details>
  <summary>3.Can you explain the page life cycle of MVC?</summary>
  
> **Answer:**
> The process follows in the sequence
> * App initialization
> * Routing
> * Instantiate and execute controller
> * Locate and invoke controller action
> * Instantiate and render view

</details>

<details>
  <summary>4.What do you mean by Routing in MVC?</summary>
  
> **Answer:**
> Routing is a pattern matching mechanism of incoming requests to the URL patterns which are registered in route table.

</details>

<details>
  <summary>5. What are Actions in MVC?</summary>
  
> **Answer:**
> Actions are the methods in Controller class which is responsible for returning the view or json data. Action will mainly have the return type - "ActionResult" and it will be invoked from method : "InvokeAction()" called by controller.

</details>

<details>
  <summary>6. What is the difference between ViewBag and ViewData in MVC? Explain TempData in MVC. </summary>
  
> **Answer:**
> ViewBag is a wrapper around ViewData, which allows to create dynamic properties. Advantage of viewbag over viewdata will be:
> * In ViewBag no need to typecast the objects as in ViewData.
> * ViewBag will take advantage of dynamic keyword. But before using ViewBag we have to keep in mind that ViewBag is slower than ViewData.
> TempData is a key-value pair like ViewData, but derived from “TempDataDictionary” class. It is used when the data is to be used in two consecutive requests, this could be between the actions or between the controllers.

</details>

<details>
  <summary>7. What is Layout in MVC?</summary>
  
> **Answer:**
> Layout Views are similar to master pages in traditional web forms. This is used to set the common look across multiple Views, if the layout is specified for these specific Views.

</details>

<details>
  <summary>8. Explain Sections in MVC.</summary>
  
> **Answer:**
> Section are the part of HTML which is to be rendered in layout View. In Layout View we will use the `@RenderSection("SectionName")` syntax for rendering the HTML.
> If any child page does not have the section defined then error will be thrown. So to avoid that we can make section not required by `@RenderSection(SectionName, required: false)`

</details>

## WebAPI

<details>
  <summary>1. What is the difference between MVC and WebAPI in ASP.NET Core?</summary>
  
> **Answer:**
> * We can use the MVC for developing the Web application that replies as both data and views but the Web API is used for generating the HTTP services that replies only as data
> * In the Web API the request performs tracing with the actions depending on the HTTP services but the MVC request performs tracing with the action name.
> * The Web API returns the data in various formats, such as JSON, XML and other format based on the accept header of the request. But the MVC returns the data in the JSON format by using JSONResult
> * The Web API supports content negotiation, self hosting. All these are not supported by the MVC
> * The Web API helps the creation of RESTful services over the .Net Core but the MVC does not support.

</details>

<details>
  <summary>2. What is SOAP?</summary>
  
> **Answer:**
> SOAP is a simple XML-based protocol that enables applications to exchange information over HTTP. SOAP provides a way to communicate between applications that are running on different operating systems, with different technologies and programming languages.

</details>

<details>
  <summary>3. What is REST?</summary>

> **Answer:**
>
> REST is acronym for **RE**presentational **S**tate **T**ransfer.
> It is an architecture style for designing loosely coupled applications over HTTP, that is often used in the development of web services. REST does not enforce any rule regarding how it should be implemented at lower level, it just put high level design guidelines and leave you to think of your own implementation.

</details>
