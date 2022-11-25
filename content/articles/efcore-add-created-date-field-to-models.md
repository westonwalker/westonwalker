---
title: How to add created date and updated date columns to your EF Core models
description: If your using the code first approach in Entity Framework Core, you'll probably need to make some properties nullable in your database. Here's how you do it.
publishDate: 2022-11-25
published: false
---

If your using the code first approach in Entity Framework Core, you'll probably need to make some properties nullable in your database. Here's how you do it.

In your model, add `?` to your class property you want to make nullable in the database.

```csharp
public DateTime? UpdatedDate { get; set; }
```

Now, create and run a new migration.

```bash
dotnet ef migrations add MakeUpdatedDateNullable
dotnet ef database update
```

The `UpdatedDate` column should now be nullable in your database!