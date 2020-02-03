# window
: 브라우저 윈도우 객체로 최상위 객체   


속성 | 설명
---|---
window.outerWidth  | 윈도우 창 전체 너비 반환
window.outerHeight | 윈도우 창 전체 높이 반환
window.innerWidth  | 윈도우 너비 반환
window.innerHeight | 윈도우 높이 반환
window.pageXOffset | 현재 위치 == window.scrollX
window.pageYOffset | 현재 위치 == window.scrollY


- [window.setTimeout()](#windowsettimeout)
- [window.clearTimeout()](#windowcleartimeout)
- [window.setInterval()](#windowsetinterval)
- window.clearInterval()
- ...



## window.setTimeout()
: 일정 시간 후 인자로 들어온 함수를 한 번만 호출

> setTimeout(func, delay, arg)

```js
function func(x, y){
    console.log( `${x} ${y}`);
}
setTimeout(func, 3000, 'a', 'b');


setTimeout( (x, y) => { console.log( `${x} ${y}`); }, 3000, 'a', 'b');
```



## window.clearTimeout()
: setTimeout() 호출을 취소하기 위해 사용하는 함수  

```js
const timer = setTimeout( () => { console.log('실행'); }, 3000 );
setTimeout( () => {
    console.log('종료');
    clearTimeout(timer);
}, 1000);
```



## window.setInterval()
: 일정 시간을 간격으로 인자로 들어온 함수 주기적으로 실행

> setInterval(func, delay, arg)

```js
const timer = setInterval( () => {console.log('실행');}, 1000 );

setTimeout( () => { clearInterval(timer); console.log('종료'); }, 5000 );
```



[top](#)
