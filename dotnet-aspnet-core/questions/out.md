# Exam questions

## Fundamentals

<details>
  <summary>1. What are the differences between ASP.NET and ASP.NET Core</summary>
  
> **Answer:**
> * ASP.NET Core is Cross Platform;
> * ASP.NET Core is Cloud Ready;
> * ASP.NET Core doesn't require IIS for hosting;
> * ASP.NET Core includes a simple built-in container that supports constructor injection by default, and ше makes certain services available through DI;
> * ASP.NET Core has no App_Start, App_Data, Global.asax and root web.config file. App_Start is replaced by Startup.cs and web.config is replaced by appsetting.json. There is also a new configuration system, where JSON is preferred over XML for configuration settings;
> * ASP.NET Core uses wwwroot folder for static files;
> * ASP.NET Core MVC TagHelper allows to enable server-side code to participate in creating and rendering HTML elements in Razor files;
> * ASP.NET Core MVC Supports RESTful style routes with attribute routing;
> * ASP.NET Core came up with storing all the packages related to its development in Users folder and while creating ASP.NET Core applications, Visual Studio will reference them from Users folder.

</details>

<details>
  <summary>2. What <code>ConfigureServices()</code> method does in Startup.cs?</summary>

> **Answer:**
> This method is optional. It is the place to add services required by the application. For example, if you wish to use Entity Framework in your application then you can add in this method.
```cs
public void ConfigureServices(IServiceCollection services)  
{
    services.Configure<AppSettings>(Configuration.GetSubKey("AppSettings"));
    services.AddEntityFramework()
            .AddSqlServer()
            .AddDbContext<SchoolContext>();
    // Add MVC services to the services container.
    services.AddMvc();
}
```

</details>

<details>
  <summary>3. What <code>Configure()</code> method does in Startup.cs?</summary>

> **Answer:**
> The Configure method is used to specify how the ASP.NET application will respond to HTTP requests. 
> The request pipeline is configured by adding middleware components to an IApplicationBuilder instance that is provided by dependency injection. 
> There are some built-in middlewares for error handling, authentication, routing, session and diagnostic purpose.

</details>

<details>
  <summary>4. How to Configure services without Startup.cs?</summary>

> **Answer:**
> To configure services and the request processing pipeline without using a Startup class, call **ConfigureServices** and **Configure** convenience methods on the host builder. Multiple calls to **ConfigureServices** append to one another. If multiple **Configure** method calls exist, the last **Configure** call is used.
```cs
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureAppConfiguration((hostingContext, config) =>
            {
            })
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.ConfigureServices(services =>
                {
                    services.AddControllersWithViews();
                })
                .Configure(app =>
                {
                    var loggerFactory = app.ApplicationServices
                        .GetRequiredService<ILoggerFactory>();
                    var logger = loggerFactory.CreateLogger<Program>();
                    var env = app.ApplicationServices.GetRequiredService<IWebHostEnvironment>();
                    var config = app.ApplicationServices.GetRequiredService<IConfiguration>();

                    logger.LogInformation("Logged in Configure");

                    if (env.IsDevelopment())
                    {
                        app.UseDeveloperExceptionPage();
                    }
                    else
                    {
                        app.UseExceptionHandler("/Home/Error");
                        app.UseHsts();
                    }

                    var configValue = config["MyConfigKey"];
                });
            });
        });
}
```

</details>

<details>
  <summary>5. What is the difference between services.AddSingletone, services.AddTransient and service.AddScope methods in Asp.Net Core?</summary>

> **Answer:**
> ASP.NET Core out of the box supports dependency injection. These 3 methods allows to register the dependency. However, they offers different lifetime for registered service. 
> Transient objects are created for every request (when requested). This lifetime works best for lightweight, stateless services. 
> Scoped objects are the same within a request, but different across different requests.
> Singleton objects are created the first time they’re requested (or when ConfigureServices is run and an instance is specified with the service registration).

</details>

<details>
  <summary>6. What is WebListener?</summary>

