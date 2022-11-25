---
title: The one code snippet you need to understand css media queries
description: This code snippet is what I use to start my CSS file in new projects. It breaks down how media queries work.
icon: 🐙
publishDate: 2022-05-17
tags: ['css']
published: true
---

Media queries can be confusing. But they really are simple. If you only need to target 3 device types (mobile, tablet, desktop), the below css is all you need!

```css
/* Base Class - Phones will always have a red button  */
/* Less than 767px */
/* .button will have red background and black text */
.button {
    background-color: red;
    color: white;
}

/* Laptop & Tablet */
/* CSS is used for screens 767px - 1280px */
/* .button will have white background and black text */
@media (min-width: 767px ) {
    .button {
        background-color: orange;
        color: black;
    }
}

/* Desktop */
/* CSS is used for screens 1280px and up */
/* .button will have blue background and black text */
@media (min-width: 1280px) {
    .button {
      background-color: lightblue;
    }
}
```
