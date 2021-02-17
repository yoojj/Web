# Permission API

https://www.w3.org/TR/permissions/


**api**
- PermissionStatus
- Permissions



## PermissionStatus

```webidl
[Exposed=(Window,Worker)]
interface PermissionStatus : EventTarget {
  readonly attribute PermissionState state;
  attribute EventHandler onchange;
};

enum PermissionState {
  "granted",
  "denied",
  "prompt",
};
```



## Permissions

```webidl
[Exposed=(Window,Worker)]
interface Permissions {
  Promise<PermissionStatus> query(object permissionDesc);
};

dictionary PermissionDescriptor {
  required PermissionName name;
};

enum PermissionName {
  "geolocation",
  "notifications",
  "push",
  "midi",
  "camera",
  "microphone",
  "speaker",
  "device-info",
  "background-fetch",
  "background-sync",
  "bluetooth",
  "persistent-storage",
  "ambient-light-sensor",
  "accelerometer",
  "gyroscope",
  "magnetometer",
  "clipboard-read",
  "clipboard-write",
  "display-capture",
  "nfc",
};
```



[top](#)
