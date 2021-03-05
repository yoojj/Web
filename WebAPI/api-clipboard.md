# Clipboard API

https://www.w3.org/TR/clipboard-apis/


**api**
- ClipboardEvent
- Clipboard
- ClipboardItem



## ClipboardEvent

```webidl
[Exposed=Window]
interface ClipboardEvent : Event {
  constructor(DOMString type, optional ClipboardEventInit eventInitDict = {});
  readonly attribute DataTransfer? clipboardData;
};

dictionary ClipboardEventInit : EventInit {
  DataTransfer? clipboardData = null;
};
```



## Clipboard

```webidl
[SecureContext, Exposed=Window] interface Clipboard : EventTarget {
  Promise<ClipboardItems> read();
  Promise<DOMString> readText();
  Promise<undefined> write(ClipboardItems data);
  Promise<undefined> writeText(DOMString data);
};

typedef sequence<ClipboardItem> ClipboardItems;
```



## ClipboardItem

```webidl
[Exposed=Window] interface ClipboardItem {
  constructor(record<DOMString, ClipboardItemData> items,
    optional ClipboardItemOptions options = {});

  static ClipboardItem createDelayed(
      record<DOMString, ClipboardItemDelayedCallback> items,
      optional ClipboardItemOptions options = {});

  readonly attribute PresentationStyle presentationStyle;
  readonly attribute long long lastModified;
  readonly attribute boolean delayed;

  readonly attribute FrozenArray<DOMString> types;

  Promise<Blob> getType(DOMString type);
};

typedef (DOMString or Blob) ClipboardItemDataType;
typedef Promise<ClipboardItemDataType> ClipboardItemData;

callback ClipboardItemDelayedCallback = ClipboardItemData();

dictionary ClipboardItemOptions {
  PresentationStyle presentationStyle = "unspecified";
};

enum PresentationStyle { "unspecified", "inline", "attachment" };
```



[top](#)
