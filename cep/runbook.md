# Product Runbook

Automated runbooks surface helpful information to on-call responders immediately, shortening the incident response lifecycle and getting someone on-the-scene to quickly start fixing the incident. When creating your runbook, you’ll want to strike the perfect balance between automatically serving helpful instructions at the right time and providing useful information that helps people work.

Each app and service in Platform+ Tech must have a runbook present in their github repository. A product cannot move into the Launch kanban phase without a set of complete and accurate runbooks present in the product's github repositories.

Below is a runbook template to be included in every git repo that has applications running in a production environment.
:::info
# Runbook Template

## Table of Contents

A Table of Contents with links to main sections

## General

A quick description of the services. Ideally only 1 to 2 sentences max. Why does this service matter? What is it's core functionality? What Features does it provide users?

## Dashboards

Links to the Dashboards for this service

## Alerts

Links to the Alerts for this service
For Every Alert there should be a corresponding section in alphabetical order

### Alert Title

Alert Description: Why do we have this alert? What does it mean? What is typically the cause of this alert?
Alert SLAs, SLOs, SLIs: What real metrics are the alerts tied to?

#### Impact to Customers:

How does this situation impact our customers? If the customers are not being impacted, this is a good indicator that the alert can be deleted.

#### Remediation Steps:

Checklist manifesto style steps for how to resolve this alert. A person who has never worked on our stack should be able to follow these steps and remediate the incident. If it cannot be remediated, include escalation steps here.

    Do this
    Check this graph
    Do this thing
    Do this other thing
    Verify service has recovered

## Contact Info

Team contact info. Potentially contact info for who to escalate to. What services do we have dependencies on? How do we escalate to them? Define this information here.

## Latest Deployments

We do Production Change Management Deployments via Jira or Rally, we included a link of all the latest changes here. Recent commits, CI log etc... is incredibly helpful in understanding what code is deployed to the system, what recent changes were made.

## Deployment

How do you deploy this services. Favor Checklist manifesto style lists here as well.

    Do this thing
    Do this other thing
    Finally do this thing

### Zero Downtime Deploy

Instructions on how to achieve zero downtime Deployment

    Do this to introduce new version of the app
    Test the new version of the app
    Redirect traffic to newer version of the app
    Take out the previous version of app from live traffic



### Rollback Deploy

Instructions on how to Rollback a Deploy.

    Get the rollback build here
     Do this thing
    Do this other thing.

## Credentials

Key credentials, e.g. login / passwords for test accounts.

## A list of back-end resources

Back-end dependencies to the service

## Test plans and test scripts

Links to test plans and the associated test scripts that can be used for smoke testing and other validation purposes
:::
