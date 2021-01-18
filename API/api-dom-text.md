# Text

https://dom.spec.whatwg.org/#interface-text


```webidl
[Exposed=Window]
interface Text : CharacterData {
  constructor(optional DOMString data = "");

  [NewObject] Text splitText(unsigned long offset);
  readonly attribute DOMString wholeText;
};
```



[top](#)
