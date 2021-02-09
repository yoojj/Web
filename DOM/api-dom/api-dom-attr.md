# Attr

https://dom.spec.whatwg.org/#interface-attr


```webidl
[Exposed=Window]
interface Attr : Node {
  readonly attribute DOMString? namespaceURI;
  readonly attribute DOMString? prefix;
  readonly attribute DOMString localName;
  readonly attribute DOMString name;
  [CEReactions] attribute DOMString value;

  readonly attribute Element? ownerElement;

  readonly attribute boolean specified; // useless; always returns true
};
```


속성 | 설명
---|---
namespaceURI | 네임 스페이스 반환
prefix    | 네임 스페이스 접두사 반환
localName | 로컬 네임 반환
name      | 속성 이름 반환
value     | 속성 값 반환
ownerElement | 속성과 연결된 요소 반환


ex.
```html
<tag example="value">


<script>
var el = document.getElementsByTagName('tag')[0];

(el.attributes.example.name === 'example') == true
</script>
```



[top](#)
