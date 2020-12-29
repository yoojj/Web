# Headless Browser
: 사용자 인터페이스(GUI)가 없는 브라우저   
: 요청, 응답, 성능, 등 테스트를 위해 사용  


- 브라우저 헤드리스 모드
    - Headless Firefox
    - Headless Chromium
- [PhantomJS](#phantomjs)
- SlimerJS
- Zombie.js
- Splash
- HtmlUnit



## PhantomJS

https://phantomjs.org/


```bash
$ npm install phantomjs -g
$ phantomjs -v

$ phantomjs example.js
```

ex.
```js
var version = phantom.version;

console.log(JSON.stringify(version));

phantom.exit();
```



[top](#)
