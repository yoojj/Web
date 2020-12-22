# Web Worker API
: 백그라운드에서 스크립트를 실행하기 위한 API    
: 별도의 스레드에서 스크립트가 실행되어 UI 스레드를 중단시키지 않음   


https://www.w3.org/TR/workers/   
https://html.spec.whatwg.org/multipage/workers.html



## API

**AbstractWorker**
- onerror


**WorkerGlobalScope**   
- self      : WorkerGlobalScope 객체 반환
- location  : WorkerLocation 객체 반환
    - href
    - origin
    - protocol
    - host
    - hostname
    - port
    - pathname
    - search
    - hash
- navigator : WorkerNavigator 객체 반환  
    - NavigatorID
    - NavigatorLanguage
    - NavigatorOnLine
    - NavigatorConcurrentHardware
- importScripts(URL) : url 목록 실행 후 반환  
- onerror
- onlanguagechange
- onoffline
- ononline  
- onrejectionhandled   
- onunhandledrejection


**DedicatedWorkerGlobalScope**
- name
- postMessage(postMessage, onmessage)
- postMessage(postMessage, onmessage, PostMessageOptions)
- close()
- onmessage
- onmessageerror


**SharedWorkerGlobalScope**
- name
- close()
- onconnect


**Worker**
- constructor(USVString, WorkerOptions)
- terminate()
- postMessage(postMessage, onmessage)
- postMessage(postMessage, onmessage, PostMessageOptions)
- onmessage
- onmessageerror


**WorkerOptions**
- type : WorkerType 지정  
- credentials : RequestCredentials 지정  
- name


**WorkerType**
- 'classic'
- 'module'


**SharedWorker**
- constructor(USVString, DOMString | WorkerOptions)
- port


ex.
```js
const worker = new Worker('example.js', {type: 'classic'});

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



[top](#)
