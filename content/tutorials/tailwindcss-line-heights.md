---
title: Working with Line Heights in Tailwind CSS
description: Line heights in Tailwind CSS can be tricky.
icon: 🌠
alt: tailwind-line-heights
publishDate: 2022-07-07
tags: ['tailwind']
published: true
---

To apply a line height in Tailwind CSS, you can use the leading class.
```html
<p class="text-xl leading-relaxed">This is a big line height!!!</p>
```
However, if you add a font size at a larger breakpoint, the font size at that breakpoint will override the line height you set. To fix this, you need to re-apply your line height at that breakpoint as well, even if it is the same line height class!

```html
<p class="text-xl md:text-2xl leading-relaxed md:leading-relaxed">
    This is a big line height!!!
</p>
```
<p class="text-xl md:text-2xl leading-relaxed md:leading-relaxed">
    This is a big line height!!!
</p>

You can see all of the available line height classes here <a target="_blank" href="https://tailwindcss.com/docs/line-height">➡️</a>