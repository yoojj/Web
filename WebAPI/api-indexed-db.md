# Indexed Database API      
: 유저 에이전트에 데이터를 영구적으로 저장하기 위한 API     
: 키/값 기반으로 데이터를 관리      

https://www.w3.org/TR/IndexedDB/    
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/Modules/indexeddb


**api**
- [IDBRequest](#idbrequest)
- [IDBFactory](#idbfactory)
- [IDBDatabase](#idbdatabase)
- [IDBObjectStore](#idbobjectstore)
- [IDBIndex](#idbindex)
- [IDBKeyRange](#idbkeyrange)
- [IDBCursor](#idbcursor)
- [IDBTransaction](#idbtransaction)


ex.
```js
/*
interface WindowOrWorkerGlobalScope {
  [SameObject] readonly attribute IDBFactory indexedDB;
};
*/

var indexedDB = window.indexedDB;
var request = indexedDB.open('database');

request.onupgradeneeded = function(e){

     var db = request.result;
     var store = db.createObjectStore('name', {keyPath: 'key'});

     store.createIndex('name', 'name', {unique: true});

};
```



## IDBRequest

```webidl
[Exposed=(Window,Worker)]
interface IDBRequest : EventTarget {
  readonly attribute any result;
  readonly attribute DOMException? error;
  readonly attribute (IDBObjectStore or IDBIndex or IDBCursor)? source;
  readonly attribute IDBTransaction? transaction;
  readonly attribute IDBRequestReadyState readyState;

  attribute EventHandler onsuccess;
  attribute EventHandler onerror;
};

enum IDBRequestReadyState { "pending", "done" };


[Exposed=(Window,Worker)]
interface IDBOpenDBRequest : IDBRequest {
  attribute EventHandler onblocked;
  attribute EventHandler onupgradeneeded;
};


[Exposed=(Window,Worker),
  Constructor(DOMString type, optional IDBVersionChangeEventInit eventInitDict)]
interface IDBVersionChangeEvent : Event {
  readonly attribute unsigned long long oldVersion;
  readonly attribute unsigned long long? newVersion;
};

dictionary IDBVersionChangeEventInit : EventInit {
  unsigned long long oldVersion = 0;
  unsigned long long? newVersion = null;
};


[Exposed=(Window,Worker),
 Constructor(DOMString type, optional IDBVersionChangeEventInit eventInitDict)]
interface IDBVersionChangeEvent : Event {
  readonly attribute unsigned long long oldVersion;
  readonly attribute unsigned long long? newVersion;
};

dictionary IDBVersionChangeEventInit : EventInit {
  unsigned long long oldVersion = 0;
  unsigned long long? newVersion = null;
};
```



## IDBFactory

```webidl
[Exposed=(Window,Worker)]
interface IDBFactory {
  [NewObject] IDBOpenDBRequest open(
      DOMString name,
      optional [EnforceRange] unsigned long long version);
  [NewObject] IDBOpenDBRequest deleteDatabase(DOMString name);

  short cmp(any first, any second);
};
```



## IDBDatabase

```webidl
[Exposed=(Window,Worker)]
interface IDBDatabase : EventTarget {
  readonly attribute DOMString name;
  readonly attribute unsigned long long version;
  readonly attribute DOMStringList objectStoreNames;

  [NewObject] IDBTransaction transaction(
      (DOMString or sequence<DOMString>) storeNames,
      optional IDBTransactionMode mode = "readonly");

  void close();

  [NewObject] IDBObjectStore createObjectStore(
      DOMString name,
      optional IDBObjectStoreParameters options);

  void deleteObjectStore(DOMString name);

  attribute EventHandler onabort;
  attribute EventHandler onclose;
  attribute EventHandler onerror;
  attribute EventHandler onversionchange;
};

dictionary IDBObjectStoreParameters {
  (DOMString or sequence<DOMString>)? keyPath = null;
  boolean autoIncrement = false;
};
```



## IDBObjectStore

```webidl
[Exposed=(Window,Worker)]
interface IDBObjectStore {
  attribute DOMString name;
  readonly attribute any keyPath;
  readonly attribute DOMStringList indexNames;
  [SameObject] readonly attribute IDBTransaction transaction;
  readonly attribute boolean autoIncrement;

  [NewObject] IDBRequest put(any value, optional any key);
  [NewObject] IDBRequest add(any value, optional any key);
  [NewObject] IDBRequest delete(any query);
  [NewObject] IDBRequest clear();
  [NewObject] IDBRequest get(any query);
  [NewObject] IDBRequest getKey(any query);
  [NewObject] IDBRequest getAll(
      optional any query,
      optional [EnforceRange] unsigned long count);
  [NewObject] IDBRequest getAllKeys(
      optional any query,
      optional [EnforceRange] unsigned long count);
  [NewObject] IDBRequest count(optional any query);

  [NewObject] IDBRequest openCursor(
      optional any query,
      optional IDBCursorDirection direction = "next");
  [NewObject] IDBRequest openKeyCursor(
      optional any query,
      optional IDBCursorDirection direction = "next");

  IDBIndex index(DOMString name);

  [NewObject] IDBIndex createIndex(
      DOMString name,
      (DOMString or sequence<DOMString>) keyPath,
      optional IDBIndexParameters options);
  void deleteIndex(DOMString name);
};

dictionary IDBIndexParameters {
  boolean unique = false;
  boolean multiEntry = false;
};
```



## IDBIndex

```webidl
[Exposed=(Window,Worker)]
interface IDBIndex {
  attribute DOMString name;
  [SameObject] readonly attribute IDBObjectStore objectStore;
  readonly attribute any keyPath;
  readonly attribute boolean multiEntry;
  readonly attribute boolean unique;

  [NewObject] IDBRequest get(any query);
  [NewObject] IDBRequest getKey(any query);
  [NewObject] IDBRequest getAll(
      optional any query,
      optional [EnforceRange] unsigned long count);
  [NewObject] IDBRequest getAllKeys(
      optional any query,
      optional [EnforceRange] unsigned long count);
  [NewObject] IDBRequest count(optional any query);

  [NewObject] IDBRequest openCursor(
      optional any query,
      optional IDBCursorDirection direction = "next");
  [NewObject] IDBRequest openKeyCursor(
      optional any query,
      optional IDBCursorDirection direction = "next");
};
```



## IDBKeyRange

```webidl
[Exposed=(Window,Worker)]
interface IDBKeyRange {
  readonly attribute any lower;
  readonly attribute any upper;
  readonly attribute boolean lowerOpen;
  readonly attribute boolean upperOpen;

  [NewObject] static IDBKeyRange only(any value);
  [NewObject] static IDBKeyRange lowerBound(
      any lower, optional boolean open = false);
  [NewObject] static IDBKeyRange upperBound(
      any upper, optional boolean open = false);
  [NewObject] static IDBKeyRange bound(
      any lower, any upper,
      optional boolean lowerOpen = false,
      optional boolean upperOpen = false);

  boolean _includes(any key);
};
```



## IDBCursor

```webidl
[Exposed=(Window,Worker)]
interface IDBCursor {
  readonly attribute (IDBObjectStore or IDBIndex) source;
  readonly attribute IDBCursorDirection direction;
  readonly attribute any key;
  readonly attribute any primaryKey;

  void advance([EnforceRange] unsigned long count);
  void continue(optional any key);
  void continuePrimaryKey(any key, any primaryKey);

  [NewObject] IDBRequest update(any value);
  [NewObject] IDBRequest delete();
};

enum IDBCursorDirection { "next", "nextunique", "prev", "prevunique" };
```



## IDBTransaction

```webidl
[Exposed=(Window,Worker)]
interface IDBTransaction : EventTarget {
  readonly attribute DOMStringList objectStoreNames;
  readonly attribute IDBTransactionMode mode;
  [SameObject] readonly attribute IDBDatabase db;
  readonly attribute DOMException error;

  IDBObjectStore objectStore(DOMString name);
  void abort();

  attribute EventHandler onabort;
  attribute EventHandler oncomplete;
  attribute EventHandler onerror;
};

enum IDBTransactionMode { "readonly", "readwrite", "versionchange" };
```



[top](#)
