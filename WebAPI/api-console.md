# Console API

https://console.spec.whatwg.org/


```webidl
[Exposed=(Window,Worker,Worklet)]
namespace console {
  // Logging
  undefined assert(optional boolean condition = false, any... data);
  undefined clear();
  undefined debug(any... data);
  undefined error(any... data);
  undefined info(any... data);
  undefined log(any... data);
  undefined table(optional any tabularData, optional sequence<DOMString> properties);
  undefined trace(any... data);
  undefined warn(any... data);
  undefined dir(optional any item, optional object? options);
  undefined dirxml(any... data);

  // Counting
  undefined count(optional DOMString label = "default");
  undefined countReset(optional DOMString label = "default");

  // Grouping
  undefined group(any... data);
  undefined groupCollapsed(any... data);
  undefined groupEnd();

  // Timing
  undefined time(optional DOMString label = "default");
  undefined timeLog(optional DOMString label = "default", any... data);
  undefined timeEnd(optional DOMString label = "default");
```


**assert()**   
: 주어진 조건이 참인 경우 참 반환   

```js
var condition = 0;
var bool;

console.log(condition == 0);
console.log(bool = (condition == 0), { result: bool ? 'ok' : 'error' });
```


**clear()**   
: 콘솔 내용을 전부 지움   


[top](#)
