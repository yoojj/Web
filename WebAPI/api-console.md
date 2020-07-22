# Console API
: 디버깅 기능을 제공하는 API        
: 브라우저의 콘솔에 디버그 정보 출력        
: 노드에서는 브라우저의 콘솔 메커니즘과 유사한 기능을 지원하는 콘솔 모듈을 제공        

https://console.spec.whatwg.org/


**logging**   
- [console.assert()](#consoleassert)
- console.clear()
- console.debug()
- console.error()
- console.info()
- console.log()
- console.table()
- console.trace()
- console.warn()
- console.dir()
- console.dirxml()


**counting**  
- console.count()
- console.countReset()


**grouping**   
- console.group()
- console.groupCollapsed()
- console.groupEnd()


**timing**  
- console.time()
- console.timeLog()
- console.timeEnd()



## console.assert()
: 주어진 조건이 거짓이면 오류 메시지 반환  

> console.assert(표현식)  
> console.assert(표현식, 메시지)  
> console.assert(표현식, 객체)



[top](#)
