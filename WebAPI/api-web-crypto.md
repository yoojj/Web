# WebCrypto API

https://www.w3.org/TR/WebCryptoAPI/


**api**
- GlobalCrypto
- Crypto
- CryptoKey
- SubtleCrypto



## GlobalCrypto

```webidl
[NoInterfaceObject,Exposed=(Window,Worker)]
interface GlobalCrypto {
  readonly attribute Crypto crypto;
};

Window implements GlobalCrypto;
WorkerGlobalScope implements GlobalCrypto;        
```



## Crypto

```webidl
[Exposed=(Window,Worker)]
interface Crypto {
  [SecureContext] readonly attribute SubtleCrypto subtle;
  ArrayBufferView getRandomValues(ArrayBufferView array);
};
```



## CryptoKey

```webidl
[SecureContext,Exposed=(Window,Worker)]
interface CryptoKey {
  readonly attribute KeyType type;
  readonly attribute boolean extractable;
  readonly attribute object algorithm;
  readonly attribute object usages;
};

enum KeyType { "public", "private", "secret" };

enum KeyUsage { "encrypt", "decrypt", "sign", "verify", "deriveKey",
  "deriveBits", "wrapKey", "unwrapKey" };
```



## SubtleCrypto

```webidl
[SecureContext,Exposed=(Window,Worker)]
interface SubtleCrypto {
  Promise<any> encrypt(AlgorithmIdentifier algorithm,
                       CryptoKey key, BufferSource data);

  Promise<any> decrypt(AlgorithmIdentifier algorithm,
                       CryptoKey key, BufferSource data);

  Promise<any> sign(AlgorithmIdentifier algorithm,
                    CryptoKey key, BufferSource data);

  Promise<any> verify(AlgorithmIdentifier algorithm, CryptoKey key,
                      BufferSource signature, BufferSource data);

  Promise<any> digest(AlgorithmIdentifier algorithm, BufferSource data);

  Promise<any> generateKey(AlgorithmIdentifier algorithm,
                          boolean extractable, sequence<KeyUsage> keyUsages);

  Promise<any> deriveKey(AlgorithmIdentifier algorithm, CryptoKey baseKey,
                         AlgorithmIdentifier derivedKeyType,
                         boolean extractable, sequence<KeyUsage> keyUsages);

  Promise<ArrayBuffer> deriveBits(AlgorithmIdentifier algorithm,
                          CryptoKey baseKey, unsigned long length);

  Promise<CryptoKey> importKey(KeyFormat format, (BufferSource or JsonWebKey) keyData,
                         AlgorithmIdentifier algorithm, boolean extractable,
                         sequence<KeyUsage> keyUsages);

  Promise<any> exportKey(KeyFormat format, CryptoKey key);

  Promise<any> wrapKey(KeyFormat format, CryptoKey key,
                       CryptoKey wrappingKey, AlgorithmIdentifier wrapAlgorithm);

  Promise<CryptoKey> unwrapKey(KeyFormat format, BufferSource wrappedKey,
                         CryptoKey unwrappingKey, AlgorithmIdentifier unwrapAlgorithm,
                         AlgorithmIdentifier unwrappedKeyAlgorithm,
                         boolean extractable, sequence<KeyUsage> keyUsages);
};

typedef (object or DOMString) AlgorithmIdentifier;

enum KeyFormat { "raw", "spki", "pkcs8", "jwk" };
```



[top](#)
