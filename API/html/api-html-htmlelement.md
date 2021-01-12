[HTMLElement](#htmlelement)  
[HTMLUnknownElement](#htmlunknownelement)



# HTMLElement

https://html.spec.whatwg.org/multipage/dom.html#htmlelement


```webidl
[Exposed=Window]
interface HTMLElement : Element {
  [HTMLConstructor] constructor();

  [CEReactions] attribute DOMString title;
  [CEReactions] attribute DOMString lang;
  [CEReactions] attribute boolean translate;
  [CEReactions] attribute DOMString dir;

  [CEReactions] attribute boolean hidden;
  undefined click();
  [CEReactions] attribute DOMString accessKey;
  readonly attribute DOMString accessKeyLabel;
  [CEReactions] attribute boolean draggable;
  [CEReactions] attribute boolean spellcheck;
  [CEReactions] attribute DOMString autocapitalize;

  [CEReactions] attribute [LegacyNullToEmptyString] DOMString innerText;

  ElementInternals attachInternals();
};

HTMLElement includes GlobalEventHandlers;
HTMLElement includes DocumentAndElementEventHandlers;
HTMLElement includes ElementContentEditable;
HTMLElement includes HTMLOrSVGElement;



/* CSSOM */
partial interface HTMLElement {
  readonly attribute Element? offsetParent;
  readonly attribute long offsetTop;
  readonly attribute long offsetLeft;
  readonly attribute long offsetWidth;
  readonly attribute long offsetHeight;
};

HTMLElement includes ElementCSSInlineStyle;
```



# HTMLUnknownElement

```webidl
[Exposed=Window]
interface HTMLUnknownElement : HTMLElement {};
```



[top](#)
