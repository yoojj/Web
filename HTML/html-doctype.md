# DTD
Document Type Declaration    
: 브라우저에게 문서의 버전과 종류-형식을 알리기 위한 선언문      
: 선언한 독타입 규약에 따라 렌더링하므로 문서의 첫 줄에 선언    
: IE 경우 독타입을 선언하지 않으면 쿼크 모드로 렌더링    


**quirks mode**    
: IE 브라우저 경우 6,7,8,9 버전에서 IE5.5 버전으로 호환하기 위한 모드   
&nbsp; (compatibility mode는 IE7 버전을 기반으로 렌더링)

```html
<code>
    <p style="white-space:pre;">쿼크 모드에서 지원되지 않음</p>
    <p style="width:500px;margin:0 auto;">쿼크 모드에서 지원되지 않음</p>
</code>
```



## html5
: DTD-less Doctype   
: SGML 기반이 아니므로 DTD를 참조하지 않음   
: 생략할 경우 브라우저에 따라 렌더링 모드가 달라지는 경우가 있을 수 있으므로 생략하지 않음  


```html
<!doctype html>
```



## html4
: Doctype Sniffing, Doctype Switching   
: SGML 기반으로 DTD를 참조하므로 DTD 식별자 명시 필수     


**종류**  
- 완전 표준 모드
- 유사 표준 모드 : 표준 모드로 동작 + 몇몇의 호환 모드 지원
- 엄격 모드


```html
<!-- 표준 모드 -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">


<!-- 유사 표준 모드 -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```



[top](#)
