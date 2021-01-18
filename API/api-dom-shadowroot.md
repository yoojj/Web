# ShadowRoot

https://dom.spec.whatwg.org/#interface-shadowroot


```webidl
[Exposed=Window]
interface ShadowRoot : DocumentFragment {
  readonly attribute ShadowRootMode mode;
  readonly attribute Element host;
  attribute EventHandler onslotchange;
};

enum ShadowRootMode { "open", "closed" };
```



[top](#)
