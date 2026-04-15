---
title: 'Software Engineering'
description: Turning coffee into code ☕️
weight: 1
---
## Software Engineer
Software Engineers (SWEs) are responsible for technical success of products. SWEs within Platform+ Tech practice collaborative
development through programming in pairs, performing technical retrospectives, conducting code reviews, and reducing
knowledge silos through pair swapping. SWEs validate quality by seeking feedback from product managers, product users,
and automated testing through a continuous integration / continuous deployment pipeline.

Delivery needs are balanced with optimizing features and reducing technical debt. Features are implemented in the
priority order that’s defined by the team’s Product Manager. Backlogs are regularly populated with chore stories that
contain instructions for reducing technical debt and improving application architecture.

We focus on developing clean code & use a test-driven development approach. As the products take
form, higher abstraction tests are built in our CI/CD pipeline including automated acceptance, integration, performance,
and component tests.

Recognized design patterns are used with a bias towards the established set of technologies being implemented across
Platform+. We identify service level objectives, adopt design patterns and recommend the use of new technologies,
languages, and frameworks appropriately. Software engineers implement non-functional requirements such as security,
performance, logging, load testing, and deployment.

## Anchor Engineer
Teams have anchor engineers that provide context to new engineers joining the team, product managers and members of other teams. Anchors have experience delivering software that team members can leverage as software design patterns are identified, application architecture is established, and quality of code is considered. The team’s anchor acts as steward, not the sole owner or gate, for good engineering decisions and healthy team collaboration.

![Anchor Image](/images/engineering/anchor.png)

<table class="docs-table">
    <thead class="docs-table">
        <tr>
            <th class="docs-table">Anchors Do</th>
            <th class="docs-table">Anchors Don't</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="docs-table">
                <ul>
                    <li>Actively code as much as possible</li>
                    <li>Facilitate conversations between product managers and developers</li>
                    <li>Keep the team focused on developing towards core business and product goals</li>
                    <li>Support broad architecture efforts outside of team</li>
                    <li>Think about sustainable solutions</li>
                    <li>Ensure software engineers groom the backlog with the Product Manager</li>
                    <li>Spread domain knowledge by performing pair swapping</li>
                    <li>Ensure backlog addresses an appropriate amount of technical debt</li>
                    <li>Spread accountability</li>
                    <li>Enable team members to be successful</li>
                    <li>Lead from behind</li>
                </ul>
            </td>
            <td class="docs-table">
                <ul>
                    <li>Make every architecture decision</li>
                    <li>Attend every meeting that requires an engineering subject matter expert</li>
                    <li>Make key decisions without consulting others, such as engineers, product managers, etc.</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

Product Line Anchors (PLAs) support all the product teams in a product line. They are senior engineers with significant systems design experience. These "anchor of anchors" help guide product lines and are stewards of the platform's code craftsmanship. They help anchors consider platform requirements such as scalability and performance and ensure their teams have robust test suites.

## Product Line Anchor
- Provide technical leadership to solve problems and remove blockers for the individual product teams
- Coordinate reuse, architecture, and interoperability strategy for teams in the product line
- Support consistency within the software engineering practice
- Work with other Product Line Anchors to drive consistency across Platform+ Tech’s Common Engineering Policies and systems
- Support platform architecture efforts and encourage coordination with Platform Services. Conduct talks on platform practices.
- Ambassador to raise issues to leadership on behalf of the Product Line's software engineers
- Work closely with the Product Line Managers and Product Line Owners to include continuous technical improvement in the Product Line roadmap
- Identify skill gaps and find learning opportunities to close those skill gaps
- Provide mentoring and coaching for anchors and engineers in the product line
- Lead anchors within the product line to help them be more successful in their role
- Help teams prepare for Tech Council meetings, and address action items from them
- Partners with Product Line ownership and management to allocate software engineers to teams within product line
- Pair program to stay current on the code base / tech stack

## Product Group Anchor
- Work closely with the Product Group Managers to include continuous technical improvement in the Product Group roadmap Collaborates with other Product Group Anchors to reduce complexity across the portfolio, enhance interoperability between services, and make key design decisions across the portfolio.
- Ensures engineering excellence (e.g. best practices and quality) is achieved within product group.
- Attends Platform+ Tech Portfolio Tech Council and their Product Group Tech Council.
- Cascades relevant information from Platform+ Tech Portfolio Tech Council to appropriate members of their product line.
- Chairs the Product Group Tech Council with their Product Group Owner and Manager. As products in the product line move through delivery phases, PGA makes go/no-go decisions, provides feedback and support to accelerate software product delivery.
- Organizes Engineering Town Halls to ensure information sharing across the team, clarifying the bar for engineering excellence, and highlighting individual contributions.
- Curates the CoP Manifesto.
- Contributes to Product Group Anchor CoP, Product Line Anchor CoP, and Anchor CoP.
- Responsible for identifying and fostering software engineer, anchor, and product line anchor allocations within product group.

