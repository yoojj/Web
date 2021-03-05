# HTTP Version

- [HTTP/0.9](#http09)
- [HTTP/1.0](#http10)
- [HTTP/1.1](./http-v1-1.md)
- [HTTP/2.0](./http-v2.md)
- [HTTP/3.0](./http-v3.md)


버전 | 특징
---|---
HTTP/0.9 (1991년~)| TCP/IP 기반 통신, HTTP 헤더 없음, GET 메소드만 존재
HTTP/1.0 (1996년~)| HTTP 헤더 지원, 상태 코드 지원, HTTP 메소드 추가
HTTP/1.1 (1999년~)| 캐시 지원, 파이프 라이닝 개념 도입, HTTP 메소드 추가
HTTP/2.0 (2015년~)| 헤더 압축, 메시지 캡슐화, 멀티플렉싱
HTTP/3.0 (2020년~)| UDP 기반 통신  



## HTTP/0.9
: World Wide Web을 위해 설계된 새로운 프로토콜    
: HTTP/1.0 표준이 발표되면서 구분을 위해 0.9라는 버전을 붙임   

- 클라이언트 요청은 GET 메소드와 문서 주소로 구성  
- 포트를 지정하지 않으면 80을 기본으로 사용
- 클라이언트 요청은 단일 ASCII 문자열
- 클라이언트 요청은 캐리지 리턴(CRLF)에 의해 종료  
- 서버 응답은 ASCII 문자의 바이트 스트림
- 서버 응답 객체는 HTML 문서만 가능
- 문서 전송이 완료되면 연결 종료



## HTTP/1.0
: HTTP 프로토콜 개선을 위해 IETF내에 HTTP Working Group 설립    
: HTTP WG에서 HTTP/1.0 문서 발표

RFC1945  
https://tools.ietf.org/html/rfc1945   


- HTTP 메소드 추가 (HEAD, POST)
- HTTP 헤더를 지원해 메타 데이터를 포함 (HTTP 버전, 상태 코드, 콘텐츠 타입)   
- 콘텐츠 타입을 지정해 HTML 문서 외 리소스를 응답 객체로 지원  

```bash
# Request
GET /text.txt HTTP/1.0
User-Agent:  
Accept:

# Response
HTTP/1.0 200 OK
Date:
Content-Type: text/plain
Content-Length:
Expires:
Last-Modified:
Server:

[txt contents]


## Request-Header
Authorization      
From
If-Modified-Since
Referer
User-Agent

## Response Status-Code
200 OK
201 Created
202 Accepted
204 No Content
301 Moved Permanently
302 Moved Temporarily
304 Not Modified
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
500 Internal Server Error
501 Not Implemented
502 Bad Gateway
503 Service Unavailable
```



[top](#)
