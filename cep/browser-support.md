# Browser Support


Run the command:

```
npx browserslist "> 0.2% in alt-NA or > 0.2% in alt-EU, Firefox ESR, not dead and fully supports css-container-queries"
```

### Breakdown

- Greater than 0.2% Market share in NA and those in the EU with greater than 0.2%
- Firefox Extended Support Release (ESR)
- No browsers that have not had support within the last 24 months
- Fully support the css feature [css-container-queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_queries)
- Preview the browsers in [browsersl.ist](https://browsersl.ist/#q=%3E+0.2%25+in+alt-EU+%2C+%3E+0.2%25+in+alt-NA%2C+Firefox+ESR%2C+not+dead+and+fully+supports+css-container-queries)

### Package.json extract

```json
{
  "browserslist": {
    "production": [
      "> 0.2% in alt-NA",
      "> 0.2% in alt-EU",
      "Firefox ESR",
      "not dead and fully supports css-container-queries"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}
```
