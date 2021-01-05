# Mixin API

- NonElementParentNode
- DocumentOrShadowRoot
- ParentNode
- NonDocumentTypeChildNode
- ChildNode
- Slottable



## NonElementParentNode

```webidl
interface mixin NonElementParentNode {
  Element? getElementById(DOMString elementId);
};

Document includes NonElementParentNode;
DocumentFragment includes NonElementParentNode;
```



## DocumentOrShadowRoot

```webidl
interface mixin DocumentOrShadowRoot {};

Document includes DocumentOrShadowRoot;
ShadowRoot includes DocumentOrShadowRoot;
```



## ParentNode

```webidl
interface mixin ParentNode {
  [SameObject] readonly attribute HTMLCollection children;
  readonly attribute Element? firstElementChild;
  readonly attribute Element? lastElementChild;
  readonly attribute unsigned long childElementCount;

  [CEReactions, Unscopable] undefined prepend((Node or DOMString)... nodes);
  [CEReactions, Unscopable] undefined append((Node or DOMString)... nodes);
  [CEReactions, Unscopable] undefined replaceChildren((Node or DOMString)... nodes);

  Element? querySelector(DOMString selectors);
  [NewObject] NodeList querySelectorAll(DOMString selectors);
};

Document includes ParentNode;
DocumentFragment includes ParentNode;
Element includes ParentNode;
```



## NonDocumentTypeChildNode

```webidl
interface mixin NonDocumentTypeChildNode {
  readonly attribute Element? previousElementSibling;
  readonly attribute Element? nextElementSibling;
};

Element includes NonDocumentTypeChildNode;
CharacterData includes NonDocumentTypeChildNode;
```



## ChildNode

```webidl
interface mixin ChildNode {
  [CEReactions, Unscopable] undefined before((Node or DOMString)... nodes);
  [CEReactions, Unscopable] undefined after((Node or DOMString)... nodes);
  [CEReactions, Unscopable] undefined replaceWith((Node or DOMString)... nodes);
  [CEReactions, Unscopable] undefined remove();
};

DocumentType includes ChildNode;
Element includes ChildNode;
CharacterData includes ChildNode;
```



## Slottable

```webidl
interface mixin Slottable {
  readonly attribute HTMLSlotElement? assignedSlot;
};

Element includes Slottable;
Text includes Slottable;
```



[top](#)
