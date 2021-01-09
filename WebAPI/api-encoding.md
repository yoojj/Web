# Encoding API

https://encoding.spec.whatwg.org/


**api**
- TextDecoderCommon
- TextDecoder
- TextEncoderCommon
- TextEncoder
- TextDecoderStream
- TextEncoderStream



## TextDecoderCommon

```webidl
interface mixin TextDecoderCommon {
  readonly attribute DOMString encoding;
  readonly attribute boolean fatal;
  readonly attribute boolean ignoreBOM;
};
```



## TextDecoder

```webidl
[Exposed=(Window,Worker)]
interface TextDecoder {
  constructor(optional DOMString label = "utf-8", optional TextDecoderOptions options = {});

  USVString decode(optional [AllowShared] BufferSource input, optional TextDecodeOptions options = {});
};

dictionary TextDecoderOptions {
  boolean fatal = false;
  boolean ignoreBOM = false;
};

dictionary TextDecodeOptions {
  boolean stream = false;
};

TextDecoder includes TextDecoderCommon;
```



## TextEncoderCommon

```webidl
interface mixin TextEncoderCommon {
  readonly attribute DOMString encoding;
};
```



## TextEncoder

```webidl
[Exposed=(Window,Worker)]
interface TextEncoder {
  constructor();

  [NewObject] Uint8Array encode(optional USVString input = "");
  TextEncoderEncodeIntoResult encodeInto(USVString source, [AllowShared] Uint8Array destination);
};

dictionary TextEncoderEncodeIntoResult {
  unsigned long long read;
  unsigned long long written;
};

TextEncoder includes TextEncoderCommon;
```



## TextDecoderStream

```webidl
[Exposed=(Window,Worker)]
interface TextDecoderStream {
  constructor(optional DOMString label = "utf-8", optional TextDecoderOptions options = {});
};
TextDecoderStream includes TextDecoderCommon;
TextDecoderStream includes GenericTransformStream;

```



## TextEncoderStream

```webidl
[Exposed=(Window,Worker)]
interface TextEncoderStream {
  constructor();
};

TextEncoderStream includes TextEncoderCommon;
TextEncoderStream includes GenericTransformStream;
```


[top](#)
