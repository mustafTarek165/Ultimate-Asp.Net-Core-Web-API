- the [ApiController] attribute is applied to a controller class to enable the following opinionated, API-specific behaviors: 
    - Attribute routing requirement 
    - Automatic HTTP 400 responses 
    - Binding source parameter inference 
    - Multipart/form-data request inference 
    - Problem details for error status codes
 - options.SuppressModelStateInvalidFilter = true; for disabling this automatic Response and even if request is not valid it will reach the action controller and you are responsible for manually checking ModelState.IsValid.  
 - When you call `CreatedAtRoute`, several things happen:

1. **HTTP Status Code 201**: A **201 Created** status is returned, which indicates that the request has been fulfilled and resulted in a new resource being created.
2. **Location Header**: The response includes a **Location** header that provides the URI of the newly created resource, allowing the client to know where to access the resource.
3. **Response Body**: The method also returns the newly created resource (`companyToReturn`) in the body of the response, allowing the client to inspect the details of the created object.
**Why Use `CreatedAtRoute`?**

1. **RESTful Best Practices**: It adheres to REST principles by providing the URI of the newly created resource, allowing clients to access the resource directly.
2. **Convenience**: It simplifies the process of returning a `201 Created` response with the correct URI and the resource's data in a single method call.
3. **Client Awareness**: By including the `Location` header in the response, the client can easily navigate to the newly created resource without needing to know how the server generates URIs.