## Anchor Comparison
<table class="docs-table table-bordered">
    <thead class="docs-table">
        <tr>
            <th>Activity</th>
            <th>Product Group Anchor</th>
            <th>Product Line Anchor</th>
            <th>Product Anchor</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="vertical-center" rowspan="3">Product Delivery</td>
            <td>Work closely with the Product Group Managers to include continuous technical improvement in the Product Group roadmap</td>
            <td>Work closely with the Product Line Managers to include continuous technical improvement in the Product Line roadmap​</td>
            <td>Work closely with the Product Managers to include continuous technical improvement in the Product roadmap​</td>
        </tr>
        <tr>
            <td>Collaborates with other Product Group Anchors to reduce complexity across the portfolio, enhance interoperability between services, and make key design decisions across the portfolio.</td>
            <td>Works with Product Group Anchor to align product line delivery efforts with product group priorities (including the product group roadmap and external dependencies of the product group).</td>
            <td>Delivers in accordance to established product priorities and SLAs.</td>
        </tr>    
        <tr>
            <td>Ensures engineering excellence (e.g. best practices and quality) is achieved within product group.</td>
            <td>Ensures engineering excellence (e.g. best practices and quality) is achieved within product line.</td>
            <td>Ensures engineering excellence (e.g. best practices and quality) is achieved within product.</td>
        </tr>
        <tr>
            <td class="vertical-center" rowspan="2">Tech Councils</td>
            <td>Attends Platform+ Tech Portfolio Tech Council and their Product Group Tech Council. Cascades relevant information from Platform+ Tech Portfolio tech council to appropriate members of their product line.</td>
            <td>Attends each of their Product Group Tech Councils and Platform+ Tech Portfolio Tech Council when appropriate (e.g. sharing topics for awareness).</td>
            <td>Attends their Product Group Tech Council when presenting. Attends the Platform+ Tech Portfolio Tech Council when presenting.</td>
        </tr>
        <tr>
            <td>Chairs the Product Group Tech Council with their Product Manager. As products in the product line move through delivery phases, PGA makes go/no-go decisions, provides feedback and support to accelerate software product delivery.</td>
            <td>Assesses readiness for product through kanban Tech Councils. Before Tech Council presentations, assesses and gives feedback on the product's level of CEP implementation, quality of tech stack & architecture document being published, completeness of information included in Tech Council</td>
            <td>Co-presents with PM and PO at Tech Councils. Primarily responsible in these discussions to raise technical risks, brief on technical readiness of software products, share information on key technology decisions within their product, and share update on progress towards attaining SLAs & other key objectives.</td>
        </tr>
        <tr>
            <td class="vertical-center" rowspan="3">Engineering Communities of Practice</td>
            <td>Organizes Engineering Town Halls to ensure information sharing across the team, clarifying the bar for engineering excellence, and highlighting individual contributions.</td>
            <td>Active contributor in Engineering Town Halls. Identifies key contributors to present in Engineering Town Halls. Implements initiatives cascaded through Engineering Town Halls within their Product Line.</td>
            <td>Implements initiatives cascaded through Engineering Town Halls within their product. </td>
        </tr>
        <tr>
            <td>Curates the CoP Manifesto</td>
            <td>Contributes to CoP Manifesto</td>
            <td>Contributes to CoP Manifesto</td>
        </tr>
        <tr>
            <td>Contributes to Product Group Anchor CoP, Product Line Anchor CoP, and Anchor CoP.​</td>
            <td>Contributes to Product Line Anchor CoP and Anchor CoP meetings.</td>
            <td>Attends Anchor CoP meetings.</td>
        </tr>
        <tr>
            <td class="vertical-center" rowspan="2">Common Engineering Policy</td>
            <td>Curates common engineering policies</td>
            <td>Contributes to common engineering policies</td>
            <td>Implements common engineering policies.</td>
        </tr>
        <tr>
            <td>Identifies areas within software delivery process and application ecosystem that require cohesion across the platform and addresses them through common engineering policies.</td>
            <td>Identifies areas within software delivery process and application ecosystem that require cohesion across the platform and addresses them through common engineering policies.</td>
            <td>Balances cohesion vs coupling needs in system design and software delivery practices.</td>
        </tr>
        <tr>
            <td class="vertical-center" rowspan="3">Team Management & Allocations</td>
            <td>Responsible for software engineer, anchor, and product line anchor recruiting within product group.</td>
            <td>Responsible for software engineer and anchor recruiting within product line.</td>
            <td>Performs interviews for software engineers.</td>
        </tr>
        <tr>
            <td>Rotates software engineers and anchors across the Platform+ Tech team.</td>
            <td>Rotates software engineers and anchors across the product line.</td>
            <td>Rotates software engineering pairings within the product team.</td>
        </tr>
        <tr>
            <td>Develops team sizing proposals for product teams within product group.</td>
            <td>Develops team sizing proposals for product teams within product line.</td>
            <td>Advises Product Line Anchor on allocations needs of the product team.</td>
        </tr>
    </tbody>
</table>
