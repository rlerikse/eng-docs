---
title: 'Key Technologies'
description: Technologies used by the Platform Validation team
weight: 6
---

Platform Validation uses a variety of technologies to aid in verifying feature and defect work implemented by product
teams across Platform+ Tech. Below are the main technologies used:

## Cypress

* A web automation framework based on JavaScript that was selected as the primary tool for automating web UI automated
  tests
* Considered a more user-friendly tool as compared to Selenium
* Several reasons why Cypress was chosen:
    * The ease to setup the environment
    * The ability to execute tests within the browser
    * The ability capture snapshots at test execution
    * The ability to not have to add wait commands

## Playwright

* A web automation framework based on TypeScript that was selected as a secondary tool for automating web UI automated
  tests
* Provides an easier workaround with products that have iFrames within their UI as compared to Cypress
* It allows for cross-browser web automation as well as parallel testing

## Perfecto Mobile

* A cloud device farm tool that provides access to mobile devices (phones and tablets), as well as desktop browsers for
  manual and automation testing purposes
* It provides the ability for developers, test engineers or designers to verify products across real physical devices in
  a quick and easy manner as well as across a suite of devices that varies in screen sizes, resolutions, platforms and
  operation systems
* To request access to the Perfecto tool, please reach out to the Platform+ Tech Enablement team
* For instructions on how to use Perfecto mobile, please reference the Perfecto Mobile How to document

## Datadog Synthetic Browser Test

* Automated web UI tests that can be configured to run at specific times, across different regions and different browser
  type
* Useful for creating quick UI tests, Platform Validation uses this to complement our Cypress tests

## ModHeader

* Extension for modifying HTTP request and response headers
* By using supplied cookie information from the product team, Platform Validation was able to support testing the
  staging environment of Content and Brand Marketing more easily without the need to be actively connected to the VPN
  network

## Accessibility Insights
* Extension to evaluate web accessibility of the current webpage within your browser (specifically within Windows)
* Useful for doing a high-level sweep of any potential accessibility errors for any web products 

## Narrator / NVDA / Voiceover
* Screen-reading application within Windows, which we pair up testing with Edge browser [Narrator]
* Screen-reading application within Windows, which we pair up testing with Chrome browser [NVDA]
* Screen-reading application within MacOS [Voice Over]
* Useful for doing any assistive (screen reading) testing for software products  

## Color contrast analyzer (CCA)
* Tooling that determines the contrast ratio of colors to optimize your content for individuals with vision disabilities
* Useful for testing color contrast to ensure returned value is within the WCAG guidelines 

## WAVE Evaluation Tool
* Extension to evaluate web accessibility of the current webpage within your browser 
* Useful for doing a high-level sweep of any potential accessibility errors for any web products 

