# CSSOM

https://www.w3.org/TR/cssom/#the-stylesheet-interface  



# StyleSheet

```webidl
[Exposed=Window]
interface StyleSheet {
  readonly attribute CSSOMString type;
  readonly attribute USVString? href;
  readonly attribute (Element or ProcessingInstruction)? ownerNode;
  readonly attribute CSSStyleSheet? parentStyleSheet;
  readonly attribute DOMString? title;
  [SameObject, PutForwards=mediaText] readonly attribute MediaList media;
  attribute boolean disabled;
};
```


속성 | 설명
---|---
type  | 스타일 시트 타입 반환
href  | 스타일 시트 위치 반환
ownerNode        | 스타일 시트와 연결된 노드 반환
parentStyleSheet | 스타일 시트의 부모 스타일 시트 반환
title | 스타일 시트의 타이틀을 반환하며 타이틀이 없으면 null 반환
media | 스타일 시트의 미디어 반환
disabled | 스타일 시트 적용 여부 지정    



# CSSStyleSheet

```webidl
interface CSSStyleSheet : StyleSheet {
  readonly attribute CSSRule? ownerRule;
  [SameObject] readonly attribute CSSRuleList cssRules;
  unsigned long insertRule(DOMString rule, unsigned long index);
  void deleteRule(unsigned long index);
};
```


속성 | 설명
---|---
ownerRule | 스타일 시트의 at-rule 정보를 담은 CSSRule 객체 반환
cssRules  | 스타일 시트의 규칙 정보를 담은 CSSRuleList 객체 반환  


**insertRule()**   
: 주어진 스타일 시트 규칙을 현재 스타일 시트에 추가함  

```js
el.insertRule('E {property:value;}', 'index');
```



# StyleSheetList
: 문서의 StyleSheet 객체 목록 반환   

```webidl
[ArrayClass]
interface StyleSheetList {
  getter StyleSheet? item(unsigned long index);
  readonly attribute unsigned long length;
};

/*
partial interface Document {
  [SameObject] readonly attribute StyleSheetList styleSheets;
};
*/
```

ex.
```js
for(var i = 0; i < document.styleSheets.length; i++) {
    var css = document.styleSheets[i];
}
```



[top](#)
