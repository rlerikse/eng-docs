---
title: 'Managing the Delivery'
weight: 7
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

This section outlines the Product Manager's responsibilities in managing the product delivery process, ensuring efficient workflow, high-quality output, and successful product launches. We utilize Jira for backlog management; for detailed information on Jira best practices within Platform+, please refer to the following resources:

- [Platform+ Jira](https://github.company.com/Pro-Tech/jira-planning-and-migration)
- [Jira Project & Plan Hierarchy](https://github.company.com/Pro-Tech/jira-planning-and-migration/blob/main/Jira%20Structure.md)
- [Visualizing the Workflow in Jira](https://github.company.com/Pro-Tech/jira-planning-and-migration/blob/main/Jira%20Boards.md)
- [Jira Plans for Cross Cutting Efforts](https://github.company.com/Pro-Tech/jira-planning-and-migration/blob/main/Product%20Line%20Manager%20Best%20Practices.md)
- [Jira Issues & Backlog Artifacts](https://github.company.com/Pro-Tech/jira-planning-and-migration/blob/main/Jira%20Issues.md)

## Workflow Management & Visualization
The Product Manager maintains and utilizes visual representations of the product development workflow (e.g., Kanban boards, burndown charts) in Jira. This ensures transparency, facilitating communication, collaboration, and early identification of potential bottlenecks. Effective use of Jira plans is crucial for visualizing the progression of work, even across multiple product lines or groups.

## Backlog Items (day-day)
- **Chores:** Identifying and prioritizing tasks that improve system maintainability, performance, or address technical debt.
- T**echnical Spikes:** Identifying and prioritizing short investigations to mitigate technical risks and inform architectural decisions.
- **Defects:** Ensuring all reported defects are captured, prioritized, and addressed promptly.
- **User Stories:** Defining, refining, and prioritizing user stories, ensuring clarity, appropriate sizing, and inclusion of acceptance criteria.

:::tip

<Tabs>
  <TabItem value="techniques-tools" label="Documentation">Learn more about [Chores, Spikes, Defects, and User Stories](/docs/practices/product-management/8-techniques-tools/2-product-development-delivery/1-backlog-artifacts.md)</TabItem>
  <TabItem value="degreed" label="Video">Learn more about [Chore and Spike stories](https://degreed.com/videos/chore-spike-stories?d=32067571&orgsso=organization&inputType=Video)</TabItem>
</Tabs>

:::

Make sure to think through the **Defining "Definition of Ready" (DoR) and "Definition of Done" (DoD)** within the context of you backlog and states of your delivery. This leads to improved efficiency and predictable delivery.

## Backlog Items (Features and higher)
The Product Manager defines, sizes, and prioritizes features within the product backlog. Each feature must be clearly articulated, aligned with the product roadmap and strategic objectives, and broken down into smaller, manageable user stories.

:::tip

<Tabs>
  <TabItem value="techniques-tools" label="Documentation">Learn more about [Writing epics, sub-epics and features](/docs/practices/product-management/8-techniques-tools/2-product-development-delivery/1.1-features.md)</TabItem>
  <TabItem value="degreed" label="Video">Learn more about [Writing epics, sub-epics and features](https://degreed.com/videos/writing-sub-epics-features?d=32616260&orgsso=organization&inputType=Video)</TabItem>
</Tabs>

:::info
If you are on Jira remember the following:
- Features (Rally) --> Epics (Jira)
- Sub-Epics (Rally) --> Saga (Jira)
- Epics (Rally) --> Quests (Jira)
:::

## Release Management
The Product Manager oversees the release management process, including:

- Planning release cycles
- Coordinating with various teams (development, marketing, etc.)
- Ensuring smooth and successful product launches
- Defining release criteria
- Managing stakeholder expectations