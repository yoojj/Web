# Location API

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
href      | url 반환하거나 지정  
origin    | url 출처 반환
protocol  | url 스키마를 반환하거나 지정
host      | url 호스트와 포트 번호를 반환하거나 지정  
hostname  | url 호스트 이름을 반환하거나 지정  
port      | url 포트 번호를 반환하거나 지정  
pathname  | url 경로를 반환하거나 지정
search    | url 쿼리를 반환하거나 지정
hash      | url 해시를 반환하거나 지정
ancestorOrigins |


**assing()**    
: 주어진 url로 이동  
: 이동하기 전 페이지를 방문 스택에 기록함


**replace()**   
: 주어진 url로 이동  
: 이동하기 전 페이지를 방문 스택에서 제거함


**reload()**   
: 현재 페이지를 다시 로드함



[top](#)
