# APIs

# What does REST stand for?
__* REST is an architectural style for building distributed systems based on hypermedia. REST is independent of any underlying protocol and is not necessarily tied to HTTP. *__
# REST APIs are designed around a resources.

# What is an identifer of a resource? Give an example.
__* which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:https://adventure-works.com/orders/1 *__
# What are the most common HTTP verbs?
__* GET, POST, PUT, PATCH, and DELETE. *__
# What should the URIs be based on?
__* Adopt a consistent naming convention in URIs. In general, it helps to use plural nouns for URIs that reference collections. It's a good practice to organize URIs for collections and items into a hierarchy. *__
# Give an example of a good URI.
__* https://adventure-works.com/orders *__
# What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
__* web APIs that expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires. and we need to try to avoid it so it's bad *__
# What status code does a successful GET request return?
__* typically returns HTTP status code 200 (OK) *__
# What status code does an unsuccessful GET request return?
__* the method should return 404 (Not Found). *__
# What status code does a successful POST request return?
__*  it returns HTTP status code 201 (Created). *__
# What status code does a successful DELETE request return?
__* it returns HTTP status code 201 (Created) *__