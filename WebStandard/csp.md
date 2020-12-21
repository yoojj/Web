# CSP
Content Security Policy  
: 콘텐츠 보안 정책    
: 악성 코드 삽입 공격을 방지하기 위해 도입된 보안 표준     
&nbsp; (XSS, Data Injection, Clickjacking 등 방지)    


- Policy Delivery
- Directives


https://www.w3.org/TR/CSP/   
https://w3c.github.io/webappsec-csp/   



## Policy Delivery
: 유저 에이전트에게 정책 전달   


**HTTP response header**
```bash
Content-Security-Policy:<policy>;
Content-Security-Policy-Report-Only:<policy>;

# IE 10~11 경우
X-Content-Security-Policy:<policy>;
```


**HTML meta tag**
```html
<meta http-equiv="Content-Security-Policy" content="<policy>">
```



## Directives

**Fetch Directives**

지시문 | 설명
---|---
child-src       |
connect-src     |
default-src     |
font-src        |
frame-src       |
img-src         |
manifest-src    |
media-src       |
prefetch-src    |
object-src      |
script-src      |
script-src-elem |
script-src-attr |
style-src       |
style-src-elem  |
style-src-attr  |
worker-src      |


**Document Directives**

지시문 | 설명
---|---
base-uri     |
plugin-types |
sandbox      |


**Navigation Directives**

지시문 | 설명
---|---
form-action     |
frame-ancestors |
navigate-to     |


**Reporting Directives**

지시문 | 설명
---|---
report-uri |
report-to  |


**Options**

값 | 설명
---|---
none  |
self  |
unsafe-inline |
unsafe-eval   |
strict-dynamic|



[top](#)
