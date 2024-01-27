# Interview Questions

## Fundamentals

<details>
  <summary>1. What is ASP.NET?</summary>

> **Answer:**
>ASP.NET is a free web framework for building great websites and web applications using HTML, CSS, and JavaScript. You can also create Web APIs and use real-time technologies like Web Sockets.

</details>

## MVC

<details>
  <summary>1. Describe MVC architectural pattern</summary>
  
> **Answer:**
> The Model-View-Controller (MVC) architectural pattern separates an application into three main components: the model, the view, and the controller.
> MVC is a standard design pattern that many developers are familiar with. Some types of Web applications will benefit from the MVC framework. Others will continue to use the traditional ASP.NET application pattern that is based on Web Forms and postbacks. Other types of Web applications will combine the two approaches; neither approach excludes the other.

</details>

<details>
  <summary>2. Describe 3 main components of MVC architectural pattern</summary>
  
> **Answer:**
> 1) **Models**: Model objects are the parts of the application that implement the logic for the application s data domain. Often, model objects retrieve and store model state in a database. For example, a Product object might retrieve information from a database, operate on it, and then write updated information back to a Products table in SQL Server;

> 2) **Views**: Views are the components that display the application s user interface (UI). Typically, this UI is created from the model data. An example would be an edit view of a Products table that displays text boxes, drop-down lists, and check boxes based on the current state of a Products object;

> 3) **Controllers**: Controllers are the components that handle user interaction, work with the model, and ultimately select a view to render that displays UI. In an MVC application, the view only displays information; the controller handles and responds to user input and interaction. For example, the controller handles query-string values, and passes these values to the model, which in turn queries the database by using the values.

</details>

<details>
  <summary>3. Explain the advantages of ASP.Net MVC over ASP.NET</summary>
  
> **Answer:**
> 1) Provides a clean separation of concerns among UI (Presentation layer), model (Transfer objects/Domain Objects/Entities) and Business Logic (Controller);
> 2) Easy to UNIT Test;
> 3) Improved reusability of model and views. We can have multiple views which can point to the same model and vice versa;
> 4) Improved structuring of the code.

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
  <summary>1. What is ASP.NET Web API?</summary>
  
> **Answer:**
> The ASP.NET Web API is an extensible framework for building HTTP based services that can be accessed in different applications on different platforms such as web, windows, mobile etc. It works more or less the same way as ASP.NET MVC web application except that it sends data as a response instead of html view. It is like a webservice or WCF service but the exception is that it only supports HTTP protocol.

</details>

<details>
  <summary>2. Why ASP.NET Web API?</summary>
  
> **Answer:**
> 1) ASP.NET Web API is an ideal platform for building RESTful services.
> 2) ASP.NET Web API is built on top of ASP.NET and supports ASP.NET request/response pipeline
> 3) ASP.NET Web API maps HTTP verbs to method names.
> 4) ASP.NET Web API supports different formats of response data. Built-in support for JSON, XML, BSON format.
> 5) ASP.NET Web API can be hosted in IIS, Self-hosted or other web server that supports .NET 4.0+.
> 6) ASP.NET Web API framework includes HttpClient to communicate with Web API server. HttpClient can be used in ASP.MVC server side, Windows Form application, Console application or other apps.

</details>

<details>
  <summary>3. What is the difference between MVC and Web API in ASP.NET?</summary>
  
> **Answer:**
> * We can use the MVC for developing the Web application that replies as both data and views but the Web API is used for generating the HTTP services that replies only as data;
> * In the Web API the request performs tracing with the actions depending on the HTTP services but the MVC request performs tracing with the action name;
> * The Web API returns the data in various formats, such as JSON, XML and other format based on the accept header of the request. But the MVC returns the data in the JSON format by using JSONResult;
> * The Web API supports content negotiation, self hosting. All these are not supported by the MVC;
> * The Web API includes the various features of the MVC, such as routing, model binding but these features are different and are defined in the "System.Web.Http" assembly. And the MVC features are defined in the " System.Web.Mvc" assembly;
> * The Web API helps the creation of RESTful services over the .Net Framework but the MVC does not support.

</details>

<details>
  <summary>4. Which .NET framework supports Web API?</summary>
  
> **Answer:**
> NET 4.0 and above version supports web API.

</details>

<details>
  <summary>5. What is SOAP?</summary>
  
> **Answer:**
> SOAP is a simple XML-based protocol that enables applications to exchange information over HTTP. SOAP provides a way to communicate between applications that are running on different operating systems, with different technologies and programming languages.

</details>

<details>
  <summary>6. What is REST?</summary>

> **Answer:**
>
> REST is acronym for **RE**presentational **S**tate **T**ransfer.
> It is an architecture style for designing loosely coupled applications over HTTP, that is often used in the development of web services. REST does not enforce any rule regarding how it should be implemented at lower level, it just put high level design guidelines and leave you to think of your own implementation.

</details>
