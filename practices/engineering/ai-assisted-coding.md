# AI assisted coding

:::tip
As a primer for AI assisted coding use and tooling, please read the [related engineering CEP](../../cep/ai.md).
:::

Try to think of LLMs as another human. They have a limited capacity to work on information in their minds at once (context window expressed in tokens) and their knowledge and experience comes from the model and its training. Using this context window we can give them examples of our code, ask questions and give them the history of a conversation so far (to simulate a conversation).

Like a human, the LLM needs context and precise instructions ([prompts](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#whats-a-prompt-and-what-is-prompt-engineering)) to carry out work that is useful. In the case of CoPilot, some of this context and prompt crafting is done by the tooling and coding specific training and engineering to increase the usefulness of the outputs. Well written code with specific and well scoped comments and names are, like for humans, easier for the LLM to understand.

The rest is down to the developer. [Crafting good prompts](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#3-best-practices-for-prompt-crafting-with-github-copilot) and [exposing the right context](https://github.blog/developer-skills/github/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/#1-open-your-relevant-files) can have a large impact on the results.

## Audience

All developers and users of AI code assistant tools.
The content is tailered around the use of github CoPilot, but the concepts and practices can be applied to any tooling.

## Tooling

Ranked list of preference:

1. [Github CoPilot](https://sharepoint.company.com/sites/SDE/SitePages/github-copilot/default.aspx)
2. GCP (Gemini code assist)
3. Organization LLM

Github Co-Pilot is the preferred tool of choice for code assistance. It implements code specific ehnancements such as vulnerability and licensing checks on generated outputs. Although this does not negate your responsibility to check for security issues.

## Onboarding CoPilot

Follow the [onboarding documentation](https://github-guide.company.com/ch11/02-copilot_onboarding.html) from the organization's GitHub team.

## Use cases

A non-exhaustive list of tasks AI tooling can help with. This is gathered from feedback from CoPilot users within ProTech and outside.

- ![Run terminal commands from GitHub Copilot Chat](https://github.blog/developer-skills/programming-languages-and-frameworks/10-unexpected-ways-to-use-github-copilot/#1-run-terminal-commands-from-github-copilot-chat)
- Write unit tests
- Learn a new framework
- Translate between languages or patterns
- Bootstrap
- Refactor
- [Accelerate code reviews](#code-reviews)
- Ideas generation
- Explain code
- Debugging

### Code reviews

Cloning down branches in code reviews enables the use of refactoring prompts inside CoPilot chat to suggest code changes or comments to add to the pull request conversation.

Similarly as a PR author, you can take comments from pull request conversations and combine them into a refactoring prompt to accelerate PR resolutions.

## Training

### From Github

- [How to write better prompts](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/)
- [How to use CoPilot in your IDE - Tip, tricks and best practices](https://github.blog/developer-skills/github/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/)
- [10 Unexpected ways to use CoPilot](https://github.blog/developer-skills/programming-languages-and-frameworks/10-unexpected-ways-to-use-github-copilot/)

### from the organization

- [CoPilot FAQ](https://github-guide.company.com/ch11/04-copilot_faq.html)
- [Onboarding](https://github-guide.company.com/ch11/02-copilot_onboarding.html)

## Best Practices

- Own the code. You should always assess, analyze, and validate AI-generated code.
- [Set the stage with a high-level goal.](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#1-set-the-stage-with-a-high-level-goal)
- [Make your ask simple and specific. Aim to receive a short output.](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#2-make-your-ask-simple-and-specific-aim-to-receive-a-short-output-from-github-copilot)
- [Give an example or two.](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#3-give-github-copilot-an-example-or-two)
- [Experiment with your prompts.](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#1-experiment-with-your-prompts)
- [Keep a couple of relevant tabs open.](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#2-keep-a-couple-of-relevant-tabs-open)
- [Use good coding practices.](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/#3-use-good-coding-practices)
- Ensure thorough code coverage.

## Maintaining quality

Code suggestions from AI don't always have the full context of your code or correctly apply all the other competing priorities in crafting secure and maintainable code. We must use our experience and judgement to guide the results.

LLMs are next token predictors trained on a large corpous of good and bad code. CoPilot attempts to load your code base into context to inform its decisions and make them relevant to your codebase. However a common code quality issue according to research is the reduction of the DRY principal and increase in code churn.

This can happen due to the tool not having awareness that it already suggested something semantically identical elsewhere in the code.

:::info
Sonarcube should be harnessed on all repos where AI assisted coding is used, to help identify AI generated duplicated code.
:::

### Security

AI will make mistakes, and doesn't have understanding of the principals it is applying. It can respond with security best practices and then misapply them in the code it generates. The continual theme to keep in mind is to check and own the code.

Refer to OWASP’s [Top 10 for LLMs](https://owasp.org/www-project-top-10-for-large-language-model-applications/) for guidance.

The best way to build secure software is through a [secure software development lifecycle (SDLC)](https://snyk.io/learn/secure-sdlc/). All code written by, influenced or refactored by AI must also follow
the same or greater scruiteny than code you would write yourself. All code should be scanned by the security tooling in scope for the type of code you're writing.

:::warning
You should make sure your IDE or editor does not automatically compile or run generated code before you review it.
:::

CoPilot implements an AI-based vulnerability prevention system that blocks insecure coding patterns in real-time to make Copilot suggestions more secure. The model targets the most common vulnerable coding patterns, including hardcoded credentials, SQL injections, and path injections. This can aid in improving security, it also approximates the behaviour of static analysis tools to detect vulnerable patterns in code.

This might appear to contradict the above advice that you can't trust the AI to secure code. It instead complements it. When used correctly AI can help to improve security but it shouldn't be relied on completely. AI will make mistakes, hallucinate and confidently output wrong or broken things in a convincing way.

## Measuring AI use

Sending out an [AI impact survey](https://forms.office.com/Pages/ResponsePage.aspx?id=eruQyfRRm0O9NpwH-xBBwDosc8UjW_NMsv9WqO1dBypUNk1RUldZVkdXTVdVUEZJUVNGU1dHSDlLNi4u) once a quarter within your team can help identify points of intervention.
