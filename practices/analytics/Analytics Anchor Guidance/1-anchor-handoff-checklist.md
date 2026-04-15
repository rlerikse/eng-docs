---
title: Anchor Handoff Checklist
weight: 1
---

The anchor is a key role in our product-driven organization, and has increased responsibilities, including having a key role in managing GitHub Repositories and Cloud Infrastructure. When the anchor changes for a product, it can be disruptive to the product. As such, this guide is meant to document the key steps needed for updating ownership in order to simplify process

## Checklist

This checklist is meant as a guide of the updates required when a product anchor or product line anchor changes. This list is not meant to be exhaustive; some products may have more complicated situations and require additional work, but the goal is to capture some of the essential steps and provide guides to make the transition as simple and seamless as possible.

### 1. Update _Delegation of Authority_ Form

Based on Office of Internal Controls (OIC) procedure, the GTM Lead needs to delegate authority to approve code releases to the Anchor via a form. When the anchor changes, the _Delegation of Authority_ form needs to be updated to remove the old anchor and to add the new anchor. The Product Manager can assist with this request.

### 2. Add New Anchor as Administration of Github Repositories

If the product has its own GitHub repositories, the new anchor will need to have administrator privileges.

### 3. Transfer Management of GCP infrastructure

If the product does not have their own dedicated infrastructure in Google Cloud, this section can be skipped.

Changing ownership and management of GCP infrastructure is complex, and requires updating records in multiple systems.

1. The new Anchor should request the `Infrastructure Developer` role for the project in [Access Management & Authorization](https://www.accessmgmt.company.com/CspsWeb/selectDataBegin.do?fromBookMark=true&entityName=ProductAppTechAccess&roleName=Infrastructure%20Developer). This role is required in order to make any changes to the infrastructure in [Cloud Portal](https://www.cloudportal.company.com/login). Consult the [infrastructure developer role summary](https://we.build.enterprise.com/docs/practices/analytics/Analytics%20Anchor%20Guidance/infrastructure-developer-role-summary) for more details and how to request access.

2. Add New Anchor as Member & as an Owner on all relevant FIM groups (Developer, Secret Management, etc.) for the relevant GCP project(s) in the [Enterprise Identity Management](https://iam.company.com/IdentityManagement/default.aspx) portal.

3. Update EAMS records for Application, if relevant. Specifically, the anchor or product line anchor who owns the infrastructure should be listed as the `Architect`, and the product group anchor should be listed `Architecture Delegate`

### 4. Update Documentation

If it is out of date, the outgoing anchor should update any important documentation. The product should already have a [runbook in GitHub](https://we.build.enterprise.com/docs/cep/runbook) (preferably as a Wiki) that covers the following:

1. Document and review current models, including data sources, required data cleaning, model retraining and evaluation metrics, etc.
2. Deployment processes, especially CI/CD pipelines (Tekton, Cloud Build, etc.).
3. Document scheduled processes (Airflow DAGs, Scheduled Queries, etc.).
4. If the product is in production, also update and review Disaster Recover Plan (DRP).

## Best Practices

Here are some additional best practices which can help to simplify the anchor transition and can be done now!

- If the product team owns their own FIM groups, GitHub Repos, and GCP Infrastructure, it is helpful to have the PLA or PGA added as a fallback on all FIM groups and GCP infrastructure to ensure continuity _before_ the anchor changes.
- Where feasible, infrastructure should be condensed at the Product Line level and managed by the Product Line Anchor
- Documentation should be updated periodically, and should be reviewed at least yearly and when the Kanban stage changes. The specific requirements of documentation will vary depending on the Kanban stage of the product.
