HTTP Status CODES AND THEIR DESCRIPTION<br/>
------------------------------
HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:<br/>
----------------------------------
Informational responses (100–199),<br/><br/>
Successful responses (200–299),<br/><br/>
Redirects (300–399),<br/><br/>
Client errors (400–499),<br/><br/>
and Server errors (500–599).<br/><br/>

--------------------------------------------------

Information responses
---------------------------------------------------
<br/><br/>100 Continue<br/>
	This interim response indicates that everything so far is OK and that the client should continue the request,<br/>
	or ignore the response if the request is already finished.<br/>
<br/><br/>101 Switching Protocol<br/>
	This code is sent in response to an Upgrade request header from the client, and indicates the protocol the server<br/> 
	is switching to.<br/>
<br/><br/>102 Processing (WebDAV)<br/>
	This code indicates that the server has received and is processing the request, but no response is available yet.<br/>
<br/><br/>103 Early Hints<br/>
	This status code is primarily intended to be used with the Link header, letting the user agent start preloading<br/> 
	resources while the server prepares a response.<br/><br/>
#Successful responses<br/>
-------------------------------------------------------
<br/><br/>200 OK<br/>
	The request has succeeded. The meaning of the success depends on the HTTP method:
	GET: The resource has been fetched and is transmitted in the message body.
	HEAD: The entity headers are in the message body.
	PUT or POST: The resource describing the result of the action is transmitted in the message body.
	TRACE: The message body contains the request message as received by the server.<br/>
<br/>201 Created<br/>
	The request has succeeded and a new resource has been created as a result. This is typically the
	response sent after POST requests, or some PUT requests.<br/>
<br/><br/>202 Accepted<br/>
	The request has been received but not yet acted upon. It is noncommittal, since there is no way 
	in HTTP to later send an asynchronous response indicating the outcome of the request. It is intended 
	for cases where another process or server handles the request, or for batch processing.<br/>
<br/><br/>203 Non-Authoritative Information<br/>
	This response code means the returned meta-information is not exactly the same as is available from 
	the origin server, but is collected from a local or a third-party copy. This is mostly used for mirrors 
	or backups of another resource. Except for that specific case, the "200 OK" response is preferred to this status.<br/>
<br/>204 No Content<br/>
	There is no content to send for this request, but the headers may be useful. The user-agent may update its cached 
	headers for this resource with the new ones.<br/>
<br/>205 Reset Content<br/>
	Tells the user-agent to reset the document which sent this request.<br/>
<br/>206 Partial Content<br/>
	This response code is used when the Range header is sent from the client to request only part of a resource.<br/>
<br/>207 Multi-Status (WebDAV)<br/>
	Conveys information about multiple resources, for situations where multiple status codes might be appropriate.<br/>
<br/>208 Already Reported (WebDAV)<br/>
	Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings 
	to the same collection.<br/>
<br/>226 IM Used (HTTP Delta encoding)<br/>
	The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.<br/>
Redirection messages
--------------------------
<br/><br/>300 Multiple Choice<br/>
	The request has more than one possible response. The user-agent or user should choose one of them. 
	(There is no standardized way of choosing one of the responses, but HTML links to the possibilities 
	are recommended so the user can pick.)
<br/><br/>301 Moved Permanently<br/>
	The URL of the requested resource has been changed permanently. The new URL is given in the response.
<br/><br/>302 Found<br/>
	This response code means that the URI of requested resource has been changed temporarily. Further changes 
	in the URI might be made in the future. Therefore, this same URI should be used by the client in future requests.
<br/><br/>303 See Other<br/>
	The server sent this response to direct the client to get the requested resource at another URI with a GET request.
<br/><br/>304 Not Modified<br/>
	This is used for caching purposes. It tells the client that the response has not been modified, so the client can continue 
	to use the same cached version of the response.
<br/><br/>305 Use Proxy <br/>
	Defined in a previous version of the HTTP specification to indicate that a requested response must be accessed by a proxy. 
	It has been deprecated due to security concerns regarding in-band configuration of a proxy.
<br/><br/>306 unused<br/>
	This response code is no longer used; it is just reserved. It was used in a previous version of the HTTP/1.1 specification.
<br/><br/>307 Temporary Redirect<br/>
	The server sends this response to direct the client to get the requested resource at another URI with same method that was 
	used in the prior request. This has the same semantics as the 302 Found HTTP response code, with the exception that the user 
	agent must not change the HTTP method used: If a POST was used in the first request, a POST must be used in the second request.
<br/><br/>308 Permanent Redirect<br/>
	This means that the resource is now permanently located at another URI, specified by the Location: HTTP Response header. 
	This has the same semantics as the 301 Moved Permanently HTTP response code, with the exception that the user agent must not 
	change the HTTP method used: If a POST was used in the first request, a POST must be used in the second request.
