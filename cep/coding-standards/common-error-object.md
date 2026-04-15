# Common Error Object

## Java

### ErrorResponse Class

This Java class represents the error response structure.

```java
@Build
@Data
@NoArgsConstructor
@AllArgsConstructor
public class ErrorResponse {
    private OffsetDateTime timestamp;
    private String errorCode;
    private String errorMessage;
    private String requestId;
}
```

## YAML

### ErrorResponse Schema

This YAML schema defines the ErrorResponse object for API specifications.

```yaml
ErrorResponse:
  title: "Error Response Object"
  description: "An error response indicates an error occurred."
  properties:
    errorMessage:
      type: string
    errorCode:
      type: string
    timeStamp:
      type: string
      format: date-time
    requestId:
      type: string
```

## Suggestions for Future

### ErrorResponseError Class

A proposed Java class to handle a list of error responses.

```java
@Build
@Data
@NoArgsConstructor
@AllArgsConstructor
public class ErrorResponseError {
    private OffsetDateTime timestamp;
    List<ErrorResponseError> errors;
}
```

````markdown
# Common Error Object

## Java

### ErrorResponse Class

This Java class represents the error response structure.

```java
@Build
@Data
@NoArgsConstructor
@AllArgsConstructor
public class ErrorResponse {
    private OffsetDateTime timestamp;
    private String errorCode;
    private String errorMessage;
    private String requestId;
}
```
````

## YAML

### ErrorResponse Schema

This YAML schema defines the ErrorResponse object for API specifications.

```yaml
ErrorResponse:
  title: "Error Response Object"
  description: "An error response indicates an error occurred."
  properties:
    errorMessage:
      type: string
    errorCode:
      type: string
    timeStamp:
      type: string
      format: date-time
    requestId:
      type: string
```

## Suggestions for Future

### ErrorResponseError Class

A proposed Java class to handle a list of error responses.

```java
@Build
@Data
@NoArgsConstructor
@AllArgsConstructor
public class ErrorResponseError {
    private OffsetDateTime timestamp;
    List<ErrorResponseError> errors;
}
```

### ErrorResponseError Subclass

A Java class to represent individual errors within a list.

```java
@Build
@Data
@NoArgsConstructor
@AllArgsConstructor
public class ErrorResponseError {
    private String errorCode;
    private String errorMessage;
}
```

## Another Option for Common Error Object Model

### JSON Structure

An alternative JSON structure for error responses.

```json
{
  "timestamp": "",
  "status": "400",
  "Errors": [
    {
      "type": "vehicle/rides etc",
      "field": "vehicle[0].location",
      "message": "user readable text",
      "rejectedValue": "actual location",
      "errorCode": 0
    }
  ],
  "path": "/"
}
```

## Error Code

### Description

The `errorCode` field should be a computer-readable/human understandable code. The format should be all caps with hyphens.

### Purpose

The intent is to provide the type of error in a computer understandable format to remove the need to parse actual error messages.

### Suggested Example Codes

- `BAD-REQUEST`
- `NOT-FOUND`
- `ERROR`
- `UNCAUGHT-EXCEPTION`
- `ARGUMENT-OUT-OF-RANGE`
- `REQUIRED-ARGUMENT-MISSING`
- `REQUIRED-FIELD-MISSING`
