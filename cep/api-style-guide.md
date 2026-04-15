# API Style Guide

APIs are designed in accordance with the API Style Guide.

## High-Level Rules

- All Organization APIs must follow the [REST architectural](https://restfulapi.net/rest-architectural-constraints) style as much as possible.


- A RESTful API MUST have one and exactly one entry point with the following [structure](https://github.company.com/NSILVER4/APIStyleGuide/wiki/URL-Structure):
`https://{domain name}:port/{version}/{api identification}/{endpoint}`


- All [proper security controls](https://github.company.com/NSILVER4/APIStyleGuide/wiki/Security) must be used when creating APIs.


- Standard [HTTP headers](https://github.company.com/NSILVER4/APIStyleGuide/wiki/HTTP-Headers), defined or referenced from the [HTTP/1.1](https://tools.ietf.org/html/rfc2616) specification must be used over custom headers.


- Always use accurate [HTTP status codes](https://github.company.com/NSILVER4/APIStyleGuide/wiki/HTTP-Status-Codes).


- Any operation created to support the API must match [HTTP method semantics](https://github.company.com/NSILVER4/APIStyleGuide/wiki/HTTP-Methods).


- All [Swagger documentation](https://github.company.com/NSILVER4/APIStyleGuide/wiki/API-Documentation) must be clear, concise, and complete.