---
title: How to add and subtract dates in Laravel
description: Find out how to add and subtract dates in Laravel with the Carbon package
icon: 🐠
publishDate: 2022-05-14
tags: ['laravel']
published: true
---

Laravel utilizes the [Carbon](https://carbon.nesbot.com/) package. It is an API extension for DateTime in PHP.

Carbon provides the add and sub methods. Both methods accept either a string or a integer and string.
```php
use Carbon\Carbon;
...

$now = Carbon::now();           // 2022-05-13 07:00:00

echo $now->add('61 seconds');   // 2022-05-13 07:01:01

echo $now->sub('1 day');        // 2022-05-14 07:01:01

echo $now->add('1 month');      // 2022-06-14 07:01:01

echo $now->add(1, 'year');      // 2023-06-14 07:01:01
```

Carbon also provies add and sub methods for each time field.
```php
use Carbon\Carbon;
...

$now = Carbon::now();           // 2022-05-13 07:00:00

echo $now->addCenturies(4);     // 2423-06-12 14:39:05
echo $now->subCenturies(4);     // 2022-05-13 07:00:00

echo $now->addYears(4);         // 2026-05-13 07:00:00
echo $now->subYears(4);         // 2022-05-13 07:00:00

echo $now->addMonths(5);         // 2022-10-13 07:00:00
echo $now->subMonths(5);         // 2022-05-13 07:00:00

// .. and so on for each field
```
