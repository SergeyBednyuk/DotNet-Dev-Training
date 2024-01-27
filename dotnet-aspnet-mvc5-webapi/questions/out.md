# Exam questions

## Fundamentals

<details>
  <summary>1. What is Razor View Engine In ASP.NET MVC?</summary>
  
> **Answer:**
> Razor View engine is a markup syntax which helps us to write HTML and server-side code in web pages using C# or VB.NET. It is server-side markup language however it is not at all a programming language.

>Razor is a templating engine and ASP.NET MVC has implemented a view engine which allows us to use Razor inside of an MVC application to produce HTML. However, Razor does not have any ties with ASP.NET MVC.

</details>

<details>
  <summary>2. View Model in ASP.Net MVC. What and why?</summary>
  
> **Answer:**
> View Model is a plain class with properties, which is used to bind it to strongly typed view. The view model in asp.net mvc represent only the data we want to display on view whether it is used for displaying or for taking input from view. 
> If we want to display more than one model on view in asp.net mvc then we need to create a new view model.
> View Model can have the validation rules defined for its properties using data annotations.

</details>

<details>
  <summary>3. What basic folders do we have in an ASP.NET MVC project without Areas? What are they for?</summary>
  
> **Answer:**
> 1) **App_Data** can be used to store some application’s data;
> 2) **App_Start** contains configuration classes: RouteConfig, BundleConfig, etc.;
> 3) **Content** is a publicly accessible folder for static files, such as CSS files, images, etc., but not scripts;
> 4) **Controllers** is a default folder for application controllers;
> 5) **Scripts** is a publicly accessible folder for JavaScript files;
> 6) **Views**: The folder contains a folder for every controller, plus a special folder Shared for views used by multiple views/controllers. For example, if we have a controller called HomeController, we will have a Home subfolder here with all the views related to HomeController.

</details>

## MVC

<details>
  <summary>1. What are HTML Helpers in MVC?</summary>
  
> **Answer:**
> HTML Helpers are like controls in traditional web forms. But HTML helpers are more lightweight compared to web controls as it does not hold viewstate and events. HTML Helpers returns the HTML string which can be directly rendered to HTML page. Custom HTML Helpers also can be created by overriding "HtmlHelper" class.

</details>

<details>
  <summary>2. What are AJAX Helpers in MVC?</summary>
  
> **Answer:**
> AJAX Helpers are used to create AJAX enabled elements like as Ajax enabled forms and links which performs the request asynchronously.

</details>

<details>
  <summary>3. What is the difference between asynchronous and synchronous actions? When would you use asynchronous actions?</summary>
  
> **Answer:**
> Asynchronous actions won’t block the executing thread. Using asynchronous actions can increase the throughput of a system if you use such a pattern for I/O operations, but it won’t help with CPU-bound operations.

</details>

<details>
  <summary>4. What is Separation of Concerns in ASP.NET ASP.Net MVC?</summary>
  
> **Answer:**
> It is the process of breaking the program into various distinct features which overlaps in functionality as little as possible. ASP.Net MVC pattern concerns on separating the content from presentation and data-processing from content.

</details>

<details>
  <summary>5. What is the recommended approach for ASP.NET MVC to globally intercept exceptions? What other functionality can be implemented with the approach?</summary>
  
> **Answer:**
> You can create a custom exception filter to intercept and log unhandled exceptions.
> To intercept exceptions globally, the filter should be registered in GlobalFilterCollection (usually in _~/App_Start/FilterConfig_). Authentication, authorization, custom action filters, logging, and action result transformation can be done with the same approach.

</details>

<details>
  <summary>6. What is Attribute Routing in ASP.Net MVC 5?</summary>
  
> **Answer:**
> ASP.NET MVC5 and WEB API 2 supports a new type of routing, called attribute routing. In this routing, attributes are used to define routes. Attribute routing provides you more control over the URIs by defining routes directly on actions and controllers in your ASP.NET MVC application and WEB API
>Attribute Routing can be defined at controller level or at Action level like :

```csharp
[Route("{action = TestCategoryList}")] - Controller Level
[Route("customers/{TestCategoryId:int:min(10)}")] - Action Level
```

>You can also add a _RoutePrefix_ Attribute on the controller if each of the controller actions within that controller shares a particular route prefix.

</details>

<details>
  <summary>7. When to use Attribute Routing?</summary>
  
