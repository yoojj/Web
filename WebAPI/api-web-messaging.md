# Web Messaging API

https://www.w3.org/TR/webmessaging/   
https://html.spec.whatwg.org/multipage/web-messaging.html


**api**
- MessageChannel
- MessagePort
- BroadcastChannel



## MessageChannel

```webidl
[Exposed=(Window,Worker)]
interface MessageChannel {
  constructor();

  readonly attribute MessagePort port1;
  readonly attribute MessagePort port2;
};
```



## MessagePort

```webidl
[Exposed=(Window,Worker,AudioWorklet), Transferable]
interface MessagePort : EventTarget {
  undefined postMessage(any message, sequence<object> transfer);
  undefined postMessage(any message, optional PostMessageOptions options = {});
  undefined start();
  undefined close();

  attribute EventHandler onmessage;
  attribute EventHandler onmessageerror;
};

dictionary PostMessageOptions {
  sequence<object> transfer = [];
};
```


**postMessage(message)**   
: 메시지 전송  



## BroadcastChannel

```webidl
[Exposed=(Window,Worker)]
interface BroadcastChannel : EventTarget {
  constructor(DOMString name);

  readonly attribute DOMString name;
  undefined postMessage(any message);
  undefined close();
  attribute EventHandler onmessage;
  attribute EventHandler onmessageerror;
};
```



[top](#)
