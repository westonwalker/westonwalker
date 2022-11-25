---
title: How to dynamically render a laravel blade component from a variable
description: Learn how to use variable values to call Laravel Blade components.
icon: ⛄️
alt: laravel-dynamic-components
publishDate: 2022-05-20
tags: ['laravel']
published: true
---

I'm in the middle of making courses on beginner web development. My current setup is storing courses and lesson meta information in the database but I wanted to store the actual course content in markdown that resides in Laravel blade components.

Well we can do that!

Laravel has a special component called a dynamic component.

```php
<x-dynamic-component :component="$variable" />
```

It works by passing in a string variable to the component prop. It will then find the correct component in the views/components folder based on that string value.

So for each one of my courses, I can pull the record from the database. Then based on the slug of the course, I can call the correct component. Laravel really is awesome!

```php
@foreach ($courses as $course)
    <x-dynamic-component :component="'content.courses.'.$course->slug" />
@endforeach
```

This is the component called...
```html
<p class="text-sm font-semibold text-blue-500 tracking-widest uppercase">Beginners</p>
# Web Fundamentals

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nunc arcu, congue vel faucibus eu, porttitor sed leo. Maecenas in ultricies velit. Nam vel risus iaculis, lobortis orci a, faucibus orci. 

```

The result...
<img src="https://i.imgur.com/wUfrNqJ.png" alt="Laravel Dynamic Component" >