> **Answer:**
> The convention-based routing is complex to support certain URI patterns that are common in RESTful APIs. But by using attribute routing you can define these URI patterns very easily.
>For example, resources often contain child resources like Clients have orders, movies have actors, books have authors and so on. It’s natural to create URIs that reflects these relations like as: /clients/1/orders
>This type of URI is difficult to create using convention-based routing. Although it can be done, the results don’t scale well if you have many controllers or resource types.
>
>With attribute routing, it’s pretty much easy to define a route for this URI. You simply add an attribute to the controller action as:

```csharp
[Route("clients/{clientId}/orders")] 
public IEnumerable GetOrdersByClient(int clientId) 
{ 
//TODO: Implementation
}
```

</details>

<details>
  <summary>8. How to enable Attribute Routing in ASP.NET MVC 5?</summary>
  
> **Answer:**
> Enabling attribute routing in your ASP.NET MVC 5 application is simple, just add a call to routes.`MapMvcAttributeRoutes()` method with in `RegisterRoutes()` method of RouteConfig.cs file.

```csharp
public class RouteConfig
{
 public static void RegisterRoutes(RouteCollection routes)
 {
 routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

 //enabling attribute routing
 routes.MapMvcAttributeRoutes();
 }
}
```

>You can also combine attribute routing with convention-based routing.

```csharp
public class RouteConfig
{
 public static void RegisterRoutes(RouteCollection routes)
 {
 routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

 //enabling attribute routing
 routes.MapMvcAttributeRoutes();

 //convention-based routing
 /routes.MapRoute(
 name: "Default",
 url: "{controller}/{action}/{id}",
 defaults: new { controller = "Home", action = "Index", id = UrlParameter.Optional });
 }
}
```

</details>

<details>
  <summary>9. What is the most appropriate lifetime for a database connection/ORM context in an ASP.NET MVC application?</summary>
  
> **Answer:**
> The lifetime should be the same as the request, because usually requests don’t live very long. Where it’s possible to wrap the whole request in one transaction, this can help comply with ACID principles.

</details>

<details>
  <summary>10. What is Partial views in ASP.NET MVC?</summary>
  
> **Answer:**
>A partial view is a view that is rendered within another view. The HTML output generated by executing the partial view is rendered into the calling (or parent) view. Like views, partial views use the .cshtml file extension.

</details>

<details>
  <summary>11. When to use partial views in ASP.NET MVC?</summary>
  
> **Answer:**
> * Partial views are an effective way of breaking up large views into smaller components. They can reduce duplication of view content and allow view elements to be reused. Common layout elements should be specified in _Layout.cshtml. Non-layout reusable content can be encapsulated into partial views;
> * If you have a complex page made up of several logical pieces, it can be helpful to work with each piece as its own partial view. Each piece of the page can be viewed in isolation from the rest of the page, and the view for the page itself becomes much simpler since it only contains the overall page structure and calls to render the partial views.

</details>

<details>
  <summary>12. What is Layout View in ASP.NET MVC?</summary>
  
> **Answer:**
> An application may contain a specific UI portion that remains the same throughout the application, such as header, left navigation bar, right bar, or footer section. ASP.NET MVC introduced a Layout view which contains these common UI portions so that we don't have to write the same code in every page. The layout view is the same as the master page of the ASP.NET webform application.
>
>The layout view allows you to define a common site template, which can be inherited in multiple views to provide a consistent look and feel in multiple pages of an application. The layout view eliminates duplicate coding and enhances development speed and easy maintenance.
>
>The layout view has the same extension as other views, .cshtml or .vbhtml. Layout views are shared with multiple views, so it must be stored in the Shared folder. By default, a layout view _Layout.cshtml is created when you Create MVC application using Visual Studio

</details>

<details>
  <summary>13. By default, you have the master page in your application <code>~/Views/Shared/_Layout.cshtml</code> and you’ve created a new one <code>~/Views/Shared/_LayoutV2.cshtml</code>. How do you apply the new master page to the whole application, except pages with a non-default layout?</summary>
  
> **Answer:**
> You have to adjust the file ~/Views/_ViewStart.cshtml

```csharp
@{
    Layout = "~/Views/Shared/_LayoutV2.cshtml";
}
```

</details>

<details>
  <summary>14. What are the Filters in ASP.NET MVC?</summary>
  
> **Answer:**
> In ASP.NET MVC, controllers define action methods that usually have a one-to-one relationship with possible user interactions, but sometimes you want to perform logic either before an action method is called or after an action method runs.
>
>To support this, ASP.NET MVC provides filters. Filters are custom classes that provide both a declarative and programmatic means to add pre-action and post-action behavior to controller action methods. \
>Filters provide a way for cross-cutting concerns (logging, authorization, and caching).

