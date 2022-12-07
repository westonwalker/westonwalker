---
title: Journey to find an affordable and simple service to host and deploy my .NET Blazor app
description: I spent a week finding the perfect service to host and deploy my .NET apps. 
publishDate: 2022-12-07
published: true
---

I’ve been on a week-long journey to find a deployment platform for .NET apps that is affordable, reliable, and VERY easy to set up. Something I can set up in 10 minutes and never have to think about again. No mapping of multiple services. No complicated UI’s. No manual database updates. No big monthly bills. No Docker (great tool, just don’t want to deal with it outside of work)

Some people like the challenge of setting up complicated infrastructure and deployments. I have a low pain tolerance when it comes to hosting and deploying apps. Nothing frustrates me more and slows my momentum on a project than spending hours setting up deployments. I want to code and ship features. Fast.

Well, I finally found something that fits the bill. [Railway](https://railway.app/). So here is guide that will save you a lot of time setting it up!

Keep in mind, this is for my side projects. There are other popular methods that should be used for larger enterprise apps.

## App requirements

This is for [asp.net](http://asp.net) core mvc or blazor server apps using mysql or postresql. I haven’t tried it with other combinations but i’m sure they will work with a little tweaking. This has been tested using efcore and identity for authentication.

It’s also important to use a `.env` locally file for your connection string instead of your appsettings.json files. This is because the platform were deploying to uses environment variables for the database connections. Just remember to add your `.env` file to your `.gitignore`!

## Links

Here is the public repo of the app i’m currently hosting if you’d like to use it for examples
[https://github.com/westonwalker/dotnetdevs](https://github.com/westonwalker/dotnetdevs)

Here is the live app.
[https://dotnetdevs-production.up.railway.app/](https://dotnetdevs-production.up.railway.app/)

Now to the actual guide.

## Project Setup
My current app is a Blazor Server project on .NET 6 but you can also use a [asp.net](http://asp.net) core web app as well.

Your solution file and project must be in the same folder.
![solution folder](https://i.imgur.com/kX2cF9S.png)

Use efcore and the Pomelo mysql nuget package.
![efcore nuget](https://i.imgur.com/0aLfxvr.png)

To add `.env` file support, add the DotNetEnv nuget. This will pull in a `.env` file in your project root and allow you to access the variables in the app.
![dotnetenv nuget](https://i.imgur.com/BhdwvmE.png)


Without the next 2 steps, railway will fail to deploy your project.

In your `.csproj`, add the following property inside the `<PropertyGroup></PropertyGroup>` tag.
```xml
<InvariantGlobalization>true</InvariantGlobalization>
```
Add `.dockerignore` file in your root folder with the following.
```bash
# directories
**/bin/
**/obj/
**/out/

# files
Dockerfile*
**/*.md
```

### Helper methods
Because railway.app gives you access to the database creds through env variables with specific names, we need to add a helper functions to build our connection string. So add a ConnectionHelper class. 

```csharp
public static class ConnectionHelper
{
    public static string GetConnectionString()
    {
        var connectionString = Environment.GetEnvironmentVariable("LOCAL_DB");
        return !string.IsNullOrEmpty(connectionString) ? connectionString : BuildConnectionString();
    }

    private static string BuildConnectionString()
    {
        var server = Environment.GetEnvironmentVariable("MYSQLHOST");
        var port = Environment.GetEnvironmentVariable("MYSQLPORT");
        var user = Environment.GetEnvironmentVariable("MYSQLUSER");
        var db = Environment.GetEnvironmentVariable("MYSQLDATABASE");
        var password = Environment.GetEnvironmentVariable("MYSQLPASSWORD");
        return $"server={server}; port={port}; database={db}; user={user}; password={password}; Persist Security Info=False; Connect Timeout=300";
    }
}
```

This will try to find an environment variable called `LOCAL_DB`. I only set this variable locally in my local `.env` file. Again, don't forget to add your `.env` file to `.gitignore`. In production, it will instead use the railway environment variables to build the connection string.

Add this to your local `.env` file.
```bash
LOCAL_DB="server=localhost;database=dotnet_devs;uid=root;pwd=;"
```

Finally, add this to your `program.cs`. Change the db context to whatever you named yours.
```csharp
...
var builder = WebApplication.CreateBuilder(args);
var connectionString = ConnectionHelper.GetConnectionString();
builder.Services.AddDbContextFactory<ApplicationDbContext>(options => options
	.UseMySql(connectionString, ServerVersion.AutoDetect(connectionString)));
...
```
To run your migrations on app startup, add the following code snippet in your `program.cs` after `builder.Build()`
```csharp
...
var app = builder.Build();

// run migrations
using (var scope = app.Services.CreateScope())
{
	var db = scope.ServiceProvider.GetRequiredService<ApplicationDbContext>();
	db.Database.Migrate();
}
...
```

## Railway Setup
Go to [railway.app](http://railway.app) and create an account.

Once your account is setup, add a new MySQL instance. You will see the environment variables I’ve talked about above after it’s finished.
![railway app](https://i.imgur.com/HDGQLCe.png)

Then, add a new github repo. This will deploy your site and add automatic deployments whenever your repo is updated.
![railway github repo](https://i.imgur.com/X7ovtw1.png)

Let deployment finish. Then add a new variable to your site - PORT=3000
![railway port](https://i.imgur.com/rUOWBRp.png)

Then generate a domain.
![railway domain](https://i.imgur.com/vKx7fCG.png)

It may be in the process of deploying because you changed the settings. I would advise waiting for that deployment to finish and redeploying 1 more time.

Now visit your site!
![visit site](https://i.imgur.com/OGrVjF7.png)

It should be live. If it’s not, give it a minute.
![dotnetdevs site](https://i.imgur.com/aP6cEnt.png)

Let's check our database in Railway. Look at that, our migrations were also ran!
![database migrations ran](https://i.imgur.com/QgWLk7P.png)

Now, anytime I push a change to my repo, [railway.app](http://railway.app) will release the changes automatically and also run any outstanding migrations I have.

Here is my live site with Blazor server, identity, and database - [https://dotnetdevs-production.up.railway.app/](https://dotnetdevs-production.up.railway.app/)

### Ok, how much does it cost?

I don’t have an exact cost. You get $5 of free credits a month. From what I’ve read, it should be around $10-$15 a month for the database and application combined. Which is very affordable in my eyes.

I will update this post after a couple of weeks with what my spending is.