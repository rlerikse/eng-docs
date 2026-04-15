# AI assisted coding

AI Introduces opportunities to augment the development workflow. This policy sets out direction and boundaries when integrating AI tooling into the software delivery lifecycle.

## Scope

This policy applies to all developers who use
generative Al tools for code completion within ProTech.
It extends and complements Organization policy. Where conflicts
arise, presidence should be given to Organization policy.

## Tooling

[Organization policy](https://www.policyportal.company.com/) should be followed for the use of any software, including AI tooling. Only use approved tools and models that appear on [EAMS](https://www.eams.company.com/).

### Open source

Opensource models and tools should not be used until they have been added to [EAMS](https://www.eams.company.com/). Onboarding is possible through the [ProTech EAMS process](https://sharepoint.company.com/:p:/r/sites/EnterpriseTech/FPDP%20General%20Documents/FP%20Architecture/Tech%20Mgmt%20Process.pptx?d=w812c25fb4d5a48db86afc53f4ee38065&csf=1&web=1&e=fDbMK3&nav=eyJzSWQiOjIxNDQ4Njc5NzIsImNJZCI6Mzk3MzEwMDM4MH0).

Open source models and tools are available on the internet. Special consideration should be given to how their use fits into Organization policy including by not exclusively; protection of Organization data and licensing. AI **models** come with their own licenses which must be considered in addition to the associated tooling. The technology standards processes should be followed before using these tools (EAMS entry).

Any model can be influenced or biasted by it's training, datasources and prompts. They are challenging to inspect and unpredictable, making evaluating their safety a large topic of research. Commercial and open source models are succeptable. However opensource models are especially vulnerable to this, where rebuilding yourself from source (re-training off the dataset and code) can be expensive and trusting the origin something done with care. Models can even be rogue and designed to compromise the output or manipulate the user of the model.

### External APIs

Sending any data to external APIs which haven't been officially onboarded and been through associated security review is forbidden. Including telemetry of usage. This is especially important in AI tooling as the telemetry can include sensitive Organization data such as code and future product information.

:::warning
Telemetry in some AI tooling is sent even when using local only models.
:::

## Intellectual Property

Developers who use Al tools must ensure that any
features designed to highlight and/or block outputs
that match public code are active at all times.

## Responsible Use

Developers who use generative Al tools for code
completion must use the tools responsibly,
to assist in coding. Generative Al tools are not a
replacement for critical thinking and coding
expertise. You are responsible for the code you
write with the help of Al tools, and you must follow
the same policies and practices you would use
for any other type of code that you did not originate.
Use of the tools must be consistent with any
agreements or policies or practices that apply to
your project.

:::info
AI Tools are not a replacement for pairing or code review.
:::
