---
title: 'Working with Platform Validation'
description: How to engage with Platform Validation and the process we follow
weight: 3
---
## Testing Engagement
During a product’s development phase, each product team needs to engage with the Platform Validation team to:  

1. **Understand the product’s scope:** Understand the overview of the product’s roadmap, determine if testing will be supported, identify and define what platforms and operating system versions (if any) the product will be supported on (e.g., For a web product, what browsers do we plan on supporting, browser versions, PC and/or Mac, etc.), determine if any additional testing will be required besides exploratory testing and story verification, gather important deadlines, release milestones, etc.   
2. **Establish a cadence:** Align on a testing cadence, determine how stories will be verified by the Platform Validation team, set up the necessary Flow States for stories in the product team's Rally Board  
3. **Determine method of communication:** Align on method of communication for notification of the beginning of testing, discussion of stories or product, as well as testing feedback from the Platform Validation team  
4. **Determine product team rituals/ceremonies:** As test engineers are embedded into the product team, align on the rituals/ceremonies that the members should attend.

## Testing Process
The Platform Validation team follows these steps as part of the testing process: 
1. **Story verification** – Ensuring delivered stories are working as expected 
2. **Exploratory testing** – Explore testing around newly delivered stories or areas with newly developed code 
3. **Test Plan execution** – Execution of a smoke test plan (consists of the main user flows of the product) or a release candidate test plan (consists of all features of the product)
4. **Wrap up** – Updating of delivered stories with testing notes, creating new bugs within Rally project, providing testing updates to product team/stakeholders relating to latest testing session 

## Story Verification
Once the software engineers have committed code for a particular story, verification can begin shortly after. This is to ensure that everything from designs to feature requirements within a story has been implemented correctly and meets the defined acceptance criteria.

Once story verification is completed, the test engineer will make a comment in the Discussion tab of the story with the result - passed/failed/unable to test, build version and environment, platform/OS versions tested on (if applicable), devices/browsers (if applicable), etc. If the story failed or if it was untestable, explain why. Attach screenshots, screen recordings, and/or logs whenever possible. The tested story will then be moved to the appropriate Flow State as established between the product team and Platform Validation. 

## Exploratory Testing
Once all the stories have been verified, the Platform Validation Team can begin an Exploratory Testing session on the build. 

The focus of an exploratory testing session is usually around the delivered features/bug fixes or a particular area of the product that is deemed critical and in need of extra attention. A pair of Test Engineers execute an Exploratory Testing session and document their progress and results in a Testing Charter document.

A testing charter document is prefaced by its mission statement (aka a “charter”) in the following format:

**Charter**: Explore (**target**) with (**resources**) to discover (**information**)

*Target*: Where are you exploring? It could be a feature, a requirement, a module.  

*Resources*: What resources will you bring with you? Resources can be anything: a tool, data set, technique, configuration, or perhaps an inter- dependent feature.  

*Information*: What kind of information are you hoping to find? Are you characterizing the security, performance, reliability, capability, usability, or some other aspect of the system? Are you looking for consistency of design or violations of a standard?  

A good charter offers direction without over-specifying test actions. When charters are too specific, they become just a different (and weird) way of expressing individual tests. On the flip side, charters that are too broad run the risk of not providing enough focus.  

**Rule of Thumb: A Charter Should Be  Brief Enough To Tweet!**

## Bug Reports
A Bug Report documents a defect in the product and how exactly it has occurred. It is a roadmap you give your Software Engineers to help them get to the bottom of a software issue and fix it. Bug reports in Rally are logged and can be found under the Quality > Defects tab.

A good bug report contains relevant information in the following format:
* Title - A stakeholder should be able to understand the defect at a high-level just by reading its title. 
A good practice is to word this from the user’s perspective I.e. in third-person
* Steps to Reproduce - A list of detailed steps taken to arrive at the defect
* Expected Results - What you’re expecting to happen once the defect is addressedActual 
* Actual Results - What happened as a result of this defect
* Frequency - The frequency with which this defect is reproducible. Usually documented on a scale of 0%-100%
* Devices/Browsers - The platform(s) on which you were able to reproduce the defect
* Notes - A place to jot down any miscellaneous info that may be relevant to explaining the defect

## Test Plans
During the many phases of a product’s development, it becomes necessary to execute a pre-defined set of test cases to assess the product’s overall health and release readiness. The two most essential types of test plans to maintain and execute are the Smoke test plan, and the Release Candidate (RC) test plan.

The Smoke test plan is a non-exhaustive set of test cases that aims at ensuring that the most important functions of the product works. This is useful when you need to decide if a product is stable enough to proceed with further testing, to verify that a hot fix you need to get out for release hasn’t broken the rest of the product, and/or just to gather a quick assessment on the overall health. The Smoke test plan can be executed on as-needed basis but is usually run at least once a week.A test case is usually documented with the following info:
* Title - An apt title for the test case
* Pre-condition(s) - A set of pre-conditions (e.g., User should be on a specific screen in the application) that need to be true before the steps for this test case can be executed
* Steps - A detailed list of steps to perform the test case
* Expected Results - What you’re expecting to happen after performing the steps

### Release Candidate Test Plan
A Release Candidate (RC) test plan is an exhaustive set of test cases that assesses every feature and possible behavior of a product. The purpose of this test plan is to ensure that newly added code has not broken existing functionality, and to determine a product's release readiness.  When the all stories have been verified, and exploratory testing has yielded no major bugs, the team can begin executing the release candidate test plan. This test plan encompasses a thorough run through of all the product’s features thus far, as well as exposing the product to different variables (e.g. Poor internet connection, etc.) and edge cases.

