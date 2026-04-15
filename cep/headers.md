# Headers

In order to ensure that the various components of the Platform+ Tech function in a unified way, they must adhere to receiving and passing along certain common HTTP header data that act as the “glue” in this architectural unity.

## Required and Optional Headers

`X-User-Id` (optional): ID of the user, if any, that originated the request or that the request represents.


`X-Correlation-Id` (optional): A surrogate ID that if provided by an external system, the Platform+ Tech will propagate through all calls branching off the originating call. This allows one to “correlate” things such as transactions/call traces between systems.

## Header Expectations

- All header data must always be extracted at the very beginning of any controller, serverless handler, etc.


- If a request arrives missing any required header data (e.g. `X-Sample-Id`), the call must be rejected stating that required context data was not provided.


- Any HTTP calls to other services must propagate any and all header data received (required and optional) downstream using the same header tags and with no modification of that data (e.g. no changing of IDs, specially `X-Correlation-Id`).


- Optional data not received should not suddenly have header data appear unless that component has a sensible reason to introduce it. For example, a mid-stream component should not suddenly populate the `X-Correlation-Id`.
