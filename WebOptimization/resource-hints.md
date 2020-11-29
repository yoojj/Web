# Resource Hints
https://www.w3.org/TR/resource-hints/

- preconnect
- prefetch
- dns-prefetch
- prerender

ex.

```html
<link rel="preconnect" href="//example.com">
<link rel="preconnect" href="//cdn.example.com" crossorigin>

<link rel="prefetch" href="example.js" as="script">
<link rel="prefetch" href="example.css" as="style">
<link rel="prefetch" href="//example.com/next-page.html" as="document" crossorigin="use-credentials">

<link rel="dns-prefetch" href="//example.com">

<link rel="prerender" href="//example.com/next-page.html">
```




[top](#)
