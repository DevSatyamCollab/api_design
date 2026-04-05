## Caching

- Caching involves storing copies of respone of http requests to speed up future requests.

- When API receives the same request multiple times, instead of processing each request separately, it can use a previously store response.

- thereby improving performance, efficiency and reduce network traffic

### How Caching work ?

- When a consumer request a resource, the request go through a cache or series of cahces (local cache, proxy cache, reverse proxy cache)

- If any of the cache along the request path has a fresh copy of the requested representaion, it uses a copy. If none of the caches can satisfy the request, then the request travel to server.

- By using HTTP headers, a server indicates whether a response can be cached and if so, by whom and for how long.

- Caches along the response path can take a copy of a response, but only if the caching metadata allows to do so.

### Caching in REST APIs

1. GET requests should be cachable by default – until a special condition arises. Usually, browsers treat all GET requests as cacheable.

2. POST requests are not cacheable by default but can be made cacheable if either an Expires header or a Cache-Control header with a directive, to explicitly allows caching, is added to the response.

3. Responses to PUT and DELETE requests are not cacheable at all.

### HTTP Headers to Control Caching Behavior

1. Expires
2. ETag
3. Last-Modified
4. Cache-Control
