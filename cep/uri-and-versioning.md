# URI and Versioning
## URI Naming
A RESTful URI is a semi-permanent commitment to customers of an API. Choosing a URI naming strategy should be considered a long-term decision. We should be careful with what is part of URI since URI is visible throughout all the request hops and hence, we should **avoid including any PII or SPII data into URI.**

## RESTful URI Naming General Rules

- All resource names/URIs will match [RFC specifications](https://www.rfc-editor.org/rfc/rfc3986) and use spinal-case as a multiword separator.

`nameplate-configuration` and not `nameplateconfiguration`, `nameplateConfiguration`, `NameplateConfiguration`, etc.

- Standard RESTful noun focus is required, with a preference for plurals for collections and identifiers under a collection for instances.

`/vehicles` references a collection while `/vehicles/1FDSW3AT0B0014719` references a vehicle instance.
  - Singular may be used if there is no natural plural form for a word.

- Verbs should not be used in base URIs.

- Pagination, filtering, sorting, etc. should be expressed via query parameters.

## Versioning

### API Versioning

- API versioning is required because it ensures stability and reliability.
- All Platform+ Tech components should be independently versioned and follow a common version naming and operational model.
- This is critical for a good end-user developer experience.

### Internal Versioning

- Internal versioning of each component must follow the semver model.
- Versioning should be of the style: `MAJORVERSION.MINORVERSION.PATCHVERSION`.

### URLs

- URLs should be a combination of scheme, API service name, API version number, and the RESTful URI for the resource(s) in question:

  - Pattern: `{scheme}:{DNS Record}/v{MAJORVERSION}/{Absolute URI}`
  - Example: `https://api.enterprise.com/v2/vehicles/1FDSW3AT0B0014719`

- URLs cannot contain minor or patch version numbers.
- Any URL referencing a major version number maps to one and only one fully qualified semver version (e.g. v2 is a pointer to v2.1.1 and cannot point to anything else).

### Internal Deployments

- Internal deployments should be addressable using a fully qualified semver version.
- The last 4 patch/minor releases will be deployed and available.

### Releases

- Releases within a major version should be non-breaking to clients.
- This implies that any minor or patch release be non-breaking.

- Non-major releases should document all fixes, improvements, etc. in a public-facing change log.

### Production

- All URLs must contain a version number; no implicit “version-free” URLs are allowed in production.
- Implicit “version-free” URLs should be available in development environments, however.

- If your software is being used in production, it should already be 1.0.0.
- If you have a stable API on which users have come to depend, it should be 1.0.0.
- If you’re worrying a lot about backward compatibility, it should probably already be 1.0.0.
- If there are API Contract Tests implemented, it should be 1.0.0.

### Deprecation

- No more than two major versions can be exposed publicly at any given time.
- On the stable release of any major version n+1, current version n must enter a maximum of 180 day deprecation window.

- Deprecation requires:

  - a) public documentation be updated reflecting the target deprecation date.
  - b) broad-based communication channels (e-mail, slack, etc.) be exercised to inform all known clients of that version that the version is being deprecated.
  - c) should repeat every 10 days for all parties who have not opted out.

- Once a deprecation window is hit, initiate a blackout process and generate an HTTP 410 for some minor fraction of each day (e.g. 5 minutes every hour) for 14 days, where on the 14th day the old API permanently generates a 410
