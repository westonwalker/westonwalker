---
title: Use line clamp to force the same height on content
description: The line clamp plugin in Tailwind will truncate text to a fixed number of lines.
publishDate: 2022-07-08
tags: ['text']
published: true
---

The line clamp plugin in Tailwind will truncate text to a fixed number of lines. Line clamp is supported by most modern browsers. Here is how to use it.

![image alt text](/line-clamp.png)


1. Install the line clamp npm package.
```bash
npm install -D @tailwindcss/line-clamp
```

2. Add it as a plugin in your Tailwind config (tailwind.config.js)
```javascript
module.exports = {
  theme: {
    // ...
  },
  plugins: [
    require('@tailwindcss/line-clamp'),
    // ...
  ],
}
```

3. Add the line-clamp class to html elements.
```html
<p class="line-clamp-3">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec fringilla, dui ac volutpat eleifend, ex mi sagittis ligula, sed congue velit quam ac mauris.
</p>
```

