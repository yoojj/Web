# CustomEvent 

https://dom.spec.whatwg.org/#interface-customevent


```webidl
[Exposed=(Window,Worker)]
interface CustomEvent : Event {
  constructor(DOMString type, optional CustomEventInit eventInitDict = {});

  readonly attribute any detail;

  undefined initCustomEvent(DOMString type, optional boolean bubbles = false,
    optional boolean cancelable = false, optional any detail = null); // legacy
};

dictionary CustomEventInit : EventInit {
  any detail = null;
};
```



[top](#)
