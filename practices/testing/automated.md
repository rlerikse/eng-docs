---
title: 'Automated Testing'
description: Fast, repeatable, reliable tests
weight: 4
---
## Benefits
Depending on the type of product, the team can choose to build an automated suite of test cases to aid in their testing practices. When implemented correctly, there are a number of benefits to automation:
* Improved test coverage and testing accuracy
* They provide a faster feedback cycle, and thereby a faster time to market
* The ability to quickly determine the stability of the product
* Less stress on the Platform Validation team, allowing them to focus more on exploratory testing rather than test plan execution
* Reduced business expenses in the long run

## Defining Automated Tests 
It is important to define the scope of your automated tests prior to writing your tests. For example, a common practice when planning for a successful automated test suite is to automate your product’s Smoke test plan, eventually followed by the Release Candidate test plan. 

Other test cases to focus on automating include
* High risk/business critical test cases
* Test cases that are executed often
* Test cases that are tedious or difficult to perform manually
* Test cases that are time-consuming (e.g., Data-driven tests)

It is also important to define the right tech stack for your automated tests. Some questions to ask yourself include:
* What languages/frameworks are the Software Engineers, Test Engineers on your team already familiar with?
* What is the most popular automated testing framework for your platform, browser, mobile device?
* How many platforms does your product support?
* What are some best-practices and design patterns you can employ with your language and framework of choice?

## Best Practices
Platform Validation has been creating automated tests, for different products. However, to be able to create these tests, the team needs to be able to identify UI elements. Below are some best practices we recommend product teams to follow such that it can help Platform Validation in the platform's automation efforts.
* Unique IDs should be implemented, wherever possible, for elements such that test engineers would be able to reference them for automation purposes 
* Avoid changing IDs frequently as this will break existing automation tests 
* Keep Platform Validation or test engineer updated ahead of time should UI/UX be changing that will potentially break existing tests 

## Automation Progress 
Platform Validation thus far have created tests for the Content and Brand Marketing team using Cypress, across the USA and Canada region. We have also created tests for the Digital Marketplace product using Playwright. If other product teams would like to create their own automated tests, do not hesitate to reach out to Platform Validation for help. We have also created [documentation](https://github.company.com/Pro-Tech/PV-Automation-Docs) should teams have questions on which framework should they be choosing for their product. Sample Cypress and Playwright tests were also integrated with DSO's frontend project generator to provide out of the box examples that should help new products with standing up their first tests. 


## Automation Updates
Refer to the below for recent changes that Platform Validation have introduced. 

### Boilerplate 
* Platform Validation has created a [Cypress](https://github.company.com/Pro-Tech/cypress-boilerplate) and [Playwright](https://github.company.com/Pro-Tech/playwrightJS-boilerplate) automation template for the Platform+ Tech Platform
* Any product teams within Platform+ Tech interested in designing and creating automation tests can utilize these templates to create automated tests in a clean, maintainable, consistent and organized manner while ensuring best practices are followed
* We have added information on which framework to choose over the other for teams looking to start writing their own tests 
* We have added authentication instructions to the boilerplate for folks looking to write tests for the authenticated experience

### Frontend Project Generator with UI Automation
* Both Cypress and Playwright sample tests have been added into the generator
* When a project is created via the generator, sample automated tests are included out of the box making it easier for teams to continue to create their own automated tests as their product develops

### Dynatrace Synthetic Browser Tests 
* Platform Validation has integrated synthetic testing as part of our testing strategy  
* It offers a fast and simple way of creating web UI tests for our products
* Platform Validation is using it to complement our Cypress tests, serving as an interim automation solution prior to having official Cypress tests implemented for products we support  
* DataDog provides an overall summary of our synthetic tests and has ability to trigger alerts and notifications to Slack channels 

