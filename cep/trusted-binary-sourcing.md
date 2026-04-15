# Trusted Binary Sourcing

Executable Binary artifacts that may end up committed to source, such as the Gradle wrapper as well as binaries used as part of the CI/CD pipeline, should be sourced from JFrog Artifactory whenever reasonably possible. This ensures the integrity and traceability of these binaries.

## Requirements

Executable binary artifacts that will be committed to source should be sourced from JFrog Artifactory when reasonably possible.
Using JFrog Artifactory as a proxy for official repositories is encouraged. In cases where it is not reasonably possible to initially source artifacts from Artifactory, these artifacts should be deployed to JFrog Artifactory as soon as possible. If a team is unable to deploy artifacts to their repo they should request support in the #help-jfrog channel.

## Deploying Binaries to JFrog Artifactory

If binaries are not currently present in Artifactory they can be deployed to the team's repository using the following methods:
1. Using the JFrog UI "Deploy" functionality for the desired repository: https://jfrog.company.com/ui/repos/tree/General/
2. The JFrog CLI: https://docs.jfrog-applications.jfrog.io/jfrog-applications/jfrog-cli/cli-for-jfrog-artifactory/generic-files

Language-specific examples, including examples for Maven, Gradle, and Node.js/npm can be found at https://jfrog-guide.company.com/ch0M/04-update-workflows.html
Support for JFrog is available in the #help-jfrog Slack and Webex channels.
