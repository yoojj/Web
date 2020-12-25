# Worklet API

https://www.w3.org/TR/worklets/  
https://html.spec.whatwg.org/multipage/worklets.html   
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/worklets


**api**
- [FakeWorkletGlobalScope](#fakeworkletglobalscope)
- [WorkletGlobalScope](#workletglobalscope)
- [Worklet](#worklet)



## FakeWorkletGlobalScope

```webidl
interface Window {
  [SameObject, SecureContext] readonly attribute Worklet fakeWorklet1;
  [SameObject, SecureContext] readonly attribute Worklet fakeWorklet2;
};

[Global=(Worklet,FakeWorklet), Exposed=FakeWorklet,SecureContext]
interface FakeWorkletGlobalScope {
  undefined registerFake(DOMString type, Function classConstructor);
};
```



## WorkletGlobalScope

```webidl
[Exposed=Worklet, SecureContext]
interface WorkletGlobalScope {};
```



## Worklet

```webidl
[Exposed=Window, SecureContext]
interface Worklet {
  [NewObject] Promise<undefined> addModule(USVString moduleURL, optional WorkletOptions options = {});
};

dictionary WorkletOptions {
  RequestCredentials credentials = "same-origin";
};
```



[top](#)
