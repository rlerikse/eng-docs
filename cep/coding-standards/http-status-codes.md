# HTTP Status Codes

## 1xx - Informational
- `100 CONTINUE`

## 2xx - Success
- `200 OK` - Standard response for a successful HTTP request.
- `201 CREATED` - Indicates success, typically following a POST REST request.
- `202 ACCEPTED`
- `204 NO CONTENT` - Often used in DELETE requests to indicate success without returning content.
- `206 PARTIAL CONTENT`
- `207 MULTI STATUS`

:::info
In REST, DELETE is always considered idempotent, meaning it should return a 2xx status code regardless of the existence of the target resource, provided no other errors occur.
:::
## 3xx - Redirection
- `301 MOVED PERMANENTLY`
- `302 FOUND`

## 4xx - Client Error
- `400 BAD REQUEST` - The request contains an error and was not processed.
- `401 UNAUTHORIZED` - Authentication required but either not provided or credentials are invalid.
- `403 FORBIDDEN` - Server recognizes the credentials, but they don't match the access requirements.
- `404 NOT FOUND` - The requested resource is not available or server does not want to disclose its existence.
- `409 CONFLICT`
- `410 GONE`
- `429 TOO MANY REQUESTS`

### Distinguishing Between 401, 403, and 404

- `401 UNAUTHORIZED` Return only when credentials are invalid (e.g., bad token, password).
- `403 FORBIDDEN` Used when the operation is restricted beyond the access level of the credentials.
- `404 NOT FOUND` Preferably used for GET, PUT, and DELETE requests where the specified resource in path parameters is not accessible or does not exist.

  It is a good practice to return 404 in scenarios where revealing the existence of the resource could lead to security issues, such as key scanning.

## 5xx - Server Error
- `500 INTERNAL SERVER ERROR` - Occurs when an internal error happens while processing the request.
- `501 NOT IMPLEMENTED`
- `502 BAD GATEWAY` - Indicates a processing error, possibly at the API Gateway level (e.g., APIGEE).
- `503 SERVICE UNAVAILABLE` - Suggests that the request might succeed if tried again later.

### Resources

#### Status Code Lists:
- **Official W3C Source**
- **HTTP Statuses Website**
- **Wikipedia List**
- **The original HTTP Status Dogs**
- **HTTP Cats**

### Examples

- **Return 401:** When no token, a bad token, invalid username/password, or invalid certificate is provided.
- **Return 403:** When the operation itself is restricted, regardless of the path variables.
- **Return 404:** When the credentials are valid but access to the specific resource in the path is restricted.
