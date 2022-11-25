---
title: 7 Tailwind CSS Buttons
description: Tailwind CSS has taken front end development by storm. Here are 7 different buttons you can build with it.
publishDate: 2022-10-07
published: true
---

Buttons. Ahhh boring buttons. The most basic element we love to neglect. But buttons don't have to be boring. Here are 7 spicy button designs using Tailwind CSS.

## 1) Icon
Adding an icon to a button is a nice cherry on top for it's design and can add some context for it's intended action.

<tailwind-buttons button-type="icon"></tailwind-buttons>

```html
<button 
    class="px-6 py-2.5 text-black rounded-lg bg-green-300 hover:bg-green-400 inline-flex items-center" 
    type="button">
    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 mr-2" ...>
        <path ... />
    </svg>
    Send email
</button>
```

## 2) Standard

Standard button to draw a users attention to an action. Great for primary actions.

<tailwind-buttons button-type="standard"></tailwind-buttons>

```html
<button 
    class="px-6 py-2.5 text-white bg-blue-500 rounded-lg hover:bg-blue-600 mt-2" 
    type="button">
    Standard
</button>
```

## 3) Outlined
Draws attention but not to much. Great for secondary actions.

<tailwind-buttons button-type="outlined"></tailwind-buttons>

```html
<button 
    class="px-6 py-2.5 text-blue-500 border-2 border-blue-500 bg-white rounded-lg hover:bg-blue-500 hover:text-white mt-2" 
    type="button">
    Outlined
</button>
```

## 4) Dark & Square
Square buttons should only be used if the rest of your design is lacking border radiuses. Usually meant for a more business like theme.

<tailwind-buttons button-type="square"></tailwind-buttons>

```html
<button 
    class="px-6 py-2.5 text-white bg-gray-900 hover:bg-black" 
    type="button">
    Dark & Square
</button>
```

## 5) Fully Rounded
A fully rounded button is meant for more light hearted designs. Again, if your using rounded buttons, keep the rest of your design consistant with it.

<tailwind-buttons button-type="rounded"></tailwind-buttons>

```html
<button 
    class="px-6 py-2.5 text-white rounded-full bg-pink-500 hover:bg-pink-600" 
    type="button">
    Fully Rounded
</button>
```

## 6) Raised
Raised buttons give depth to the page and make the element appear closer to the user, giving it a sense of purpose.

<tailwind-buttons button-type="raised"></tailwind-buttons>

```html
<button 
    class="px-8 py-3 shadow-2xl text-yellow-500 rounded bg-white hover:bg-gray-50 mt-2" 
    type="button">
    Raised
</button>
```
## 7) Smooth
Smooth buttons are great for secondary actions. Their designs don't draw as much attention as a solid primary button.

<tailwind-buttons button-type="smooth"></tailwind-buttons>

```html
<button 
    class="px-8 py-3 text-red-500 rounded bg-red-100 mt-2" 
    type="button">
    Smooth
</button>
```

## Beautiful Tailwind CSS Landing Pages

If you enjoyed this, consider checking out my new project - [Tailwind Sites](https://tailwindsites.com/)

There you will find Expertly crafted Tailwind CSS landing pages. Get a head start on your next big idea. Beautifully designed. Expertly coded. Unlimited access for just $99.



