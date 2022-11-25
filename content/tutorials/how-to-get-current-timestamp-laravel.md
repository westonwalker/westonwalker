---
title: How to get the current timestamp in Laravel
description: Find out how to get the current timestamp in Laravel with the Carbon package
icon: 🚡
publishDate: 2022-05-13
tags: ['laravel']
published: true
---

Laravel utilizes the [Carbon](https://carbon.nesbot.com/) package. It is an API extension for DateTime in PHP.
The current time can be fetched with Carbon by using the now() method.
This will equal the current time in YYY-mm-dd HH:mm:ss format
```php
use Carbon\Carbon;

...

$now = Carbon::now();
```

This will get the current timestamp.
```php
$now = Carbon::now()->timestamp;
```