</details>

<details>
  <summary>15. Describe types of Filters in ASP.NET MVC and their Sequence of Execution</summary>
  
> **Answer:**
> There are five types of Filters in ASP.NET MVC 5:
> * **Authentication Filters**. \
> Authentication filter runs before any other filter or action method. Authentication confirms that you are a valid or invalid user. The filters implement the `IAuthenticationFilter` interface; 
> * **Authorization Filters**. \
> The AuthorizeAttribute and RequireHttpsAttribute are examples of Authorization Filters. Authorization Filters are responsible for checking User Access; these implement the `IAuthorizationFilterinterface` in the framework. These filters used to implement authentication and authorization for controller actions. For example, the Authorize filter is an example of an Authorization filter;
> * **Action Filters**. \
>Action Filter is an attribute that you can apply to a controller action or an entire controller. This filter will be called before and after the action starts executing and after the action has executed. \
>Action filters implement the `IActionFilter` interface that has two methods OnActionExecuting andOnActionExecuted. OnActionExecuting runs before the Action and gives an opportunity to cancel the Action call. These filters contain logic that is executed before and after a controller action executes, you can use an action filter, for instance, to modify the view data that a controller action returns;
> * **Result Filters**. \
>The OutputCacheAttribute class is an example of Result Filters. These filters implement the `IResultFilter` interface which like the `IActionFilter` has OnResultExecuting and OnResultExecuted. The filters contain logic that is executed before and after a view result is executed. Like if you want to modify a view result right before the view is rendered to the browser;
> * **ExceptionFilters**. \
> The HandleErrorAttribute class is an example of ExceptionFilters. These implement the `IExceptionFilter` interface and they execute if there are any unhandled exceptions thrown during the execution pipeline. These filters can be used as an exception filter to handle errors raised by either your controller actions or controller action results.
>
>Filters are executed in the order listed above. For example, authorization filters are always executed before action filters and exception filters are always executed after every other type of filter.

</details>

<details>
  <summary>16. Output Caching in ASP.NET MVC. What and why?</summary>
  
> **Answer:**
> Caching is a technique which stores something in memory that is being used frequently to provide better performance. In ASP.NET MVC, OutputCache attribute is used for applying Caching. OutputCheching will store the output of a Controller in memory and if any other request comes for the same, it will return it from cache result.

>We need caching in many different scenarios to improve the performance of ASP.NET MVC application. For example, you have an ASP.NET MVC application, which displays a list employees. Now when these records are retrieved from the database by executing a database query each and every time a user invokes the controller action it returns the Index view. \
>Hence you can take advantage of the output cache to avoid executing a database query every time a user invokes the same controller action. In this case, the view will be retrieved from the cache instead of being regenerated from the controller action.

>Caching enables you to avoid performing redundant work on the server.

</details>

<details>
  <summary>17. How to enable Output Caching in ASP.NET MVC?</summary>
  
> **Answer:**
> You enable output caching by adding an [OutputCache] attribute to either an individual controller action or an entire controller class.

</details>

<details>
  <summary>18. Output Cache in ASP.NET MVC. Where Content is Cached and how to manage the location?</summary>
  
> **Answer:**
> By default, when you use the [OutputCache] attribute, content is cached in three locations: the web server, any proxy servers, and the web browser. You can control exactly where content is cached by modifying the Location property of the [OutputCache] attribute.

>You can set the Location property to any one of the following values:
> * Any;
> * Client;
> * Downstream;
> * Server;
> * None;
> * ServerAndClient.

>By default, the Location property has the value Any. However, there are situations in which you might want to cache only on the browser or only on the server. For example, if you are caching information that is personalized for each user then you should not cache the information on the server. If you are displaying different information to different users then you should cache the information only on the client.

</details>

<details>
  <summary>19. Areas in ASP.NET MVC what and why?</summary>
  
> **Answer:**
> The large ASP.NET MVC application includes many controllers, views, and model classes. So it can be difficult to maintain it with the default ASP.NET MVC project structure. ASP.NET MVC introduced a new feature called _Area_ for this. _Area_ allows us to partition the large application into smaller units where each unit contains a separate MVC folder structure, same as the default MVC folder structure. \
>We can use Areas concept for organizing project in better manageable way. So for example you have 30 controllers in your projects, rather then working on single controller folder, we can classify the module wise controllers and separate it in different areas.

>The characteristics of Areas:
> * An MVC application can have any number of Areas;
> * Each Area has its own controllers, models, and views;
> * Physically, Areas are put under separate folders;
> * Areas are useful in managing big web applications;
> * A web application project can also use Areas from different projects;
> * Using Areas, multiple developers can work on the same web application project;
> * Areas in MVC are used for modular development.

