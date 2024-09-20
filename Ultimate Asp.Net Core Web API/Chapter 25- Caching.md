- The main goal of caching is to eliminate the need to send requests towards the API in many cases and also to send full responses in other cases.
- To reduce the number of sent requests, caching uses the expiration mechanism, which helps reduce network round trips. Furthermore, to eliminate the need to send full responses, the cache uses the validation mechanism, which reduces network bandwidth.
- There are three types of caches: Client Cache, Gateway Cache, and Proxy Cache.
- The client cache lives on the client (browser); thus, it is a private cache. It is private because it is related to a single client. So every client consuming our API has a private cache.
- The gateway cache lives on the server and is a shared cache. This cache is shared because the resources it caches are shared over different clients.
- The proxy cache is also a shared cache, but it doesn’t live on the server nor the client side. It lives on the network.
- With the private cache, if five clients request the same response for the first time, every response will be served from the API and not from the cache. But if they request the same response again, that response should come from the cache (if it’s not expired). This is not the case with the shared cache. The response from the first client is going to be cached, and then the other four clients will receive the cached response if they request it.
- Response Cache attribute gives us response header Cache Control: max-age=duration like [ResponseCache(Duration = 60)] but it is just adding a header and we need cache store.
- We use built in cache middleware in .Net as a cache store after caching then requesting again a header called age is added which refers to the time since the response was added to cache store so if it is age:9 means that this response was cached before 9 seconds and of course this response from cache store.
- we can cache one action or the whole actions in controller.
- Output caching is a mechanism for storing the output of a client's request and serving the stored result on future requests. This significantly improves an application's responsiveness by providing a faster response to client requests and saving on repeated processing of the same output.
- in output caching the caching decision is solely made by the server application.
- this comes with some advanced capabilities. For example, we can configure resource locking - a true solution to prevent cache stampedes and thundering herds. Other features include: 
     - Support for custom caching stores like Redis 
     - Caching of cookies and headers
     -  Caching authenticated content 
     - Tagging of cache contents and invalidating as a group 
     - Purging cache 
     - Delayed caching 
     - Partial caching or donut caching 
 - By default, output caching follows these rules: 
    - Only HTTP 200 responses are cached. 
    - Only HTTP GET or HEAD requests are cached. 
    - Responses that set cookies aren't cached. 
    - Responses to authenticated requests aren't cached.
- [OutputCache(Duration = 60)] and adding Output Chache middleware ,The OutputCache attribute contains the properties that ResponseCache has, so we can use the Duration property this time as well.
- We don’t have the Cache-Control header anymore. That’s because the server doesn’t have to inform the client about the max-age directive of the response. But, if we send the same request before 60 seconds pass, we will see the Age header for sure.
- 