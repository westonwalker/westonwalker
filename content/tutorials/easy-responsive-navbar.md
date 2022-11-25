---
title: An Easy Responsive Navbar with Tailwind CSS
description: Use this responsive navbar with tailwind css when you don't feel like reaching for javascript to toggle mobile menu's.
icon: 🐻
publishDate: 2022-05-11
tags: ['tailwind']
published: true
---

Sometimes I just don't feel like reaching for Javascript to make a mobile navbar with a hamburger toggle.

Luckily with Tailwind CSS we can create a simple responsive navbar that requires 0 Javascript.
```html
<!-- 
Contrain max width. Use flex row to keep logo and nav links on same line for screens >= 640px. Otherwise, use
flex col to stack log on top of nav links 
-->
<div class="max-w-7xl mx-auto px-4 sm:px-12 py-4 flex flex-col items-center sm:flex-row sm:justify-between">
    <a href="/" class="leading-relaxed text-left text-2xl md:text-3xl font-black md:leading-snug bg-yellow-300 py-1 px-2">
        TheFullStackDev
    </a>
    <div class="text-base md:text-lg font-bold mt-4 sm:mt-0">
        <a class="p-2 hover:bg-yellow-300" to="#">
            🔥 Tutorials
        </a>
        <a class="p-2 hover:bg-yellow-300" to="#">
            🚀 Courses
        </a>
        <a class="p-2 hover:bg-yellow-300" to="#">
            👋 About
        </a>
    </div>
</div>
```
Desktop
<content-image image-url="/responsive-nav-1.png" />

Mobile
<content-image image-url="/responsive-nav-2.png" />
