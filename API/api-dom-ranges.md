[AbstractRange](#abstractrange])  
[StaticRange](#staticrange])  
[Range](#range])



# AbstractRange

https://dom.spec.whatwg.org/#abstractrange

```webidl
[Exposed=Window]
interface AbstractRange {
  readonly attribute Node startContainer;
  readonly attribute unsigned long startOffset;
  readonly attribute Node endContainer;
  readonly attribute unsigned long endOffset;
  readonly attribute boolean collapsed;
};
```



# StaticRange

https://dom.spec.whatwg.org/#interface-staticrange

```webidl
[Exposed=Window]
interface StaticRange : AbstractRange {
  constructor(StaticRangeInit init);
};

dictionary StaticRangeInit {
  required Node startContainer;
  required unsigned long startOffset;
  required Node endContainer;
  required unsigned long endOffset;
};
```



# Range

```webidl
[Exposed=Window]
interface Range : AbstractRange {
  constructor();

  readonly attribute Node commonAncestorContainer;

  undefined setStart(Node node, unsigned long offset);
  undefined setEnd(Node node, unsigned long offset);
  undefined setStartBefore(Node node);
  undefined setStartAfter(Node node);
  undefined setEndBefore(Node node);
  undefined setEndAfter(Node node);
  undefined collapse(optional boolean toStart = false);
  undefined selectNode(Node node);
  undefined selectNodeContents(Node node);

  const unsigned short START_TO_START = 0;
  const unsigned short START_TO_END = 1;
  const unsigned short END_TO_END = 2;
  const unsigned short END_TO_START = 3;
  short compareBoundaryPoints(unsigned short how, Range sourceRange);

  [CEReactions] undefined deleteContents();
  [CEReactions, NewObject] DocumentFragment extractContents();
  [CEReactions, NewObject] DocumentFragment cloneContents();
  [CEReactions] undefined insertNode(Node node);
  [CEReactions] undefined surroundContents(Node newParent);

  [NewObject] Range cloneRange();
  undefined detach();

  boolean isPointInRange(Node node, unsigned long offset);
  short comparePoint(Node node, unsigned long offset);

  boolean intersectsNode(Node node);

  stringifier;
};
```



[top](#)
