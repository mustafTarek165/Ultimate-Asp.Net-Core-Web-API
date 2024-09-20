- Rate Limiting allows us to protect our API against too many requests that can deteriorate our API’s performance. API is going to reject requests that exceed the limit.
- For the disallowed requests, we use a 429 status code; that stands for too many requests. This header may include the Retry-After response header and should explain details in the response body.
- This built-in middleware provides different rate limiting algorithms to control the flow of requests: 
   1- Concurrency limit – limits how many concurrent requests can access the resource 
   2- Fixed window limit – limits certain number of requests in a particular amount of time. It is the same thing we've been using in our previous book versions 
  3- Sliding window limit - it is a similar algorithm to the fixed window algorithm just in this case, we have additional segments. For example, we can configure the middleware to allow 120 requests per minute with the 2 requests every second 
  4- Token bucket limit - uses tokens while working with incoming requests. For each request a token is added and saved. If we are 279 out of tokens the request is blocked (this is pretty simplified explanation, but it hits the point)
- A built-in rate limiting mechanism enables us to queue the requests instead of rejecting them.
- 