# fem proxy
i rlly dont care wht u do with ts, just dont try and skid it i stg 😭

# Configuration
Configure Ultraviolet for both client-hooking & service worker in `uv.config.js`
```javascript
self.__uv$config = {
    bare: '/bare/',
    prefix: '/service/',
    encodeUrl: Ultraviolet.codec.xor.encode,
    decodeUrl: Ultraviolet.codec.xor.decode,
    handler: '/uv.handler.js',
    bundle: '/uv.bundle.js',
    config: '/uv.config.js',
};
```


# Example Usage
```javascript
importScripts('/PATHTOSCRIPTS/uv.sw.js');

const sw = new UVServiceWorker();

self.addEventListener('fetch', event =>
    event.respondWith(
        sw.fetch(event)
    )
);
```
