# Fetch
≒ XMLHttpRequest  
: XHR의 문제점 보완      
: Promise 기반 비동기 방식  
: HTTP의 모든 개념 도입     


https://fetch.spec.whatwg.org/


**fecth interface**
- [Headers](#headers)
- [Body](#body)
- [Request](#request)
- [Response](#response)



**fecth polyfill**    
https://github.com/github/fetch


```js
// WindowOrWorkerGlobalScope.fecth()
// - Window.fetch()
// - WorkerGlobalScope.fetch()
fecth('resource url | Request', { option })
    .then( response => response.json() )
    .then( json => console.log(json) )
    .catch( error => console.error(error) );
```


**option**  

옵션 | 설명
---|---
method  | HTTP 메소드 중 GET, POST, HEAD 메소드 지원
headers | HTTP 헤더 지정 -- [Header](#header)
body    | HTTP 바디 지정 (Blob, BufferSource, FormData, URLSearchParams 등)
mode    | CORS 모드 지정 (cors, no-cors, same-origin 등)
referrer    | 리퍼러 지정
referrerPolicy | 리퍼러 정책 지정
integrity   | 리소스 무결성을 확인하기 위한 해시 값 지정  
keepalive   | keepalive 지정  
credentials | (omit, include, same-origin)
cache       | 캐시 제어 -- [Requst.cache](#requestcache)
redirect    | 리다이렉트 제어 -- [Request.redirect](#requestredirect)



## Headers

- Headers.append()
- Headers.has()
- Headers.set()
- Headers.get()
- Headers.keys()
- Headers.entries()
- Headers.values()
- Headers.delete()

```js
var header = new Headers();

header.append('content-type', 'text/plan');
(header.get('content-type') === 'text/plan') == true

for(var h of header.entries()) {
    console.log(h[0] === 'content-type');
}
```



## Body

**속성**
- Body.body
- Body.bodyUsed

**메소드**
- Body.text()
- Body.json()
- Body.blob()
- Body.formData()
- Body.arrayBuffer()



## Request
: Body 인터페이스 구현   

**속성**  
- Request.method
- Request.headers
- Request.mode
- Request.referrer
- Request.referrerPolicy
- Request.credentials
- Request.cache
- Request.context
- Request.destination
- Request.integrity
- Request.redirect
- Request.url

**메소드**  
- Request.clone()


### Request.cache

값 | 설명
---|---
default  |
no-store | 캐시를 찾지 않으며 응답받은 리소스로 캐시를 업데이트하지 않음  
reload   | 캐시를 찾지 않으며 응답받은 리소스로 캐시를 업데이트함
no-cache |
force-cache    |
only-if-cached |


### Request.redirect

값 | 설명
---|---
follow | 리다이렉트를 따라감
manual | 리다이렉트를 따라가지 않고 리다이렉트 정보만 전달  
error  | 리다이렉트가 발생하면 오류



## Response
: Body 인터페이스 구현   

**속성**  
- Response.headers
- Response.ok
- Response.status
- Response.statusText
- Response.type
- Response.url
- Response.redirected

**메소드**
- Response.clone()
- Response.redirect()
- Response.error()



[top](#)
