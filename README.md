# RESTInfo

RESTful APIs are application programming interfaces that adhere to architectural style of REST architectural pattern.

Constraints of REST Architecture
-----
The constraints, which must be followed to call an architecture as "REST Architecture" are as follows - 

### 1.) Client Server Architecture
This is 'default' architectural style for ANY web application, which essentially separates user interfaces from data persistence concerns.

### 2.) Stateless
Now this is key constraint understanding REST.
This essentially means, Server does NOT care about STATE of the client, and vice versa!
"Each request from client to server must contain all of the information necessary to understand the request, and cannot take advantage of any stored context on the server. Session state is therefore kept entirely on the client."

### 3.) Uniform Interface
It means, creating a uniform interface between client and server, for the interactions between them, and
#### Decoupling implementations from the interfaces-
means, implementation of the business logic should not depend upon it's interface.
(concrete example: your routes in a web app must not change when you change logic of how the controller (or the business logic) is implemented)

Typically, HTTP is used to implement a uniform interface (using HTTP methods), as HTTP is a stateless protocol.
But that does not mean one must use HTTP to implement REST, any stateless protocol can work, for that matter.

### 4.) Cache
Messages are cacheable by the server, client, or any proxy in between, or when not appropriate, mark themselves as not cacheable.

Uniform Interface This constrain is typically broken down into 4 separate sub-constraints:
---
### 1.) Identification of resources - 
You use the URI (IRI) standard to identify a resource. In this case a resource is a web document.

### 2.) Manipulation of resources through these representations - 
You use the HTTP standard to describe communication. So for example GET means that you want to retrieve data about the URI identified resource. You can describe an operation with a HTTP method and an URI.

### 3.) Self-descriptive messages - 
You use standard MIME types and (standard) RDF vocabs to make messages self-descriptive. So the client can find the data by checking the semantics, and it don't have to know the application specific data structure the service uses.
 
### 4.) Hypermedia as the engine of application state (A.K.A. HATEOAS) - 
You use hyperlinks and possibly URI templates to decouple the client from the application specific URI structure. You can annotate these hyperlinks with semantics e.g. IANA link relations, so the client will understand what they mean.
A hypermedia-driven site provides information to navigate the site's REST interfaces dynamically by including hypermedia links with the responses

Richardson Maturity Model
-----
This is a simple way of evaluating how RESTful a web service is. It's not perfect, and it assumes most of the constraints simply because they are guaranteed by the web architecture, but it's a good indicator. The model has 3 levels (and 0 – not really RESTful in any meaningful way).
### 1.)Resources – 
rather than using RPC on a single endpoint, data is broken out into separate resources, at separate locations. Communication is not method names and arguments, but instead the resources being manipulated.

### 2.) HTTP Verbs – 
rather than using HTTP POST for everything (as was the standard for SOAP APIs over HTTP for a while), we use GET, POST, PUT and DELETE as appropriate. GET is idempotent, POST creates a new resource in a collection, PUT updates a resource, and DELETE deletes it.

Also, this means usage of right HTTP response codes, for example.


Informational messages - 1XX


Success response - 2XX


Redirection responses - 3XX


Client error responses - 4XX


Server error responses - 5XX

### 3.) Hypermedia – 
resources contain links to related resources and collections, and also links to perform actions on the resources themselves. APIs are now self-documenting and discoverable.

eg, Twitter's REST API was one of the first major APIs to make REST 'trendy', at least in terms of popularity and widespread use. However on closer inspection it's not particularly RESTful.
-----
1.) Endpoints are resources, so the API passes level 1.

2.) HTTP verbs are used, although whether their usage is good practice or not is up for debate. For example, to delete a tweet, a POST request must be issued to /statuses/destroy/:id, therefore encoding the action in the URI rather than the verb. Perhaps a better way would be to issue a DELETE to /statuses/:id. The API arguably fails level 2.

3.) There are no links, and no self-documentation in responses, so the API fails level 3 entirely.

Five clue to determine api is REST or not
----
<a href="https://lornajane.net/posts/2013/five-clues-that-your-api-isnt-restful" target="_blank"> click here </a>

Caching REST API
-----
<a href="http://www.kennethlange.com/posts/Boost-Your-REST-API-with-HTTP-Caching.html" target="_blank">click here </a>


HTTP Catche
------
<a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching">click here</a>

HTTP  2.0
-------
<a href="https://developers.google.com/web/fundamentals/performance/http2/">click here</a>

HTTPS
------
<a hred="https://developers.google.com/web/fundamentals/security/encrypt-in-transit/why-https">click here</a>
