HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:

Informational responses (100–199),
Successful responses (200–299),
Redirects (300–399),
Client errors (400–499),
and Server errors (500–599).
--------------------------------------------------

Information responses
---------------------------------------------------
100 Continue
	This interim response indicates that everything so far is OK and that the client should continue the request,
	or ignore the response if the request is already finished.
101 Switching Protocol
	This code is sent in response to an Upgrade request header from the client, and indicates the protocol the server 
	is switching to.
102 Processing (WebDAV)
	This code indicates that the server has received and is processing the request, but no response is available yet.
103 Early Hints
	This status code is primarily intended to be used with the Link header, letting the user agent start preloading 
	resources while the server prepares a response.
Successful responses
-------------------------------------------------------
200 OK
	The request has succeeded. The meaning of the success depends on the HTTP method:
	GET: The resource has been fetched and is transmitted in the message body.
	HEAD: The entity headers are in the message body.
	PUT or POST: The resource describing the result of the action is transmitted in the message body.
	TRACE: The message body contains the request message as received by the server.
201 Created
	The request has succeeded and a new resource has been created as a result. This is typically the
	response sent after POST requests, or some PUT requests.
202 Accepted
	The request has been received but not yet acted upon. It is noncommittal, since there is no way 
	in HTTP to later send an asynchronous response indicating the outcome of the request. It is intended 
	for cases where another process or server handles the request, or for batch processing.
203 Non-Authoritative Information
	This response code means the returned meta-information is not exactly the same as is available from 
	the origin server, but is collected from a local or a third-party copy. This is mostly used for mirrors 
	or backups of another resource. Except for that specific case, the "200 OK" response is preferred to this status.
204 No Content
	There is no content to send for this request, but the headers may be useful. The user-agent may update its cached 
	headers for this resource with the new ones.
205 Reset Content
	Tells the user-agent to reset the document which sent this request.
206 Partial Content
	This response code is used when the Range header is sent from the client to request only part of a resource.
	207 Multi-Status (WebDAV)
	Conveys information about multiple resources, for situations where multiple status codes might be appropriate.
208 Already Reported (WebDAV)
	Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings 
	to the same collection.
226 IM Used (HTTP Delta encoding)
	The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.
Redirection messages
--------------------------
300 Multiple Choice
	The request has more than one possible response. The user-agent or user should choose one of them. 
	(There is no standardized way of choosing one of the responses, but HTML links to the possibilities 
	are recommended so the user can pick.)
301 Moved Permanently
	The URL of the requested resource has been changed permanently. The new URL is given in the response.
302 Found
	This response code means that the URI of requested resource has been changed temporarily. Further changes 
	in the URI might be made in the future. Therefore, this same URI should be used by the client in future requests.
303 See Other
	The server sent this response to direct the client to get the requested resource at another URI with a GET request.
304 Not Modified
	This is used for caching purposes. It tells the client that the response has not been modified, so the client can continue 
	to use the same cached version of the response.
305 Use Proxy 
	Defined in a previous version of the HTTP specification to indicate that a requested response must be accessed by a proxy. 
	It has been deprecated due to security concerns regarding in-band configuration of a proxy.
306 unused
	This response code is no longer used; it is just reserved. It was used in a previous version of the HTTP/1.1 specification.
307 Temporary Redirect
	The server sends this response to direct the client to get the requested resource at another URI with same method that was 
	used in the prior request. This has the same semantics as the 302 Found HTTP response code, with the exception that the user 
	agent must not change the HTTP method used: If a POST was used in the first request, a POST must be used in the second request.
308 Permanent Redirect
	This means that the resource is now permanently located at another URI, specified by the Location: HTTP Response header. 
	This has the same semantics as the 301 Moved Permanently HTTP response code, with the exception that the user agent must not 
	change the HTTP method used: If a POST was used in the first request, a POST must be used in the second request.