</details>

<details>
  <summary>20. Bundling and Minification what and why?</summary>
  
> **Answer:**
> Bundling and minification are two techniques to improve request load time. Bundling and minification improves load time by reducing the number of requests to the server and reducing the size of requested assets (such as CSS and JavaScript.)

> **Bundling** - makes it easy to combine or bundle multiple files into a single file. You can create CSS, JavaScript and other bundles. Fewer files means fewer HTTP requests and that can improve first page load performance.

> **Minification** - performs a variety of different code optimizations to scripts or css, such as removing unnecessary white space and comments and shortening variable names to one character. Consider the following JavaScript function:

```javascript
AddAltToImg = function (imageTagAndImageID, imageContext) {
    ///<signature>
    ///<summary> Adds an alt tab to the image
    // </summary>
    //<param name="imgElement" type="String">The image selector.</param>
    //<param name="ContextForImage" type="String">The image context.</param>
    ///</signature>
    var imageElement = $(imageTagAndImageID, imageContext);
    imageElement.attr('alt', imageElement.attr('id').replace(/ID/, ''));
}
```

>After minification, the function is reduced to the following:

```javascript
AddAltToImg = function (n, t) { var i = $(n, t); i.attr("alt", i.attr("id").replace(/ID/, "")) }
```

>In addition to removing the comments and unnecessary whitespace, the following parameters and variable names were renamed (shortened) as follows:
> - **imageTagAndImageID** -> renamed to **n**;
> - **imageContext** -> renamed to **t**;
> - **imageElement** -> renamed to **i**.

</details>

## WebAPI

<details>
  <summary>1. How to enable Attribute Routing in ASP.NET Web API 2?</summary>
  
> **Answer:**
> To enable attribute routing, call `MapHttpAttributeRoutes` during configuration. This extension method is defined in the `System.Web.Http.HttpConfigurationExtensions` class.

```csharp
using System.Web.Http;

namespace WebApplication
{
    public static class WebApiConfig
    {
        public static void Register(HttpConfiguration config)
        {
            // Web API routes
            config.MapHttpAttributeRoutes();

            // Other Web API configuration not shown.
        }
    }
}
```

>Attribute routing can be combined with convention-based routing. To define convention-based routes, call the MapHttpRoute method.

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        // Attribute routing.
        config.MapHttpAttributeRoutes();

        // Convention-based routing.
        config.Routes.MapHttpRoute(
            name: "DefaultApi",
            routeTemplate: "api/{controller}/{id}",
            defaults: new { id = RouteParameter.Optional }
        );
    }
}
```

</details>

<details>
  <summary>2. What are main return types supported in Web API?</summary>
  
> **Answer:**
> A Web API controller action can return following values:
> * **Void** – it will return empty content (204 No Content);
> * **HttpResponseMessage** - it will convert the response directly to an HTTP response message;
> * **IHttpActionResult** - internally calls `ExecuteAsync` to create an `HttpResponseMessage`, then converts to an HTTP response message;
> * **Other types** - you can write the serialized return value into the response body.

</details>


## Other

<details>
  <summary>1. What are the advantages of using IoC containers in an application?</summary>

> **Answer:**
> * The lifetime of every object can be managed externally;
> * Objects are not responsible for creating services and providing dependencies;
> * Changes to a dependency list won’t affect an object using the service;
> * The same instance can be shared by several unrelated consumers;
> * Services provide contracts, so implementation can be changed in the future.

</details>

<details>
  <summary>2. What is SignalR? How it works internally?</summary>

> **Answer:**
> ASP.NET SignalR is a library for ASP.NET developers that simplifies the process of adding real-time web functionality to applications. Real-time web functionality is the ability to have server code push content to connected clients instantly as it becomes available, rather than having the server wait for a client to request new data.
> SignalR provides a simple API for creating server-to-client remote procedure calls (RPC) that call JavaScript functions in client browsers (and other client platforms) from server-side .NET code. SignalR also includes API for connection management (for instance, connect and disconnect events), and grouping connections.
> 
>SignalR applications can scale out to thousands of clients using built-in, and third-party scale-out providers.
>
>Built-in providers include:
> * Service Bus;
> * SQL Server;
> * Redis.
>
>Third-party providers include:
> * NCache.
>
> There are following built in transports:
> * WebSockets;
> * Server Sent Events;
> * Forever Frame;
> * Ajax Long polling.

</details>
