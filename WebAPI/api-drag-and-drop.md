# Drag and Drop API

https://html.spec.whatwg.org/multipage/dnd.html


```
[ drag ]       -->      [ drop ]
dragstart - dragenter - dragend
            dragover
            dragleave

drag : 요소 드래그
drop : 드래그한 요소를 드롭  

dragstart : 드래그 시작
dragend : 드래그 종료

dragenter : 드래그한 요소가 드롭 대상 위에 올라간 경우
dragover : 드래그한 요소가 드롭 대상 위를 지나갈 경우
dragleave : 드래그한 요소가 드롭 대상을 벗어날 경우


<tag ondrag="dragHandler(e)"
     ondrop="dropHandler(e)"
     ondragstart="dragStartHandler(e)"
     ondragend="dragEndHandler(e)"
     ondragover="dragOverHandler(e)"
     draggable="true">
```


**api**
- [DataTransfer](#datatransfer)
- [DataTransferItemList](#datatransferitemlist)
- [DataTransferItem](#datatransferitem)
- [DragEvent](#dataevent)



## DataTransfer

```webidl
[Exposed=Window]
interface DataTransfer {
  constructor();

  attribute DOMString dropEffect;
  attribute DOMString effectAllowed;

  [SameObject] readonly attribute DataTransferItemList items;

  undefined setDragImage(Element image, long x, long y);

  /* old interface */
  readonly attribute FrozenArray<DOMString> types;
  DOMString getData(DOMString format);
  undefined setData(DOMString format, DOMString data);
  undefined clearData(optional DOMString format);
  [SameObject] readonly attribute FileList files;
};
```



## DataTransferItemList

```webidl
interface DataTransferItemList {
  readonly attribute unsigned long length;
  getter DataTransferItem(unsigned long index);
  DataTransferItem? add(DOMString data, DOMString type);
  DataTransferItem? add(File data);
  undefined remove(unsigned long index);
  undefined clear();
};
```



## DataTransferItem

```webidl
[Exposed=Window]
interface DataTransferItem {
  readonly attribute DOMString kind;
  readonly attribute DOMString type;
  undefined getAsString(FunctionStringCallback? _callback);
  File? getAsFile();
};

callback FunctionStringCallback = undefined (DOMString data);
```



## DragEvent

```webidl
[Exposed=Window]
interface DragEvent : MouseEvent {
  constructor(DOMString type, optional DragEventInit eventInitDict = {});

  readonly attribute DataTransfer? dataTransfer;
};

dictionary DragEventInit : MouseEventInit {
  DataTransfer? dataTransfer = null;
};
```



[top](#)
