# Location

https://html.spec.whatwg.org/multipage/history.html#the-location-interface


```webidl
[Exposed=Window]
interface Location {
  [LegacyUnforgeable] stringifier attribute USVString href;
  [LegacyUnforgeable] readonly attribute USVString origin;
  [LegacyUnforgeable] attribute USVString protocol;
  [LegacyUnforgeable] attribute USVString host;
  [LegacyUnforgeable] attribute USVString hostname;
  [LegacyUnforgeable] attribute USVString port;
  [LegacyUnforgeable] attribute USVString pathname;
  [LegacyUnforgeable] attribute USVString search;
  [LegacyUnforgeable] attribute USVString hash;

  [LegacyUnforgeable] undefined assign(USVString url);
  [LegacyUnforgeable] undefined replace(USVString url);
  [LegacyUnforgeable] undefined reload();

  [LegacyUnforgeable, SameObject] readonly attribute DOMStringList ancestorOrigins;
};
```


속성 | 설명
---|---
href      | URL을 반환하거나 지정  
origin    | URL 출처 반환
protocol  | URL 스키마를 반환하거나 지정
host      | URL 호스트명과 포트 번호를 반환하거나 지정  
hostname  | URL 호스트명을 반환하거나 지정  
port      | URL 포트 번호를 반환하거나 지정  
pathname  | URL 경로를 반환하거나 지정
search    | URL 쿼리를 반환하거나 지정
hash      | URL 해시를 반환하거나 지정
ancestorOrigins |


**assing()**    
: 주어진 URL로 이동  
: 이동하기 전에 페이지를 방문 스택에 기록함


**replace()**   
: 주어진 URL로 이동  
: 이동하기 전에 페이지를 방문 스택에서 제거함


**reload()**   
: 현재 페이지를 다시 로드함



[top](#)
