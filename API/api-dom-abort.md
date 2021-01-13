# AbortController

https://dom.spec.whatwg.org/#interface-abortcontroller

```webidl
[Exposed=(Window,Worker)]
interface AbortController {
  constructor();

  [SameObject] readonly attribute AbortSignal signal;

  undefined abort();
};
```



# AbortSignal

https://dom.spec.whatwg.org/#interface-AbortSignal


```webidl
[Exposed=(Window,Worker)]
interface AbortSignal : EventTarget {
  readonly attribute boolean aborted;

  attribute EventHandler onabort;
};
```
