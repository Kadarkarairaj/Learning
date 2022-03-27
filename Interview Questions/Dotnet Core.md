# .Net Core
https://www.enqos.com/blog/key-things-need-know-asp-net-core

C# Version History with Table format

https://www.tutorialsteacher.com/csharp/csharp-version-history

# What are the new Features in .NET 6
 - .NET 6 delivers the final parts of the .NET unification plan that started with .NET 5. 
 - .NET 6 unifies the SDK, base libraries, and runtime across mobile, desktop, IoT, and cloud apps
 - .NET 6 has comes with C# 10. Its new features reduces the amount code to be written
 - .NET 6 is the fastest full stack web framework, which lowers compute costs if you're running in the cloud
 - .NET 6 provides hot reload, crossgen2, ARM64 support

 # What are the new Features in  .NET 5
 - .NET 5 is next major release of .Net Core following 3.1. Microsoft removed "Core" in its name, also skipped Version 4 to avoid confusion between .NET Framework and .Net Core.
 - .NET 5 and later versions are the main implementations of .NET going forward. However, .NET framework 4.x is still supported.
 - .NET 5 comes with C# 9, ASP.NET Core 5.0.
 - There are performance improvements in Garbage Collections, System.Text.Json, Regular Expressions, etc.,
  
 # What are the difference between .NET Framework and .NET (or formerly .NET Core)
 - .NET Framework is windows only component
 - .NET (formerly .Net Core) is designed to be cross plotform.
 - .NET Core is light weight so It is well suited for Micro services.
 - .NET Core is high performance and scalable.

 # Difference between ASP.NET MVC vs ASP.NET Core MVC
 - ASP.NET Core has built-in support for dependency injection (DI). 
 - ASP.NET Core everything is decided on Middleware.
 - ASP.NET Core can run on cross platform
 - ASP.NET Core can run as framework independent.
  
 # what is TFM or Target Framework Moniker
 Target Framework Moniker is a standardized token format for specifying the target framework of a . NET app or library

# ASP.NET Core MVC Life Cycle

Http Request -> Middleware -> Routing -> Controller Initialization -> Action Method Execution -> 
Result Execution -> Data Result (or)
Result Execution -> View Result -> View Rendering  -> Http Response

## Depedency Injection
- ASP.NET Core has built-in support for dependency injection (DI). 
- In ASP.NET Core MVC, controllers can request needed services through their constructors.

Your app can also use dependency injection in view files, using the @inject directive

## Routing 

- Conventions based routing
- Attribute Routing

# ASP.NET MVC 5 Life Cycle

![ASP.NET MVC 5 Life Cycle](https://i0.wp.com/dotnettekki.com/wp-content/uploads/2018/05/mvc-page-lifecycle.jpg?w=684&ssl=1)

# Common Web Application Architectures

https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures

1. Monolithic
2. All-in-one Monolithic
- In this architecture, the entire logic of the application is contained in a single project, compiled to a single assembly, and deployed as a single unit
- A new ASP.NET Core project, whether created in Visual Studio or from the command line, starts out as a simple "all-in-one" monolith. It contains all of the behavior of the application, including presentation, business, and data access logic in a single project.
3. N-Layer Architecture
 - As applications grow in complexity, one way to manage that complexity is to break up the application according to its responsibilities or concerns
 - This approach follows the separation of concerns principle and can help keep a growing codebase organized so that developers can easily find where certain functionality is implemented.
 - Typical N-Layer architecures uses UI, BLL, DAL. 
4. Clean or Onion Arhitecture

5. Monolithic Applications and Containers

# Middleware
- In ASP.Net Core, Every HTTP Request is handled by set of request delegates. 
- Request delegates are used to build the app/request pipeline.
- Request delegates are configured using Run, Map, and Use extension methods
- An individual request delegate can be specified in-line as an anonymous method or it can be defined in a reusable class. 
- These reusable classes and in-line anonymous methods are middleware, also called middleware components.
- Each middleware component in the request pipeline is responsible for invoking the next component in the pipeline or short-circuiting the pipeline (Prevent a request processed by further middleware )

``` C#

// Middleware written using reusable methods and can be defined in a reusable class

app.Map("/map1/seg1", HandleMultiSeg);

static void HandleMultiSeg(IApplicationBuilder app)
{
    app.Run(async context =>
    {
        await context.Response.WriteAsync("Map Test 1");
    });
}

// Middleware written using in-line anonymous method
app.Run(async context =>
{
    await context.Response.WriteAsync("Hello from non-Map delegate. <p>");
});

```
# Transcient vs Scoped Vs Singleton
 - Transient objects are always different; a new instance is provided to every controller and every service.
 - Scoped objects are the same within a request, but different across different requests.
 - Singleton objects are the same for every object and every request.
