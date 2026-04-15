# Handling S/PII in Frontend Applications

## Overview of S/PII

**Definition:** Information, which if lost, compromised, or disclosed without authorization, could result in substantial harm, embarrassment, inconvenience, or unfairness to an individual.

These following lists should NOT be regarded as an all-inclusive list of sensitive data elements. Context is also important in determining the sensitivity of PII. PII that might not include the data elements identified may still be sensitive and require special handling if its compromise could cause substantial harm, inconvenience, embarrassment, or unfairness to an individual.

### Stand Alone

- GPS Coordinates with 5-digit precision
- Drivers license or state ID numbers
- Social Security numbers (SSN)
- Passport numbers
- Financial account numbers
- Biometric identifiers

### In Combination

- Vehicle Identification Numbers
- GPS Coordinates
- Personal email
- Personal addresses
- Account passwords
- Last 4 of SSN
- Date of birth

The above are examples, but not all-inclusive.

More details about Organization’s overall SPII policies can be found [here](https://www.policyportal.company.com/D2/#d2).

[Link to EU privacy data](https://sharepoint.company.com/sites/DataProtectionOffice/SitePages/Personal%20Data%20Information.aspx)

## Implications

Platform+ currently supports a variety of 3rd party software solutions on frontend applications that have an elevated risk regarding S/PII data:

- Adobe Analytics
- Quantum Metric
- OneLink
- DataDog (Not in scope)
- Optimizely (Not in scope)

Usage data ranging from analytics to session replay is being captured and recorded when our users use our applications. As Platform+ Tech engineers and product teams, we need to ensure that risks of exposing our customer’s S/PII data are minimized. Mechanisms to safeguard the transmission of S/PII data to these 3rd party solutions MUST be implemented.

## Mitigation

**Input Elements:** All input fields MUST be blocked by default.

**OneLink:** All input fields MUST be given the classname `OneLinkNoTx`.

**Quantum Metric:** All input fields MUST be provided with the data attribute `data-qm-block`.

```html
<input
  id="social-security-number"
  classname="OneLinkNoTx"
  data-qm-block="true">
  012-23-2233
</input>
```

**Exception:** If the user provided value of an input field is not considered S/PII AND you have need to query against the user provided value in Quantum Metric, then you may exclude the input field from being ignored.

**Contextual Elements:** All contextual elements displaying S/PII data to the user MUST be blocked. This applies to all HTML element types excluding `input` (ie. `<span>`, `<label>`, `<div>`, `<p>`, `<body>`).

```html
<p
  id="social-security-number"
  classname="OneLinkNoTx"
  data-qm-block="true">
  012-23-2233
</p>
```

**Adobe Analytics:** Teams MUST NOT transmit S/PII data to Adobe Analytics.

Because we do not want to block all DOM elements by default, for contextual elements we need to maintain increased awareness of the type of data being displayed on the screen and mitigate the exposure risks using good judgement.

Product teams building new user experience should include S/PII blocking as an acceptance criteria if the new experiences expose S/PII data to the end customer.