---
sidebar_position: 4
---

# GCP Data lineage Limitations

- You can see the objects in data lineage only if you have access to
  - underlying object and
  - data lineage permissions

- Lineage is limited to Pro360 project only.
  - Lineage may or may not be available for the upstream/downstream systems
  - Lineage links outside Pro360 projects are subject to availability and access

- All lineage information is retained in the system for 30 days only.
  <!-- - this may lead to cases when an object is deleted but visible in lineage for 30 days. -->

:::info

this may lead to cases when an object is deleted but visible in lineage for `30 days`.

:::

- Data Lineage is enabled on per project
