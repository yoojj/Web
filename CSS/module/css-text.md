# CSS Text

https://www.w3.org/TR/css-text/  
https://www.w3.org/TR/css-text-4/


속성 | 설명
---|---
text-transform   | 텍스트의 대소문자 지정
white-space      | 공백 문자 처리 방법 지정  
tab-size         | 탭 문자의 크기 지정
word-break       | 한중일 텍스트가 박스를 벗어날 경우 처리 방법 지정  
line-break       | 한중일 텍스트가 줄 바꿈 방법 지정  
hyphens          | 줄 바꿈되는 단어에 하이픈 추가 여부 지정
overflow-wrap, word-wrap | 텍스트가 박스를 벗어날 경우 처리 방법 지정  
text-align       | text-align-* 속성 축약
text-align-all   | 텍스트의 정렬 방향 지정  
text-align-last  | 마지막 줄이나 강제 줄 바꿈되는 텍스트의 정렬 방향 지정  
text-justify     | 텍스트의 간격 지정  
word-spacing     | 단어 사이에 간격 지정  
letter-spacing   | 글자 사이에 간격 지정    
text-indent      | 텍스트에 들여쓰기 지정  


```css
E {text-transform:none | capitalize | uppercase | lowercase | full-width | full-size-kana;}
/*
- capitalize : 첫 글자만 대문자
- uppercase : 모든 글자 대문자
- lowercase : 모든 글자 소문자
*/


E {white-space:normal | pre | nowrap | pre-wrap | break-spaces | pre-line;}


E {tab-size:number | length;}


E {word-break:normal | keep-all | break-all | break-word;}
/*
- normal
- keep-all
- break-all
*/


E {line-break:auto | loose | normal | strict | anywhere;}


E {hyphens:none | manual | auto;}


E {overflow-wrap:normal | break-word | anywhere;}
E {word-wrap:normal | break-word | anywhere;}
/* 동일한 기능으로 word-wrap은 하위 브라우저를 위해 사용 */


E {text-align:start | end | left | right | center | justify | match-parent | justify-all;}

E {text-align-all:start | end | left | right | center | justify | match-parent;}

E {text-align-last:auto | start | end | left | right | center | justify | match-parent;}


E {text-justify:auto | none | inter-word | inter-character;}
/* text-align:justify;*/


E {word-spacing:normal | length;}


E {letter-spacing:normal | length;}


E {text-indent:length;}






```



[top](#)
