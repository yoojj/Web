# Typed OM
CSS Typed Object Model   
: CSSOM을 확장한 인터페이스       

https://www.w3.org/TR/css-typed-om/


ex.
```js
// CSSOM
el.style.opacity = 0.5;
el.style.opacity;

// Typed OM
el.attributeStyleMap.set('opacity', 0.5);
el.attributeStyleMap.set('opacity', '0.5');
el.attributeStyleMap.set('opacity', CSS.number(0.5));
el.attributeStyleMap.get('opacity').value;
```



## CSSStyleValue

```webidl
[Exposed=(Window, Worker, PaintWorklet, LayoutWorklet)]
interface CSSStyleValue {
    stringifier;
    [Exposed=Window] static CSSStyleValue parse(USVString property, USVString cssText);
    [Exposed=Window] static sequence<CSSStyleValue> parseAll(USVString property, USVString cssText);
};
```



## StylePropertyMapReadOnly

```webidl
[Exposed=(Window, Worker, PaintWorklet, LayoutWorklet)]
interface StylePropertyMapReadOnly {
    iterable<USVString, sequence<CSSStyleValue>>;
    any get(USVString property);
    sequence<CSSStyleValue> getAll(USVString property);
    boolean has(USVString property);
    readonly attribute unsigned long size;
};
```



## StylePropertyMap

```webidl
[Exposed=Window]
interface StylePropertyMap : StylePropertyMapReadOnly {
    void set(USVString property, (CSSStyleValue or USVString)... values);
    void append(USVString property, (CSSStyleValue or USVString)... values);
    void delete(USVString property);
    void clear();
};
```



## CSSUnparsedValue

```webidl
[Exposed=(Window, Worker, PaintWorklet, LayoutWorklet),
 Constructor(sequence<CSSUnparsedSegment> members)]
interface CSSUnparsedValue : CSSStyleValue {
    iterable<CSSUnparsedSegment>;
    readonly attribute unsigned long length;
    getter CSSUnparsedSegment (unsigned long index);
    setter CSSUnparsedSegment (unsigned long index, CSSUnparsedSegment val);
};

typedef (USVString or CSSVariableReferenceValue) CSSUnparsedSegment;

[Exposed=(Window, Worker, PaintWorklet, LayoutWorklet),
 Constructor(USVString variable, optional CSSUnparsedValue? fallback = null)]
interface CSSVariableReferenceValue {
    attribute USVString variable;
    readonly attribute CSSUnparsedValue? fallback;
};
```



[top](#)
