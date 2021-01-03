# HTMLMediaElement API  

https://html.spec.whatwg.org/multipage/media.html#htmlmediaelement


- HTMLMediaElement
- MediaError
- TimeRanges
- ...



## HTMLMediaElement

```webidl
[Exposed=Window]
interface HTMLMediaElement : HTMLElement {

  readonly attribute MediaError? error;

  [CEReactions] attribute USVString src;
  attribute MediaProvider? srcObject;
  readonly attribute USVString currentSrc;
  [CEReactions] attribute DOMString? crossOrigin;
  const unsigned short NETWORK_EMPTY = 0;
  const unsigned short NETWORK_IDLE = 1;
  const unsigned short NETWORK_LOADING = 2;
  const unsigned short NETWORK_NO_SOURCE = 3;
  readonly attribute unsigned short networkState;
  [CEReactions] attribute DOMString preload;
  readonly attribute TimeRanges buffered;
  undefined load();
  CanPlayTypeResult canPlayType(DOMString type);

  const unsigned short HAVE_NOTHING = 0;
  const unsigned short HAVE_METADATA = 1;
  const unsigned short HAVE_CURRENT_DATA = 2;
  const unsigned short HAVE_FUTURE_DATA = 3;
  const unsigned short HAVE_ENOUGH_DATA = 4;
  readonly attribute unsigned short readyState;
  readonly attribute boolean seeking;

  attribute double currentTime;
  undefined fastSeek(double time);
  readonly attribute unrestricted double duration;
  object getStartDate();
  readonly attribute boolean paused;
  attribute double defaultPlaybackRate;
  attribute double playbackRate;
  attribute boolean preservesPitch;
  readonly attribute TimeRanges played;
  readonly attribute TimeRanges seekable;
  readonly attribute boolean ended;
  [CEReactions] attribute boolean autoplay;
  [CEReactions] attribute boolean loop;
  Promise<undefined> play();
  undefined pause();

  [CEReactions] attribute boolean controls;
  attribute double volume;
  attribute boolean muted;
  [CEReactions] attribute boolean defaultMuted;

  [SameObject] readonly attribute AudioTrackList audioTracks;
  [SameObject] readonly attribute VideoTrackList videoTracks;
  [SameObject] readonly attribute TextTrackList textTracks;
  TextTrack addTextTrack(TextTrackKind kind, optional DOMString label = "", optional DOMString language = "");
};

enum CanPlayTypeResult { "", "maybe", "probably" };

typedef (MediaStream or MediaSource or Blob) MediaProvider;
```



## MediaError

```webidl
[Exposed=Window]
interface MediaError {
  const unsigned short MEDIA_ERR_ABORTED = 1;
  const unsigned short MEDIA_ERR_NETWORK = 2;
  const unsigned short MEDIA_ERR_DECODE = 3;
  const unsigned short MEDIA_ERR_SRC_NOT_SUPPORTED = 4;

  readonly attribute unsigned short code;
  readonly attribute DOMString message;
};
```



## TimeRanges

```webidl
[Exposed=Window]
interface TimeRanges {
  readonly attribute unsigned long length;
  double start(unsigned long index);
  double end(unsigned long index);
};
```



[top](#)
