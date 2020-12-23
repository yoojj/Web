# Console API


https://console.spec.whatwg.org/



## API

- Window.console    
- WorkerGlobalScope.console


**console**
- assert(data)
- clear()
- debug(data)
- error(data)
- info(data)
- log(data)
- table(tabularData)
- trace(data)
- warn(data)
- dir(data)
- dirxml(data)
- count(DOMString)
- countReset(DOMString)
- group(data)
- groupCollapsed(data)
- groupEnd()
- time(DOMString)
- timeLog(DOMString)
- timeEnd(DOMString)


**비표준**   
- context()
- memory()
- profile()
- profileEnd()
- timeStamp()
- ...


그룹 | 함수
---|---
log   | log(), trace(), dir(), dirxml(), group(), groupCollapsed(), debug(), timeLog()
info  | count(), info(), timeEnd()
warn  | warn(), countReset()
error | error(), assert()



[top](#)
