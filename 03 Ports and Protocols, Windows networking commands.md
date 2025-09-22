
# HTTP Response Status Codes
HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:

1. Informational responses (100 – 199)
2. Successful responses (200 – 299)
3. Redirection messages (300 – 399)
4. Client error responses (400 – 499)
5. Server error responses (500 – 599)

---

## 1. Informational responses (100 – 199)

- 100 Continue → Server says: “I got the first part, send the rest.”
- 101 Switching Protocols → Server says: “Okay, I’m switching to the new protocol you asked for.”
- 102 Processing (Deprecated) → Server says: “I received your request, working on it… result will come later.”
- 103 Early Hints → Server says: “Full response coming soon, meanwhile start loading resources.”
## 2 . Successful responses (200 – 299)

- 200 OK → Request worked.
	- GET → Got the resource.
	- POST/PUT → Resource created/updated.
	- HEAD → Only headers sent.
	- TRACE → Echoes your request.
- 201 Created → Request worked, and a new resource was made (common with POST).
- 202 Accepted → Request received, but not finished yet (processing later).
- 203 Non-Authoritative Info → Data returned is from a copy/mirror, not the main server.
- 204 No Content → Success, but no content in response (empty body)
- 205 Reset Content → Success, but client should reset the form/document that sent it.
- 206 Partial Content → Sending only part of the resource (like resume a download).
- 207 Multi-Status (WebDAV) → Multiple status codes for different resources.
- 208 Already Reported (WebDAV) → Resource info already given, no need to repeat.
- 226 IM Used → Success, with some transformations applied to the resource

## 3 . Redirection messages (300 – 399)

- 300 Multiple Choices → Several possible responses, client must choose.
- 301 Moved Permanently → Resource moved to a new URL forever.
- 302 Found → Resource moved temporarily, try again later at new URL.
- 303 See Other → Go to a different URL using GET.
- 304 Not Modified → Resource not changed, use cached copy.
- 305 Use Proxy (Deprecated) → Resource must be accessed via proxy (not used anymore).
- 306 (Unused) → Reserved code, not used.
- 307 Temporary Redirect → Resource temporarily at new URL, but use same method (POST stays POST).
- 308 Permanent Redirect → Resource permanently at new URL, and keep the same method.

## 4 . Client error responses (400 – 499)

- 400 Bad Request → Invalid request (syntax/format issue).
- 401 Unauthorized → Need to log in (actually means Unauthenticated).
- 402 Payment Required → Rare, meant for payments (almost never used).
- 403 Forbidden → You’re not allowed, even if logged in.
- 404 Not Found → Resource doesn’t exist (most famous error).
- 405 Method Not Allowed → Method not supported (e.g., DELETE not allowed).
- 406 Not Acceptable → Server can’t give data in format client asked.
- 407 Proxy Authentication Required → Need to authenticate with proxy.
- 408 Request Timeout → Took too long, server closed connection.
- 409 Conflict → Request conflicts with server state (e.g., editing same data).
- 410 Gone → Resource deleted permanently, no forwarding link.
- 411 Length Required → Server needs Content-Length header, but it’s missing.
- 412 Precondition Failed → Request conditions not met (e.g., version mismatch).
- 413 Content Too Large → Request body too big.
- 414 URI Too Long → URL too long for server.
- 415 Unsupported Media Type → File/data type not supported.
- 416 Range Not Satisfiable → Requested range not valid (e.g., asking byte 1000 of a 500-byte file).
- 417 Expectation Failed → Server couldn’t meet the Expect header request.
- 418 I’m a teapot (Joke) → Server refuses to brew coffee with a teapot (April Fools’).
- 421 Misdirected Request → Request sent to wrong server.
- 422 Unprocessable Content → Request looks fine, but server can’t process due to logic/semantic errors.
- 423 Locked (WebDAV) → Resource is locked.
- 424 Failed Dependency (WebDAV) → Request failed because a previous request failed.
- 425 Too Early (Experimental) → Server won’t process now because request might be replayed.
- 426 Upgrade Required → Must switch to another protocol (e.g., HTTPS).
- 428 Precondition Required → Must send request with conditions to avoid conflicts.
- 429 Too Many Requests → You’re sending too many requests (rate limit).
- 431 Request Header Too Large → Headers too big.

## 5. Server error responses (500 – 599)

- 500 Internal Server Error → Generic error, server can’t handle request.
- 501 Not Implemented → Method not supported (server doesn’t know how to handle).
- 502 Bad Gateway → Server acting as a gateway got a bad response.
- 503 Service Unavailable → Server is down/overloaded/maintenance.
- 504 Gateway Timeout → Gateway didn’t get a response in time.
- 505 HTTP Version Not Supported → HTTP version not supported by server.
- 506 Variant Also Negotiates → Server config error (loop in negotiation).
- 507 Insufficient Storage (WebDAV) → Server can’t store the data.
- 508 Loop Detected (WebDAV) → Infinite loop detected in request.
- 510 Not Extended → Request needs extra extensions not supported.
- 511 Network Authentication Required → Must authenticate to access network.

