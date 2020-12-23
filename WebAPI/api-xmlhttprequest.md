# XMLHttpRequest API   


https://xhr.spec.whatwg.org/



## API

- Window.XMLHttpRequest
- DedicatedWorker.XMLHttpRequest
- SharedWorker.XMLHttpRequest


**XMLHttpRequestEventTarget**
- onloadstart
- onprogress
- onabort
- onerror
- onload
- ontimeout
- onloadend


**XMLHttpRequest** : XMLHttpRequestEventTarget 상속  
- constructor()
- onreadystatechange
- UNSENT
- OPENED
- HEADERS_RECEIVED
- LOADING
- DONE
- readyState : XMLHttpRequest 객체의 상태 반환  
- open(method, url)
- open(method, url, async, username = null, password = null)
- setRequestHeader(name, value) : 요청 헤더 지정
- timeout : 요청 종료 시간 지정
- withCredentials : 자격 증명(쿠키를 요청에 포함) 여부 지정
- upload : 진행 상황을 모니터링하기 위한 XMLHttpRequestUpload 객체 반환  
- send(Document | XMLHttpRequestBodyInit)
- abort() : 요청된 경우 요청을 중단하기 위한 메소드  
- responseURL
- status : 응답 코드 반환
- statusText : 응답 문자열 반환
- getResponseHeader(name) : 특정 응답 헤더 반환
- getAllResponseHeaders() : 모든 응답 헤더 반환
- overrideMimeType(mime) : 응답 받을 데이터의 MIME 유형을 변경해서 받음
- responseType : XMLHttpRequestResponseType 반환
- response : 응답 반환
- responseText : 응답을 문자열 형태로 반환
- responseXML : 응답 반환


값 | 상태 | 설명
---|---|---
0 | UNSENT | 객체는 생성되었으나 open() 메소드를 통해 요청이 초기화되지 않음
1 | OPENED | open() 메소드 호출
2 | HEADERS_RECEIVED | send() 메소드 호출
3 | LOADING | 요청 처리중이며 일부 데이터 수신 가능
4 | DONE    | 모든 요청 처리


**XMLHttpRequestUpload** : XMLHttpRequestEventTarget 상속  
- onloadstart : 업로드 시작
- onprogress : 현재 진행 상황  
- onabort : 업로드 중단
- onerror : 업로드 오류
- onload : 업로드 완료
- ontimeout : 업로드 시간 초과
- onloadend : (성공과 실패에 상관없이) 업로드 종료


**XMLHttpRequestBodyInit**
- Blob
- BufferSource
- FormData
- URLSearchParams
- USVString


**XMLHttpRequestResponseType**
- 'arraybuffer'
- 'blob'
- 'document'
- 'json'
- 'text'


ex.
```js
var xhr = new XMLHttpRequest();

xhr.setRequestHeader('content-type', 'text/plain');

// MIME 유형 변경
xhr.overrideMimeType('application/json');

// 타임아웃 설정
xhr.timeout = 3000;

xhr.open('POST', 'url', true);


// readyState가 변경되면 onreadystatechange 이벤트 발생
// readyState가 총 5번 변경되므로 onreadystatechange 이벤트도 5번 발생
xhr.onload = function() {
    if(this.readyState == XMLHttpRequest.DONE && this.status == 200){
        console.log(this.responseText);
    } else {
        console.log ('error');
    }
}


// 타임아웃 됐을 경우
xhr.ontimeout = function() {};

xhr.send();
```



[top](#)
