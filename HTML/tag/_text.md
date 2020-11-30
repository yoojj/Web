# text
: 텍스트의 의미나 목적을 나타내기 위한 태그  
: 텍스트의 시각적인 변화에 영향주는 태그 존재    


태그 | 설명
---|---
h1 ~ h6   | 제목  
p         | 문단
dt-dd     | 정렬되는 목록의 용어와 설명
li        | 정렬되지 않는 목록
figure    | figcaption 설명   
blockquot | 블록 인용
pre       | 특수 문자, 공백 등 입력한 내용을 그대로 출력  


```html
<hgroup>
    <h1>제목</h1>
    <h2>부제목</h2>
</hgroup>


<style>
pre {
    white-space:pre;
}
</style>

<pre>
공백과
줄바꿈 유지
</pre>
```


**인라인 텍스트**

태그 | 설명
---|---
a      | 하이퍼 링크  
time   | 컴퓨터가 판독 가능한 날짜 및 시간 데이터를 나타냄   
var    | 소스 코드의 변수를 나타냄  
data   | 프로그램 결과물을 나타냄
samp   | 소스 코드 샘플이나 프로그램 결과물을 나타냄
kbd    | 키보드 등의 사용자 입력 장치를 나타냄  
strong | 텍스트의 중요성, 심각성, 긴급성을 나타내기 위해 글자를 굵게함
mark   | 텍스트를 강조하기 위해 글자에 하이라이트
em     | 주변 텍스트에서 해당 텍스트를 강조하기 위해 글자를 기울임
b      | 주변 텍스트에서 해당 텍스트를 구분하기 위해 글자를 굵게함
i      | 주변 텍스트에서 해당 텍스트를 구분하기 위해 글자를 기울임
u      | 텍스트 주석을 나타내며 글자에 밑줄을 표현
small  | 주석같은 덧붙이는 텍스트를 위해 글자를 작게함<br>(작은 글자 표현을 위해 사용하지 말 것)
s      | 관련없어진 텍스트를 위해 글자에 취소선을 표현
q      | 짧은 문장, 저작원 등 인라인 인용을 나타냄
cite   | 노래, 책, 블로그 등의 인용 제목, 저자, url같은 참조를 나타냄
dfn    | 정의하고 있는 용어를 나타냄  
abbr   | 약어, 약자를 나타냄
ruby   | 문자의 발음 기호를 나타냄  
sub    | 아래 첨자
sup    | 윗 첨자
bdi    | 텍스트 방향성 분리
bdo    | 텍스트 방향성 재정의
br     | 텍스트 줄바꿈 강제 (그룹을 구분하기 위해 사용하지 말 것)
wbr    | 텍스트나 단어가 줄바꿈 될 위치 지정



```html
<!-- kbd -->
<style>
kbd {padding:3px;border-radius:3px;background:#ccc;}
</style>
<kbd>Ctrl</kbd> + <kbd>c</kbd>


<!-- blockquote vs q vs cite -->
<blockquote cite="https://www.w3.org/">
    <q cite="https://www.w3.org/">
    The World Wide Web Consortium <cite>(W3C)</cite> is an international community
    </q>
</blockquote>


<!-- dfn -->
<p>
    <dfn>W3C</dfn> World Wide Web Consortium
<p>


<!-- dfn vs abbr -->
<p>
    The <dfn><abbr title="World Wide Web Consortium">W3C</abbr></dfn> is an international community
</p>


<!-- wbr -->
<p style="width:230px;border:1px solid red;">
    The World Wide Web Consortium<wbr>(W3C) is an international community
</p>
```



[top](#)
