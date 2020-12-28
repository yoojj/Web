# Service Worker API

https://www.w3.org/TR/service-workers/


**api**
- ServiceWorker
- ServiceWorkerRegistration
- ServiceWorkerContainer
- ServiceWorkerGlobalScope
- Client
- Clients
- ExtendableEvent
- FetchEvent
- ExtendableMessageEvent
- [Cache](#cache)
- [CacheStorage](#cachestorage)



## ServiceWorker

```webidl
[SecureContext, Exposed=(Window,Worker)]
interface ServiceWorker : EventTarget {
  readonly attribute USVString scriptURL;
  readonly attribute ServiceWorkerState state;
  void postMessage(any message, optional sequence<object> transfer = []);

  attribute EventHandler onstatechange;
};

ServiceWorker includes AbstractWorker;

enum ServiceWorkerState { "installing", "installed", "activating",
  "activated", "redundant" };
```



## ServiceWorkerRegistration

```webidl
[SecureContext, Exposed=(Window,Worker)]
interface ServiceWorkerRegistration : EventTarget {
  readonly attribute ServiceWorker? installing;
  readonly attribute ServiceWorker? waiting;
  readonly attribute ServiceWorker? active;

  readonly attribute USVString scope;
  readonly attribute ServiceWorkerUpdateViaCache updateViaCache;

  [NewObject] Promise<void> update();
  [NewObject] Promise<boolean> unregister();

  attribute EventHandler onupdatefound;
};

enum ServiceWorkerUpdateViaCache { "imports", "all", "none" };
```



## ServiceWorkerContainer

```webidl
[SecureContext, Exposed=(Window,Worker)]
interface ServiceWorkerContainer : EventTarget {
  readonly attribute ServiceWorker? controller;
  readonly attribute Promise<ServiceWorkerRegistration> ready;

  [NewObject] Promise<ServiceWorkerRegistration> register(USVString scriptURL, optional RegistrationOptions options = {});

  [NewObject] Promise<any> getRegistration(optional USVString clientURL = "");
  [NewObject] Promise<FrozenArray<ServiceWorkerRegistration>> getRegistrations();

  void startMessages();

  attribute EventHandler oncontrollerchange;
  attribute EventHandler onmessage;  
  attribute EventHandler onmessageerror;
};

dictionary RegistrationOptions {
  USVString scope;
  WorkerType type = "classic";
  ServiceWorkerUpdateViaCache updateViaCache = "imports";
};
```



## ServiceWorkerGlobalScope

```webidl
[Global=(Worker,ServiceWorker), Exposed=ServiceWorker]
interface ServiceWorkerGlobalScope : WorkerGlobalScope {
  [SameObject] readonly attribute Clients clients;
  [SameObject] readonly attribute ServiceWorkerRegistration registration;

  [NewObject] Promise<void> skipWaiting();

  attribute EventHandler oninstall;
  attribute EventHandler onactivate;
  attribute EventHandler onfetch;

  attribute EventHandler onmessage;
  attribute EventHandler onmessageerror;
};
```



## Client

```webidl
[Exposed=ServiceWorker]
interface Client {
  readonly attribute USVString url;
  readonly attribute FrameType frameType;
  readonly attribute DOMString id;
  readonly attribute ClientType type;
  void postMessage(any message, optional sequence<object> transfer = []);
};

[Exposed=ServiceWorker]
interface WindowClient : Client {
  readonly attribute VisibilityState visibilityState;
  readonly attribute boolean focused;
  [SameObject] readonly attribute FrozenArray<USVString> ancestorOrigins;
  [NewObject] Promise<WindowClient> focus();
  [NewObject] Promise<WindowClient?> navigate(USVString url);
};

enum FrameType { "auxiliary", "top-level", "nested", "none" };
```



## Clients

```webidl
[Exposed=ServiceWorker]
interface Clients {
  [NewObject] Promise<any> get(DOMString id);
  [NewObject] Promise<FrozenArray<Client>> matchAll(optional ClientQueryOptions options = {});
  [NewObject] Promise<WindowClient?> openWindow(USVString url);
  [NewObject] Promise<void> claim();
};

dictionary ClientQueryOptions {
  boolean includeUncontrolled = false;
  ClientType type = "window";
};

enum ClientType { "window", "worker", "sharedworker", "all" };
```



## Cache

```webidl
[SecureContext, Exposed=(Window,Worker)]
interface Cache {
  [NewObject] Promise<any> match(RequestInfo request, optional CacheQueryOptions options = {});
  [NewObject] Promise<FrozenArray<Response>> matchAll(optional RequestInfo request, optional CacheQueryOptions options = {});
  [NewObject] Promise<void> add(RequestInfo request);
  [NewObject] Promise<void> addAll(sequence<RequestInfo> requests);
  [NewObject] Promise<void> put(RequestInfo request, Response response);
  [NewObject] Promise<boolean> delete(RequestInfo request, optional CacheQueryOptions options = {});
  [NewObject] Promise<FrozenArray<Request>> keys(optional RequestInfo request, optional CacheQueryOptions options = {});
};

dictionary CacheQueryOptions {
  boolean ignoreSearch = false;
  boolean ignoreMethod = false;
  boolean ignoreVary = false;
};
```



## CacheStorage

```webidl
[SecureContext, Exposed=(Window,Worker)]
interface CacheStorage {
  [NewObject] Promise<any> match(RequestInfo request, optional MultiCacheQueryOptions options = {});
  [NewObject] Promise<boolean> has(DOMString cacheName);
  [NewObject] Promise<Cache> open(DOMString cacheName);
  [NewObject] Promise<boolean> delete(DOMString cacheName);
  [NewObject] Promise<sequence<DOMString>> keys();
};

dictionary MultiCacheQueryOptions : CacheQueryOptions {
  DOMString cacheName;
};
```



[top](#)