> **Answer:**
> **WebListener** is **windows-only HTTP / Web Server** for ASP.NET Core that allows you to expose the server directly to the Internet without needing to use IIS. WebListener is built on top of Http.Sys ( the same mature technology that also powers IIS' HTTP Listener) as is as such very feature rich and provides protection against various attacks.

</details>

<details>
  <summary>7. What is Kestrel?</summary>

> **Answer:**
> **Kestrel** is a **cross-platform Web Server** for ASP.NET Core that is designed to be run behind a proxy (for example IIS or Nginx) and should not be deployed directly facing the Internetis. It's included by default in ASP.NET Core project templates. If your application accepts requests only from an internal network, you can use Kestrel by itself. If you expose your application to the Internet, you must use IIS, Nginx, or Apache as a reverse proxy server. A reverse proxy server receives HTTP requests from the Internet and forwards them to Kestrel after some preliminary handling. The most important reason for using a reverse proxy for edge deployments (exposed to traffic from the Internet) is security. \
>Kestrel is relatively new and does not have a full complement of defenses against attacks. It's also not as feature rich as **WebListener** and comes with timeout limits, size limits and concurrent user limits.
</details>

<details>
  <summary>8. What is a Host and what’s the importance of Host in ASP.NET Core application?</summary>

> **Answer:**
> ASP.NET Core apps require a host in which to execute. The host is responsible for application startup and lifetime management. Other responsibilities include ensuring the application services and the server are available and properly configured. Don’t confuse yourself with a Server. The host is responsible for starting the app and its management, where the server is responsible for accepting HTTP requests. The host is configured to use a particular server; the server is unaware of its host.

</details>

<details>
  <summary>9. How does Configuration work in ASP.NET Core?</summary>

> **Answer:**
> ASP.NET Core supports many methods of configuration. In ASP.NET Core application, the configuration is stored in name-value pairs and it can be read at runtime from various parts of the application. The name-value pairs may be grouped into multi-level hierarchy. The application configuration data may come from:
> 
> * File, such as JSON, XML, INI
> * Environment variables
> * Command Line arguments
> * An in-memory collection
> * Custom providers
> 
> Configuration System in ASP.NET Core is restructured from the older version of ASP.NET. The older version uses "System.Configuration" namespace and is able to read XML configuration file such as web.config. The new configuration model can be accessed to the key/value based settings and it can retrieve various sources, such as JSON, XML and INI.
> Retrieving of the configuration with DI container
> 
> appsettings.json
```json
  {
    "status" : "This Status read from appSettings.json file",  
    "ConnectionStrings": {  
      "DefaultConnection": "Server=.\\sqlexpress;Database=Test;Trusted_Connection=True;MultipleActiveResultSets=true"  
    }  
  }
```
>
> HomeController.cs
> 
```cs
  using Microsoft.AspNetCore.Mvc;  
  using Microsoft.Extensions.Configuration;  
  
  public class HomeController : Controller  
  {  
    IConfiguration _configuration;  
    public HomeController(IConfiguration configuration)  
    {  
      _configuration = configuration;  
    }  
    [Route("home/index")]  
    public IActionResult Index()  
    {  
      var connectionString = _configuration["ConnectionStrings:DefaultConnection"];  
      return View();  
    }  
  }
```

</details>

<details>
  <summary>10. How to handle 404 error or any other HTTP status code errors in ASP.NET Core?</summary>
  
> **Answer:**
> 1st approach. Define a custom middleware via `app.Use()` which checks for status code value in response object. And if it is 404 then it redirects to Home controller
```cs
  app.Use(async (context, next) =>
  {
    await next();
    if (context.Response.StatusCode == 404)
    {
      context.Request.Path = "/Home"; 
      await next();
    }
  });
```
>
> 2nd approach. Use a built-in middlware `StatusCodePagesMiddleware`. This middleware can be used to handle the response status code is between 400 and 600. This middleware allows to return a generic error response or allows you to also redirect to any controller action or another middleware.
 
</details>

<details>
  <summary>11. How built-in IoC container manages the lifetime of a registered service type in ASP.NET Core?</summary>
  
> **Answer:**
> Built-in IoC container automatically disposes a service instance based on the specified lifetime. \
>The built-in IoC container supports three kinds of lifetimes:
> - **Singleton**: IoC container will create and share a single instance of a service throughout the application's lifetime;
> - **Transient**: The IoC container will create a new instance of the specified service type every time you ask for it;
> - **Scoped**: IoC container will create an instance of the specified service type once per request and will be shared in a single request.

>The following example shows how to register a service with different lifetimes:
```cs
  public void ConfigureServices(IServiceCollection services)
  {
    services.Add(new ServiceDescriptor(typeof(ILog), new MyConsoleLogger()));    // singleton
    
    services.Add(new ServiceDescriptor(typeof(ILog), typeof(MyConsoleLogger), ServiceLifetime.Transient)); // Transient
    
    services.Add(new ServiceDescriptor(typeof(ILog), typeof(MyConsoleLogger), ServiceLifetime.Scoped));    // Scoped
  }
```
 
</details>

<details>
  <summary>12. What is <b>wwwroot</b> folder in ASP.NET Core and why it's being used for?</summary>
  
> **Answer:**
>  By default, the **wwwroot** folder in the ASP.NET Core project is treated as a web root folder. Static files can be stored in any folder under the web root and accessed with a relative path to that root. \

>In the standard ASP.NET application, static files can be served from the root folder of an application or any other folder under it. This has been changed in ASP.NET Core. Now, only those files that are in the web root - wwwroot folder can be served over an http request. All other files are blocked and cannot be served by default.

>Generally, there should be separate folders for the different types of static files such as JavaScript, CSS, Images, library scripts etc. in the **wwwroot** folder. You can access static files with base URL and file name. For example, we have _app.css_ file in _wwwroot\css\app.css_ and we can access it by calling _http://localhost:{port}/css/app.css_.

>Remember, you need to include a middleware for serving static files in the Configure method of Startup.cs.

</details>

<details>
  <summary>13. How to implement a custom middleware?</summary>

> **Answer:**
> * Using Run, Use and Map methods of the IApplicationBuilder instance
>
```cs
  public class Startup
  {
    public void Configure(IApplicationBuilder app)
    {
      app.Use(async (context, next) =>
      {
        var cultureQuery = context.Request.Query["culture"];
        if (!string.IsNullOrWhiteSpace(cultureQuery))
        {
        	var culture = new CultureInfo(cultureQuery);

        	CultureInfo.CurrentCulture = culture;
        	CultureInfo.CurrentUICulture = culture;
        }

        // Call the next delegate/middleware in the pipeline
        await next();
      });

      app.Run(async (context) =>
      {
        await context.Response.WriteAsync(
        	$"Hello {CultureInfo.CurrentCulture.DisplayName}");
      });

    }
  }
```
>
> * Using middleware class
>
```cs
  public class RequestCultureMiddleware
  {
    private readonly RequestDelegate _next;

    public RequestCultureMiddleware(RequestDelegate next)
    {
      _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
      var cultureQuery = context.Request.Query["culture"];
      if (!string.IsNullOrWhiteSpace(cultureQuery))
      {
        var culture = new CultureInfo(cultureQuery);

        CultureInfo.CurrentCulture = culture;
        CultureInfo.CurrentUICulture = culture;

      }

      // Call the next delegate/middleware in the pipeline
      await _next(context);
    }
  }

  public class Startup
  {
    public void Configure(IApplicationBuilder app)
    {
      app.UseMiddleware<RequestCultureMiddleware>();

      app.Run(async (context) =>
      {
        await context.Response.WriteAsync(
        	$"Hello {CultureInfo.CurrentCulture.DisplayName}");
      });

    }
  }
```

</details>

<details>
  <summary>14. Why ASP.NET Core filters are used for?</summary>
  
> **Answer:**
> Filters in ASP.NET Core allow code to be run before or after specific stages in the request processing pipeline.
>
>Custom filters can be created to handle cross-cutting concerns. Examples of cross-cutting concerns include error handling, caching, configuration, authorization, and logging. Filters avoid duplicating code. For example, an error handling exception filter could consolidate error handling.

</details>

<details>
  <summary>15. Describe types of Filters in ASP.NET Core and their Sequence of Execution</summary>
  
> **Answer:**
> Each filter type is executed at a different stage in the filter pipeline:
> * **Authorization filters** are used to determine whether the user is authorized for the request. Authorization filters short-circuit the pipeline if the request is not authorized.
>   - They are the first filters run in the filter pipeline;
>   - They control access to action methods;
>   - The filters have a before method, but no after method.

> * **Resource filters** are useful to short-circuit most of the pipeline. For example, a caching filter can avoid the rest of the pipeline on a cache hit.
>   - They implement either the `IResourceFilter` or `IAsyncResourceFilter` interface;
>   - Their execution wraps most of the filter pipeline;
>   - _OnResourceExecuting_ runs code before the rest of the filter pipeline. For example, _OnResourceExecuting_ runs code before model binding;
>   - _OnResourceExecuted_ runs code after the rest of the pipeline has completed;
>   - Only Authorization filters run before resource filters.

> * **Action filters** do not apply to Razor Pages. Razor Pages supports `IPageFilter` and `IAsyncPageFilter`.
>   - They implement either the `IActionFilter` or `IAsyncActionFilter` interface;
>   - They run code immediately before and after an action method is called;
>   - They can change the arguments passed into an action;
>   - The filters can change the result returned from the action;
>   - Action filters are not supported in Razor Pages.

> * **Exception filters** apply global policies to unhandled exceptions that occur before the response body has been written to.
>   - They implement `IExceptionFilter` or `IAsyncExceptionFilter` -> `OnException` or `OnExceptionAsync`;
>   - The filters don't have before and after events;
>   - They handle unhandled exceptions that occur in Razor Page or controller creation, model binding, action filters, or action methods;
> The filters do not catch exceptions that occur in resource filters, result filters, or MVC result execution.

> * **Result filters** run code immediately before and after the execution of action results. They run only when the action method has executed successfully. They are useful for logic that must surround view or formatter execution.
>   - The filters implement `IResultFilter` or `IAsyncResultFilter` interface;
>   - They also implement `IAlwaysRunResultFilter` or `IAsyncAlwaysRunResultFilter` interface;

</details>

<details>
  <summary>16. What is <code>IWebHostEnvironment</code> interface used for?</summary>
  
> **Answer:**
>  It is used to get information about the web hosting environment an application is running in.

>Properties:
> - _WebRootFileProvider_ - Gets or sets an `IFileProvider` pointing at `WebRootPath`;
> - _WebRootPath_ - Gets or sets the absolute path to the directory that contains the web-servable application content files.

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
  <summary>4. What is the recommended approach for ASP.NET Core MVC to globally intercept exceptions? What other functionality can be implemented with the approach?</summary>
  
> **Answer:**
>To intercept exceptions globally, the filter should be registered in Startup.ConfigureServices() as shown below:

```csharp
services.AddMvc(options => { options.Filters.Add(new ApiExceptionFilter()); });
```

>Authorization, custom action filters (sync and async), and action result transformation can be done with the same approach.

</details>

<details>
  <summary>5. What is Partial views in ASP.NET Core MVC?</summary>
  
> **Answer:**
>A partial view is a Razor markup file (.cshtml) without an @page directive that renders HTML output within another markup file's rendered output.
>The term partial view is used when developing either an MVC app, where markup files are called views, or a Razor Pages app, where markup files are called pages. This topic generically refers to MVC views and Razor Pages pages as markup files.

</details>

<details>
  <summary>6. When to use partial views in ASP.NET Core MVC?</summary>
  
> **Answer:**
>Partial views are an effective way to:
> * Break up large markup files into smaller components; \
>In a large, complex markup file composed of several logical pieces, there's an advantage to working with each piece isolated into a partial view. The code in the markup file is manageable because the markup only contains the overall page structure and references to partial views;
>
> * Reduce the duplication of common markup content across markup files. \
>When the same markup elements are used across markup files, a partial view removes the duplication of markup content into one partial view file. When the markup is changed in the partial view, it updates the rendered output of the markup files that use the partial view;
>
>Partial views shouldn't be used to maintain common layout elements. Common layout elements should be specified in _Layout.cshtml files. \
>Don't use a partial view where complex rendering logic or code execution is required to render the markup. Instead of a partial view, use a view component.

</details>

<details>
  <summary>7. Layout in ASP.NET Core MVC. What and why?</summary>
  
> **Answer:**
> Most web apps have a common layout that provides the user with a consistent experience as they navigate from page to page. The layout typically includes common user interface elements such as the app header, navigation or menu elements, and footer.
>
>Common HTML structures such as scripts and stylesheets are also frequently used by many pages within an app. All of these shared elements may be defined in a layout file, which can then be referenced by any view used within the app. Layouts reduce duplicate code in views. \
>By convention, the default layout for an ASP.NET Core app is named _Layout.cshtml. The layout files for new ASP.NET Core projects created with the templates are:
> * Razor Pages: Pages/Shared/_Layout.cshtml;
> * Controller with views: Views/Shared/_Layout.cshtml.
>
>The layout defines a top level template for views in the app. Apps don't require a layout. Apps can define more than one layout, with different views specifying different layouts.

</details>

<details>
  <summary>8. By default, you have the master page in your application <code>~/Views/Shared/_Layout.cshtml</code> and you’ve created a new one <code>~/Views/Shared/_LayoutV2.cshtml</code>. How do you apply the new master page to the whole application, except pages with a non-default layout in ASP.NET Core MVC?</summary>
  
> **Answer:**
> You have to adjust the file ~/Views/_ViewStart.cshtml

```csharp
@{
    Layout = "_LayoutV2";
}
```

</details>

<details>
  <summary>9. What is Model Binding in ASP.NET Core and how it works?</summary>
  
> **Answer:**
>Controllers and Razor pages work with data that comes from HTTP requests. \
>**Model Binding** - is a process of extracting data from HTTP request and providing them to the action method’s arguments. For example, route data may provide a record key, and posted form fields may provide values for the properties of the model. Writing code to retrieve each of these values and convert them from strings to .NET types would be tedious and error-prone. Model binding automates this process. The model binding system:
> * Retrieves data from various sources such as route data, form fields, and query strings;
> * Provides the data to controllers and Razor pages in method parameters and public properties;
> * Converts string data to .NET types;
> * Updates properties of complex types.

>Model binding tries to find values for the following kinds of targets:
> * Parameters of the controller action method that a request is routed to;
> * Parameters of the Razor Pages handler method that a request is routed to;
> * Public properties of a controller or PageModel class, if specified by attributes.

</details>

## WebAPI

<details>
  <summary>1. What are the advantages of using ASP.NET Core web API over ASP.NET Web API?</summary>
  
> **Answer:**
> * ASP.NET Core is an open-source, cross-platform framework for building modern, cloud-based web apps on Windows, macOS, and Linux;
> * The ASP.NET Core MVC controllers and web API controllers are unified;
> * Architected for testability;
> * Ability to develop and run on Windows, macOS, and Linux;
> * Open-source and community-focused;
> * Integration of modern, client-side frameworks and development workflows;
> * A cloud-ready, environment-based configuration system;
> * Built-in dependency injection;
> * A lightweight, high-performance, and modular HTTP request pipeline;
> * Ability to host on Kestrel, IIS, HTTP.sys, Nginx, Apache, and Docker;
> * Side-by-side versioning;
> * Tooling that simplifies modern web development.

</details>

<details>
  <summary>2. Describe controller action return types in ASP.NET Core web API?</summary>
  
> **Answer:**
> ASP.NET Core offers the following options for web API controller action return types:
> * **Specific type** - The simplest action returns a primitive or complex data type (for example, string or a custom object type). Following action returns a collection of custom _Product_ objects:
```csharp
[HttpGet]
public List<Product> Get() =>
    _repository.GetProducts();
```
> * **IActionResult** - is appropriate when multiple `ActionResult` return types are possible in an action. The `ActionResult` types represent various HTTP status codes. Any non-abstract class deriving from `ActionResult` qualifies as a valid return type. Some common return types in this category are _BadRequestResult (400)_, _NotFoundResult (404)_, and _OkObjectResult (200)_. Alternatively, convenience methods in the ControllerBase class can be used to return `ActionResult` types from an action. For example, `return BadRequest();` is a shorthand form of `return new BadRequestResult();`. \
>Because there are multiple return types and paths in this type of action, liberal use of the [ProducesResponseType] attribute is necessary. This attribute produces more descriptive response details for web API help pages generated by tools like Swagger. [ProducesResponseType] indicates the known types and HTTP status codes to be returned by the action;
>
> * **ActionResult&lt;T&gt;** - enables you to return a type deriving from `ActionResult` or return a specific type. `ActionResult<T>` offers the following benefits over the `IActionResult` type:
>	- The [ProducesResponseType] attribute's `Type` property can be excluded. For example, `[ProducesResponseType(200, Type = typeof(Product))]` is simplified to [ProducesResponseType(200)]. The action's expected return type is instead inferred from the `T` in `ActionResult<T>`.
>	- Implicit cast operators support the conversion of both `T` and `ActionResult` to `ActionResult<T>`. `T` converts to ObjectResult, which means `return new ObjectResult(T);` is simplified to `return T;`.
>>Most actions have a specific return type. Unexpected conditions can occur during action execution, in which case the specific type isn't returned. For example, an action's input parameter may fail model validation. In such a case, it's common to return the appropriate ActionResult type instead of the specific type.

</details>

<details>
  <summary>3. When to use custom formatters in ASP.NET Core Web API.</summary>
  
> **Answer:**
> Use a custom formatter to add support for a content type that isn't handled by the built-in formatters.

</details>

<details>
  <summary>4. I need to support specific formats for serializing and deserializing data in ASP.NET Core Web API. How can I achieve this?</summary>
  
> **Answer:**
> 1. For serializing data sent to the client, create a custom output formatter class.
> 2. For deserializing data received from the client, create a custom input formatter class.
> 3. Add instances of formatter classes to the `InputFormatters` and `OutputFormatters` collections in **MvcOptions**.

</details>

<details>
  <summary>5. How to create a custom formatter class in ASP.NET Core Web API?</summary>
  
> **Answer:**
> 1. Create and derive the class from the appropriate base class. (e.g `TextOutputFormatter` and `TextInputFormatter` for output and input formatters accordingly);
> 2. Specify valid media types and encodings in the constructor;
> 3. Override the `CanReadType` and `CanWriteType` methods for input and output formatters accordingly;
> 4. Override the `ReadRequestBodyAsync` and `WriteResponseBodyAsync` methods for input and output formatters accordingly.

>An example of output formatter:
```csharp
public class VcardOutputFormatter : TextOutputFormatter
{
    public VcardOutputFormatter()
    {
        SupportedMediaTypes.Add(MediaTypeHeaderValue.Parse("text/vcard"));

        SupportedEncodings.Add(Encoding.UTF8);
        SupportedEncodings.Add(Encoding.Unicode);
    }

    protected override bool CanWriteType(Type type)
    {
        return typeof(Contact).IsAssignableFrom(type) ||
            typeof(IEnumerable<Contact>).IsAssignableFrom(type);
    }

    public override async Task WriteResponseBodyAsync(
        OutputFormatterWriteContext context, Encoding selectedEncoding)
    {
        var httpContext = context.HttpContext;
        var serviceProvider = httpContext.RequestServices;

        var logger = serviceProvider.GetRequiredService<ILogger<VcardOutputFormatter>>();
        var buffer = new StringBuilder();

        if (context.Object is IEnumerable<Contact> contacts)
        {
            foreach (var contact in contacts)
            {
                FormatVcard(buffer, contact, logger);
            }
        }
        else
        {
            FormatVcard(buffer, (Contact)context.Object, logger);
        }

        await httpContext.Response.WriteAsync(buffer.ToString());
    }

    private static void FormatVcard(
        StringBuilder buffer, Contact contact, ILogger logger)
    {
        buffer.AppendLine("BEGIN:VCARD");
        buffer.AppendLine("VERSION:2.1");
        buffer.AppendLine($"N:{contact.LastName};{contact.FirstName}");
        buffer.AppendLine($"FN:{contact.FirstName} {contact.LastName}");
        buffer.AppendLine($"UID:{contact.Id}");
        buffer.AppendLine("END:VCARD");

        logger.LogInformation("Writing {FirstName} {LastName}",
            contact.FirstName, contact.LastName);
    }
}
```

</details>

## Other

<details>
  <summary>1. What is “Razor pages” in ASP.NET Core?</summary>

> **Answer:**
> Razor Pages is a new feature of ASP.NET Core that makes coding page-focused scenarios easier and more productive. With Razor Pages, you have this one Razor file (.cshtml), and the code for a single page lives inside of that file, and that file also represents the URL structure of the app (more about this later). Therefore, you got everything inside of one file, and it just works. However, you CAN separate your code to the code behind file with .cshtml.cs extension. You would usually have your view model and handlers (like action methods in MVC) in that file and handle the logic there. Of course, you could also have your view model moved to separate place. Since Razor Pages is part of the MVC stack, you can use anything that comes with MVC inside of our Razor Pages.

</details>

<details>
  <summary>2. What is SignalR? How it works internally?</summary>

> **Answer:**
> In ASP.NET Core SignalR is a cross-platform solution to add real-time features to web apps and more. It is an abstraction over a connection. It gives you two programming models over that connection (hubs and persistent connections). SignalR has a concept of transports, each transport decides how data is sent/received and how it connects and disconnects.
> 
> There are following built in transports:
> * WebSockets;
> * Server Sent Events;
> * Forever Frame;
> * Long polling.
>
>SignalR supports the following techniques for handling real-time communication (in order of graceful fallback):
> * WebSockets;
> * Server-Sent Events;
> * Ajax Long Polling.
>
> SignalR tries to choose the "best" connection supported by server and client (you can also force it to use a specific transport).

</details>
