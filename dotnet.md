# .NET

## IIS

Internet Information Services
Web server runs on Microsoft windows

ASP.NET core 7.0 (8.0)
Azure cloud development
Xamerin
.Net 6
.Net Framework -> .Net Core
ASP.NET, C#, VB.NET, IIS, and Windows Server
MS SQL Database
WCF

## Razor Pages => New server-side web UI development

Razor is a templating engin ethat combines C# with HTML to build dynamic web content.

## Blazor => Client-side web UI development

Blazor is a component-based, single-page app framework for building client-side web app using .NET that works well with all modern browsers via WebAssembly for client-side Blazor.

## MVC => Maintaining an MVC app

## web API+ => RESTful HTTP services

## gRPC service => Contract-first services using Protocol Buffers

## SignalR => Bidirectional communication between servers and connected clients

## Entity Framework Core

- Don't use RemoveRange, ever!
```
// false
db.Table.RemoveRange(db.Table.Where(a => a.Price <= 0).ToList())

// true
db.Table.Where(a => a.Price <= 0).DeleteFromQuery()
```

- Never loop inside DbContext instance!
```
// false
using (AppDbContext db = new AppDbContext())
{
	// your code here
}

// true
foreach(var x in items)
{
	using (AppDbContext db = new AppDbContext())
	{
		// code here
	}
}
```
- Use ExecuteSqlCommand only when necessary
ExecuteSqlCommand is equivalent to executing raw SQL queries against the database where no entity tracking/validation is carried out by Entity framework.

- Avoid defining Foreign Keys on Model classes
- Name Your Tables

## LINQ
Language Integrated Query
LINQ queries, which are behind the scenes translated into SQL by calling methods `ToArray`, `ToList`, `FirstOrDefault` etc.

```
public class AdventureWorksContext : DbContext
{
	public virtual DbSet<Product> Products { get; set; }
	...
}

public void ApplicationLogic()
{
	using var context = new AdventureWorksContext();
	var bookProducts = context.Products.Where(p => p.Type == "Book").ToList();

	var singleBook = context.Products.Where(p => p.Name == "Harry Potter").FirstOrDefault();
}
```



# Get started

`dotnet new `

developed application in agile model and involved in daily scrum meetings

communicated with the technology managers to determine application requirements and designed the same accordingly
organized and attented weekly project meetings with other technical staff members, business owners, and SMEs

participated in all Scrum acitivities including sprint planning, creating user stories, and sprint retrospectives

built and maintained efficient, reusable, and reliable code via .NET language & maintained code quality

Devised and implemented a Dynamics CRM solution for 47 call centers using ASP.NET framework with 99%+ uptime.
Completed

`dotnet new web -o TodoApi`
`dotnet dev-certs https --trust`

`dotnet add package Microsoft.EntityFrameworkCore.InMemory`
`dotnet add package Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore`

