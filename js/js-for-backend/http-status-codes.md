# HTTP Status Codes

- HTTP status codes are three-digit numbers that **indicate the result** of an HTTP request.
- They are grouped into five classes

## 🔵 1xx — Informational

> _Request received, continuing process._

- **100 Continue** – Server received the request headers, client should continue with the request body.
- **101 Switching Protocols** – Client requested a protocol switch (like HTTP to WebSocket); server agrees.
- **102 Processing** _(WebDAV)_ – Server has accepted the request but hasn’t completed it yet.

---

## 🟢 2xx — Success

> _The request was successfully received, understood, and accepted._

- **200 OK** – Standard success for GET, PUT, DELETE, or POST.
- **201 Created** – Resource created successfully (e.g., after POST).
- **202 Accepted** – Request accepted but not yet processed.
- **204 No Content** – Request successful, but no content to return (e.g., after a DELETE or PUT).

---

## 🟡 3xx — Redirection

> _Further action must be taken to complete the request._

- **301 Moved Permanently** – Resource moved to a new URL; use the new URL in the future.
- **302 Found** – Temporary redirect; URL is different, but should not be cached.
- **303 See Other** – Redirect using GET, even if the original request was POST.
- **304 Not Modified** – Resource hasn't changed; client can use cached version.
- **307 Temporary Redirect** – Like 302, but keeps the request method (e.g., POST stays POST).
- **308 Permanent Redirect** – Like 301, but keeps the method (e.g., POST stays POST).

---

## 🔴 4xx — Client Errors

> _The request contains bad syntax or cannot be fulfilled._

- **400 Bad Request** – Malformed syntax or invalid parameters.
- **401 Unauthorized** – Authentication required or failed.
- **403 Forbidden** – Authenticated but not allowed to access the resource.
- **404 Not Found** – Resource not found on the server.
- **405 Method Not Allowed** – HTTP method (e.g., PUT, DELETE) not allowed on this resource.
- **409 Conflict** – Request conflicts with the current state (e.g., duplicate entry).
- **410 Gone** – Resource was intentionally removed and is no longer available.
- **415 Unsupported Media Type** – Server doesn’t support the media type in the request.
- **429 Too Many Requests** – Client sent too many requests in a given time (rate limiting).

---

## 🔴 5xx — Server Errors

> _The server failed to fulfill a valid request._

- **500 Internal Server Error** – General server error (unexpected condition).
- **501 Not Implemented** – Server doesn’t support the requested functionality.
- **502 Bad Gateway** – Server acting as a proxy got an invalid response from upstream.
- **503 Service Unavailable** – Server is down or overloaded (try again later).
- **504 Gateway Timeout** – Upstream server failed to respond in time.
- **505 HTTP Version Not Supported** – Server doesn’t support the HTTP version used in the request.

---

If you're building an API or web app, you usually work most with:

- **200, 201, 204**
- **400, 401, 403, 404, 409**
- **500, 502, 503**
