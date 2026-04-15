# Code And Resource Naming
> There are only two hard things in Computer Science: cache invalidation and naming things. -- *Phil Karlton*

Naming standards are important to avoid confusion of intent. Standards at a Platform+ Tech level help facilitate meaningful conversation across product teams, and simplify the job of teams like Dev Enablement who support the entire platform.

While most naming standards derive from an industry standard, sometimes the industry hasn't coalesced around one standard. In this case, we should choose.

The list can have new additions or can be modified at the weekly Engineering Leadership/Anchors meeting.

## GitHub

Use this specific naming convention to be able to identify Platform+ assets.

- **Team Name**: `pro-${TEAM_NAME}`
- **Repository Name**: `${PRODUCT_TEAM}-${SERVICE_NAME}` 
  - i.e., vmi-configurator-service.  All lower case, include product team (vmi, bbc etc) and then service name.
  - Preferable, but not applicable for all technologies. 
  - Please prefer the product name and not the team name.
- **Topics**: set the value of the repository topics to the following values
  - Environment: Choose "production" or "non-production" based on the environment
  - App ID: Use the format "appid-xxxxx", replacing xxxxx with your actual app ID number. For example: “appid-12345”
  - Add "enterprisepro" to your topics as is
  - Product: Follow the format "p-xxxx", replacing xxxx with your actual product identifier. For example: “p-example-value”
  - Product Group: Follow the format "pg-xxxx", replacing xxxx with your actual product group identifier. For example: “pg-example-value”
  - Product Line: Follow the format "pl-xxxx", replacing xxxx with your actual product line identifier. For example: “pl-example-value”


## Java and Spring

Package structure - `com.organization.protech.` - Don’t include product line or team name. Example: `com.organization.protech.depotcharger`

## Headers

Hyphen-separated and beginning with "X" e.g.: "X-headerName".
As per [RFC](https://www.ietf.org/rfc/rfc2047.txt) the header to accept subscription id, should be X-Subscription-Id; not subscriptionId, not subscriptionid, not sid. Check the [industry standard headers and documentation](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers).

## Error handling

Error codes, messages, how to handle multiple errors in one call can be found in the [Enterprise API wiki](https://www.eesewiki.company.com/display/FEAPIS/Style+Guides) (VPN Accessible)

## Google Cloud Function

The naming standard should be upper camel case. It should be Product and then Function. For example, VehicleService-AddVehicle

## Google Cloud Run

The naming standard should be upper camel case. It should be Product and then compute name. For example, VehicleService-Registrations

## DevSecOps
```
Tekton : ${micro-service-name}-${environment-name} 
SonarQube Project Key: com.organization.pro-tech:${product-name}-${micro-service-name}
SonarQube Project Name: ${product-name-acronym}-${micro-service-name}
```