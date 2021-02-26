# Text

https://dom.spec.whatwg.org/#interface-text


```webidl
[Exposed=Window]
interface Text : CharacterData {
  constructor(optional DOMString data = "");

  [NewObject] Text splitText(unsigned long offset);
  readonly attribute DOMString wholeText;
};
```


**wholeText**   
: 텍스트 데이터 반환   

```html
<tag>text</tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

(tag.firstChild.data === tag.firstChild.wholeText) == true
</script>
```



**splitText()**   
: 주어진 오프셋 이후의 텍스트 노드 반환   

```html
<tag>text</tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

var result = tag.firstChild.splitText(1);
(result.data === 'ext') == true
</script>
```



[top](#)
