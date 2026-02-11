const CACHE = "dospad-cache-v1";
const ASSETS = [
  "./",
  "./index.html",
  "./manifest.webmanifest"
  // Si agregas iconos:
  // "./icon-192.png",
  // "./icon-512.png"
];

self.addEventListener("install", (event) => {
  event.waitUntil(
    caches.open(CACHE).then((cache) => cache.addAll(ASSETS))
  );
  self.skipWaiting();
});

self.addEventListener("activate", (event) => {
  event.waitUntil(
    caches.keys().then(keys =>
      Promise.all(keys.map(k => (k === CACHE ? null : caches.delete(k))))
    )
  );
  self.clients.claim();
});

self.addEventListener("fetch", (event) => {
  event.respondWith(
    caches.match(event.request).then((cached) => {
      return cached || fetch(event.request).then((resp) => {
        // Cache-as-you-go for same-origin GET
        try{
          const url = new URL(event.request.url);
          if(url.origin === location.origin && event.request.method === "GET"){
            const copy = resp.clone();
            caches.open(CACHE).then(c => c.put(event.request, copy));
          }
        } catch {}
        return resp;
      }).catch(() => cached);
    })
  );
});
