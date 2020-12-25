# Web Worker API
: 백그라운드에서 스크립트를 실행하기 위한 API    
: 별도의 스레드에서 스크립트가 실행되어 UI 스레드를 중단시키지 않음   

https://www.w3.org/TR/workers/   
https://html.spec.whatwg.org/multipage/workers.html  
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/workers


**api**
- WorkerGlobalScope
- DedicatedWorkerGlobalScope
- SharedWorkerGlobalScope
- Worker
- SharedWorker


ex.
```js
var worker = new Worker('example.js', {type: 'classic'});

function startWorker(){
    worker.onmessage = (e) => {
        console.log(e.data);
    }     
}

function stopWorker(){
    if(worker.terminate()){
        worker = null;
    }
}


// example.js
self.onmessage = (e) => {
    console.log(e.data);
    self.postMessage('send data to main');
}
```



## WorkerGlobalScope

```webidl
[Exposed=Worker]
interface WorkerGlobalScope : EventTarget {
  readonly attribute WorkerGlobalScope self;
  readonly attribute WorkerLocation location;
  readonly attribute WorkerNavigator navigator;
  undefined importScripts(USVString... urls);

  attribute OnErrorEventHandler onerror;
  attribute EventHandler onlanguagechange;
  attribute EventHandler onoffline;
  attribute EventHandler ononline;
  attribute EventHandler onrejectionhandled;
  attribute EventHandler onunhandledrejection;
};

interface WorkerLocation {
  stringifier readonly attribute USVString href;
  readonly attribute USVString origin;
  readonly attribute USVString protocol;
  readonly attribute USVString host;
  readonly attribute USVString hostname;
  readonly attribute USVString port;
  readonly attribute USVString pathname;
  readonly attribute USVString search;
  readonly attribute USVString hash;
};

interface WorkerNavigator {};
WorkerNavigator includes NavigatorID;
WorkerNavigator includes NavigatorLanguage;
WorkerNavigator includes NavigatorOnLine;
WorkerNavigator includes NavigatorConcurrentHardware;

interface mixin NavigatorConcurrentHardware {
  readonly attribute unsigned long long hardwareConcurrency;
};
```


**importScripts(urls)**  
: url 목록 실행 후 반환  

```js
self.importScripts('example.js');
```



## DedicatedWorkerGlobalScope

```webidl
[Global=(Worker,DedicatedWorker),Exposed=DedicatedWorker]
interface DedicatedWorkerGlobalScope : WorkerGlobalScope {
  [Replaceable] readonly attribute DOMString name;

  undefined postMessage(any message, sequence<object> transfer);
  undefined postMessage(any message, optional PostMessageOptions options = {});

  undefined close();

  attribute EventHandler onmessage;
  attribute EventHandler onmessageerror;
};
```


**postMessage(message)**   
: 워커에 메시지를 복제해 전송



## SharedWorkerGlobalScope

```webidl
[Global=(Worker,SharedWorker),Exposed=SharedWorker]
interface SharedWorkerGlobalScope : WorkerGlobalScope {
  [Replaceable] readonly attribute DOMString name;

  undefined close();

  attribute EventHandler onconnect;
};
```



## Worker

```webidl
[Exposed=(Window,DedicatedWorker,SharedWorker)]
interface Worker : EventTarget {
  constructor(USVString scriptURL, optional WorkerOptions options = {});

  undefined terminate();

  undefined postMessage(any message, sequence<object> transfer);
  undefined postMessage(any message, optional PostMessageOptions options = {});
  attribute EventHandler onmessage;
  attribute EventHandler onmessageerror;
};

dictionary WorkerOptions {
  WorkerType type = "classic";
  RequestCredentials credentials = "same-origin";
  DOMString name = "";
};

enum WorkerType { "classic", "module" };

Worker includes AbstractWorker;

interface mixin AbstractWorker {
  attribute EventHandler onerror;
};
```


**credentials**    
: type이 'module'인 경우 RequestCredentials 지정



## SharedWorker

```webidl
[Exposed=Window]
interface SharedWorker : EventTarget {
  constructor(USVString scriptURL, optional (DOMString or WorkerOptions) options = {});

  readonly attribute MessagePort port;
};

SharedWorker includes AbstractWorker;
```



[top](#)
