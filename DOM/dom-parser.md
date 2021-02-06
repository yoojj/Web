# DOM Parser



## DOM Parser API

https://www.w3.org/TR/DOM-Parsing/#the-domparser-interface


```webidl
[Exposed=Window]
interface DOMParser {
  constructor();

  Document parseFromString(DOMString string, DOMParserSupportedType type);
};

enum DOMParserSupportedType {
  "text/html",
  "text/xml",
  "application/xml",
  "application/xhtml+xml",
  "image/svg+xml"
};
```



ex.
```js
var string = '<div id="example"><a href="#">Link</a></div>';
var html = new DOMParser().parseFromString(string, 'text/html');
```



[top](#)
