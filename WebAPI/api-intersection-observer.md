# Intersection Observer API


https://www.w3.org/TR/intersection-observer/



## API

**IntersectionObserver**
- constructor(IntersectionObserverCallback, IntersectionObserverInit)
- root : 뷰포트로 사용될 요소
- rootMargin
- thresholds
- observe(Element)
- unobserve(Element)
- disconnect()
- takeRecords()


**IntersectionObserverCallback**
- entries : IntersectionObserverEntry
- observer : IntersectionObserver


**IntersectionObserverInit**
- root
- rootMargin
- threshold


**IntersectionObserverEntry**
- constructor(IntersectionObserverEntryInit)
- time : 변경된 시간
- rootBounds
- boundingClientRect  
- intersectionRect
- isIntersecting
- intersectionRatio
- target


**IntersectionObserverEntryInit**
- time
- rootBounds
- boundingClientRect
- intersectionRect
- isIntersecting
- intersectionRatio
- target


ex.
```js
var options = {
    root: document.querySelector('#id'),
    rootMargin: '0px',
    threshold: 1.0,
}

var io = new IntersectionObserver( (entries, observer) => {

    entries.forEach( entry => {
        entry.time;
        entry.rootBounds;
        entry.boundingClientRect;
        entry.intersectionRect;
        entry.isIntersecting;
        entry.intersectionRatio;
        entry.target;
    });

}, options);

io.observe(document.querySelector('#id'));
```



[top](#)
