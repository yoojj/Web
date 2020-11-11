# IntersectionObserver API
https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API


> IntersectionObserver(callback, options)


ex.

```js
const options = {
    root: document.querySelector('#id'),
    rootMargin: '0px',
    threshold: 1.0,
}

const io = new IntersectionObserver((entries, observer) => {

    entries.forEach( entry => {
        entry.boundingClientRect
        entry.intersectionRatio
        entry.intersectionRect
        entry.isIntersecting
        entry.rootBounds
        entry.target
        entry.time
    });

}, options);

io.observe(document.querySelector('#id'));
```


[top](#)
