# Introduction to REST API

###  What is REST?
<br>
REST stands for REpresentational State Transfer. It is an architecture for designing loosely coupled applications over HTTP. REST is often used in the development of web services.

A REST API is an application program interface (API) that uses HTTP requests to GET, PUT, POST, and DELETE resources. When a RESTful API is called, the server transfers to the client a representation of the state of the requested resource.

For example, when a developer calls the PowerProtect DD REST API to retrieve a specific user (the resource), the API responds with the state of that user, including name, unique ID, role of the user, status, and more.

The representation of the state can be in XML or JSON format.


### Architecture constraints
<br>
RESTful APIs adhere to these architectural constraints:

1. **Client–server** – Separating user interface from the data storage improves the portability of the user interface across multiple platforms and improves scalability by simplifying the server components.
2. **Stateless** – Each request from client to server must contain the necessary information to understand the request and cannot use any stored context on the server. Session state is kept on the client.
3. **Cacheable** – Cache constraints require that the data in a response to a request is labeled as cacheable or non-cacheable. If a response is cacheable, a client cache is granted the right to reuse that response data for subsequent requests.
4. **Uniform interface** – To obtain a uniform interface, multiple constraints are needed to guide the behavior of components. REST is defined by four interface constraints: identification of resources, manipulation of resources through representations, self-descriptive messages, and hypermedia as the engine of application state.
5. **Layered system** – The layered system style enables an architecture to have layers of hierarchy. It constrains each component within its own layer.
6. **Code on demand (optional)** – REST allows client functions to be extended by downloading and running code in the form of applets or scripts. This simplication reduces the number of features that must be implemented ahead of time.

### Resource
<br>
The key abstraction of information in REST is a resource. Any information that can be named can be a resource: a document or image, temporary service, collection of other resources, nonvirtual object, and so on. REST uses a resource identifier to identify the resource involved in an interaction between components.

The state of a resource at any given timestamp is known as resource representation. A representation consists of data, including metadata that describes the data and hypermedia links that can assist the clients in transition to the next desired state.

The data format of a representation is known as a media type. The media type identifies a specification that defines how a representation is processed. A RESTful API looks like hypertext. Every addressable unit of information includes an address.

### Resource methods
<br>
Another important aspect of REST are the resource methods to perform the desired transitions. The common methods are HTTP methods, or verbs: GET, POST, PUT, and DELETE.

### Making requests
REST requires that a client make a request to the server to retrieve or modify data on the server. 
A request generally consists of:

- An HTTP verb,which defines what kind of operation to perform
- A header, which allows the client to pass along information about the request
- A path to a resource
- An optional message body that contains data

### HTTP verbs
There are four HTTP verbs that are used in requests to interact with resources:

- GET — Retrieves a specific resource (by ID) or a collection of resources
- POST — Creates a new resource
- PUT — Updates a specific resource (by ID)
- DELETE — Removes a specific resource by ID

### Headers and accept parameters
In the header of the request, the client sends the type of content that it is able to receive from the server. This information is called the Accept field. It ensures that the server does not send data that cannot be understood or processed by the client.

For example,

    GET

### Response codes
Responses from the server contain status codes to alert the client about the success of the operation. As a developer, you do not need to know every status code (there are many of them), but you should know the most common ones and how they are used:


Status Code |  Name| Meaning
---------|----------|---------
 200| OK | The standard response for successful HTTP requests. Usually returned by a GET or PUT method.
 201| CREATED | The standard response for an HTTP request that results in a resource being successfully created. Usually returned by a POST method.
 301 | MOVED PERMANENTLY | The standard response for an HTTP request that the requested resource has been removed or obsoleted. Use the new URI indicated in the response if applicable.
 400 | BAD REQUEST | The request cannot be processed because of bad request syntax, excessive size, or another client error.
 401 | UNAUTHROZIED | The client is not authenticated or authorized to perform the request.
 403 | FORBIDDEN  | The client does not have permission to access this resource.
 404 | NOT FOUND  | The resource could not be found at this time. It is possible it was deleted or does not exist yet.
 411 | LENGTH REQUIRED | A request body is expected, but the body is empty.
 413 | REQUEST ENTITY TOO LARGE | The request size is greater than 64k (65536 bytes), which exceeds the buffer length for socket packets.
 414 | REQUEST URI TOO LONG | The specified URI is longger than 2000 bytes. The 2000 byte maximum URI can work for most client and server combinations.
 415 | UNSUPPORTED MEDIA TYPE | The media type in the request is not application/xml or application/json.
 500 | INTERNAL SERVER ERROR | The generic answer for an unexpected failure if no more specific information is available.
 501 | NOT IMPLEMENTED | The specified service is not implemented.

### Example of request and response