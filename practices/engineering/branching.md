---
title: 'Git Branching Strategy'
weight: 5
---
![Github Flow Illustration](/images/engineering/GitHub-Flow.webp)

* By default, most teams on Platform+ Tech should be using GitHub Flow
* Some teams might find continuous integration difficult when sticking to GitHub Flow and can consider a mixture of GitHub and Git Flow. These criteria may include:
    * Teams simultaneously handling high volumes of urgent production support fixes alongside development work
    * Mobile applications that rely upon app store updates or reusable components
    * Embedded software (which could have multiple trunk/master branches to support multiple versions of hardware)