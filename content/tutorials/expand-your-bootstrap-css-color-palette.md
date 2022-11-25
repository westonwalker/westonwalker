---
title: How to expand the Bootstrap CSS color palette
description: Bootstrap CSS only ships with a handful of colors. Learn how to get more colors at your disposale.
icon: 😏
publishDate: 2022-05-21
tags: ['design', 'bootstrap']
published: true
---

Your probably familiar with the default colors that come with Bootstrap CSS.
<img src="/bootstrap-default-colors.png" alt="Bootstrap Default Colors" >

But did you know you there are over 100 other colors at your disposal with a little setup?

You can edit the **scss/_variables.scss** file that comes with your bootstrap library to incldue these classes.
```css
$colors: (
  "yellow-100": $yellow-100, /* add colors from bootstrap color palette */ 
  "teal-300": $teal-300,
  "custom-red": #f2645a /* or add your own custom color */ 
   /* and so on */ 
);
```

Now you can use text or backgrounds classes with these colors.
```html
<a class="btn btn-teal-300 px-4" href="#">Get Started</a>
```

You can find all of the colors listed [here](https://getbootstrap.com/docs/5.2/customize/color/#all-colors).
