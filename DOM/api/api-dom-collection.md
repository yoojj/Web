# Collection API

**api**
- [NodeList](#nodelist)
- [HTMLCollection](#htmlcollection)



## NodeList

```webidl
[Exposed=Window]
interface NodeList {
  getter Node? item(unsigned long index);
  readonly attribute unsigned long length;
  iterable<Node>;
};
```



## HTMLCollection

```webidl
[Exposed=Window, LegacyUnenumerableNamedProperties]
interface HTMLCollection {
  readonly attribute unsigned long length;
  getter Element? item(unsigned long index);
  getter Element? namedItem(DOMString name);
};
```



[top](#)
