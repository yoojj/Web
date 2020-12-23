# Fetch API


https://fetch.spec.whatwg.org/


**fecth polyfill**    
https://github.com/github/fetch



## API


- [Headers](#headers)
- [Body](#body)
- [Request](#request)
- [Response](#response)


ex.
```js
/*
- WindowOrWorkerGlobalScope.fecth()
- Window.fetch()
- WorkerGlobalScope.fetch()
*/

var option {
    headers: new Headers(),
    body: new Body(),
    request: new Request(),
};

fecth('url', { option })
    .then( response => json() )
    .then( json => console.log(json) )
    .catch( error => console.error(error) );
```



### Headers

**Headers**
- constructor(HeadersInit)
- append()
- delete()
- get()
- has()
- set()
- iterable
    - keys()
    - entries()
    - values()


ex.
```js
var header = new Headers();

header.append('content-type', 'text/plan');

for(var h of header.entries()) {
    console.log(h[0] === 'content-type');
}
```



### Body

**Body**
- body
- bodyUsed
- arrayBuffer() : ArrayBuffer 객체로 요청이나 응답받음
- blob() : Blob 객체로 요청이나 응답받음
- formData() : FormData 객체로 요청이나 응답받음
- json() : Json 객체로 요청이나 응답받음
- text()



### Request

**Request** implements Body     
- constructor(RequestInfo, RequestInit)
- method : HTTP 메소드 지정
- url : url 지정
- headers : 요청과 연관된 Headers 객체
- destination : RequestDestination
- referrer : 리퍼러 지정
- referrerPolicy : 리퍼러 정책 지정  
- mode : RequestMode 지정
- credentials : RequestCredentials 지정
- cache : RequestCache 지정
- redirect : RequestRedirect 지정
- integrity : 리소스 무결성을 확인하기 위한 해시 값 지정
- keepalive
- isReloadNavigation
- isHistoryNavigation
- signal
- clone()


**RequestInit**
- method
- headers
- body
- referrer
- referrerPolicy
- mode : RequestMode 지정
- credentials : RequestCredentials 지정
- cache : RequestCache 지정
- redirect : RequestRedirect 지정
- integrity : 리소스 무결성을 확인하기 위한 해시 값 지정
- keepalive
- signal
- window


**RequestDestination**
- ''
- 'audio'
- 'audioworklet'
- 'document'
- 'embed'
- 'font'
- ...


**RequestMode**
- 'navigate'
- 'same-origin'
- 'no-cors'
- 'cors'


**RequestCredentials**
- 'omit'
- 'same-origin'
- 'include'


**RequestCache**
- 'default'
- 'no-store' : 캐시를 찾지 않으며 응답받은 리소스로 캐시를 업데이트하지 않음
- 'reload' : 캐시를 찾지 않으며 응답받은 리소스로 캐시를 업데이트함
- 'no-cache'
- 'force-cache'
- 'only-if-cached'


**RequestRedirect**
- 'follow' : 리다이렉트를 따라감
- 'error'  : 리다이렉트가 발생하면 오류
- 'manual' : 리다이렉트를 따라가지 않고 리다이렉트 정보만 전달함



### Response

**Response** implements Body  
- constructor(BodyInit, ResponseInit)
- error()
- redirect(url, status)
- type : ResponseType
- url
- redirected
- status : 응답 코드 반환
- ok : status가 2xx인 경우 true 반환
- statusText
- headers : Headers 객체 반환
- clone()


**ResponseInit**
- status
- statusText
- headers


**ResponseType**
- 'basic'
- 'cors'
- 'default'
- 'error'
- 'opaque'
- 'opaqueredirect'



[top](#)
