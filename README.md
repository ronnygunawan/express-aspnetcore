# ASPEX - Asp.Net Core Express, A wrapper for idiots

### Hello World

```cs
var app = new WebApp();
app.MapGet("/", ctx => ctx.Response.WriteAsync("Hello world."));
app.Run();
```

### Method-level Dependency Injection
```cs
app.AddTransient<IService, Service>();
app.MapGet("/people/{name}", (HttpResponse res, IService svc, string name) => res.WriteJsonAsync(svc.GetPerson(name));
app.MapPost("/people", (HttpResponse res, IService svc, Payload body) => {
    await svc.AddPerson(body);
	res.StatusCode = 201;
});
```

### Subroutes
```cs
app["home"].Map(home => {
    home.MapGet(...);
	...
});
```

### This project is a work in progress
Currently not supported:
- Rendering Razor views and Razor pages
- Blazor
