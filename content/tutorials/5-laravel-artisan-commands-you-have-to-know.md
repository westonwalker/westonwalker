---
title: The 5 laravel artisan commands you have to know
description: The 5 Laravel artisan commands you need to know to be a productive Laravel developer.
icon: 🗻
publishDate: 2022-05-16
tags: ['laravel']
published: true
---

Laravel offers a list of commands for the command line called artisan to make your life easier. But there are 5 that you have to know to be a productive Laravel developer.

## 1. Make Migration

Migrations in Laravel are what you use to create database tables and schema changes. The **make migration** command creates your migration PHP file so you can define what changes you are going to make.

```bash
php artisan make:migration create_project_table
```

## 2. Migrate

After you make your migration, you will eventually want to execute it and make the changes to the database. This is where the **migrate** command comes in.
```bash
php artisan migrate
```

## 3. Make Controller

Controllers are where all http requests are routed to and what will create the http response as well. So obviously, the **make controller** command will make our list.
```bash
php artisan make:controller ProjectController
```

and if you want to generate method stubs for all of the default rest action verbs, you can pass the **--resource** option in your command.
```bash
php artisan make:controller ProjectController --resource
```

## 4. Make Model
Models in Laravel represent the structure of your underlying database. Each table in your database will have a corresponding model. To create a model, you can use the **make model** command.
```bash
php artisan make:model Project
```

Pass -c --resource to also make a corresponding controller with method stubs
```bash
php artisan make:model Project -c --resource
```

Or even -mc --resource to create the controller and a migration.
```bash
php artisan make:model Project -mc --resource
```

## 5. Tinker
Tinker allows you to interact with your Laravel application via the command line. It's a great way to test routes, eloquent models, events, and much more. Yu can use the **tinker** command to get started.

```bash
php artisan tinker
```


