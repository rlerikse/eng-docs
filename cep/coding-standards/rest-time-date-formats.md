# REST Date/Time Formats

## Summary
It is recommended to use ISO8601 for all REST endpoints for consistency and standardization.

## OpenApi Usage
For date specifications in OpenApi:

```yaml
properties: 
  datetime:
    type: string
    format: date-time
```

Adhering to the standard is crucial to ensure uniform user experiences and simplify API parsing.

## Format

Format follows the ISO8601 standard:
```java
YYYY-MM-DDTHH:MM:SS[.NNN]Z
```