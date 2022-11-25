---
title: An Easy Mobile Navbar with Tailwind CSS and Alpine JS
description: Use this responsive navbar with tailwind css and alpine js when you need a mobile menu.
icon: 🍢
publishDate: 2022-05-12
tags: ['tailwind', 'alpine']
published: true
---

Creating a responsive nav with a mobile menu is so easy in 2022. You just need Tailwind and Alpine JS.

```html
<!-- 
Use x-data attribute in alpine to create open boolean. Open will toggle tailwind classes to show and hide mobile menu.
-->
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="//unpkg.com/alpinejs" defer></script>
</head>

<body>
    <div class="max-w-7xl px-4 sm:px-12 mx-auto p-4">
        <div x-data="{ open: false }"
            class="flex flex-col max-w-screen-xl p-5 mx-auto md:items-center md:justify-between md:flex-row md:px-6 lg:px-8">
            <div class="flex flex-row items-center justify-between md:justify-start">
                <a href="./index.html" class="">
                    <h1 class="text-3xl font-bold">YourLogo</h1>
                </a>
                <button class="rounded-lg md:hidden focus:outline-none focus:shadow-outline" @click="open = !open">
                    <svg fill="currentColor" viewBox="0 0 20 20" class="w-8 h-8">
                        <path x-show="!open" fill-rule="evenodd"
                            d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM9 15a1 1 0 011-1h6a1 1 0 110 2h-6a1 1 0 01-1-1z"
                            clip-rule="evenodd"></path>
                        <path x-show="open" fill-rule="evenodd"
                            d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                            clip-rule="evenodd" style="display: none"></path>
                    </svg>
                </button>
            </div>
            <nav :class="{'flex': open, 'hidden': !open}"
                class="flex-col flex-grow hidden md:flex md:justify-end md:flex-row">
                <ul class="space-y-2 list-none md:space-y-0 md:items-center md:inline-flex mt-4 md:mt-0">
                    <li>
                        <a href="#"
                            class="px-2 md:px-6 py-6 text-base font-bold border-b-2 border-transparent hover:border-violet-400 text-gray-700">
                            Link 1
                        </a>
                    </li>
                    <li>
                        <a href="#"
                            class="px-2 md:px-6 py-6 text-base font-bold border-b-2 border-transparent hover:border-violet-400 text-gray-700">
                            Link 2
                        </a>
                    </li>
                    <li>
                        <a href="#"
                            class="px-2 md:px-6 py-6 text-base font-bold border-b-2 border-transparent hover:border-violet-400 text-gray-700">
                            Link 3
                        </a>
                    </li>
                </ul>
            </nav>
        </div>
    </div>
</body>

</html>
```
<!-- <content-image class="bg-gray-100" image-url="/desktop.png" /> -->
<content-image class="bg-gray-100" image-url="/mobile.png" />
