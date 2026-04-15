---
sidebar_position: 1
---
# Governance and Catalog Standards

## Governance Standards ⚖️

### Introduction

- **Purpose**: To establish standards for data governance and cataloging in the Pro360 data warehouse environment.
- **Scope**: These standards apply to all teams and developers working with the Pro360 data warehouse.

### Roles and Responsibilities

- **Data Stewards**: Responsible for data quality and documentation.
- **Data Owners**: Accountable for data security and access controls.
- **Developers**: Ensure compliance with coding standards and best practices.

### Cloud Portal (CP) Management

- **Access**: Access to the Cloud Portal (CP) is limited to a few accounts. All service account and vault account creations must be documented with the governance team per standard policies.
- **Documentation**: Maintain documentation for all updates made to the Cloud Portal by FCP account holders.
- **Project Creation**: New project creation and access management should be handled by the FCP account holder only.

### Identity Management

- **Group Creation**: The creation of new FIM groups must be documented with Data Governance as per standard policies. CDSIDs should not be added via IAM, nor should requests be submitted through IAM. Governance team controls IAM Admin accounts.

### Domain and Dataset Management

- **Creation and Approval**: Any addition or removal of new domains or datasets must be approved in accordance with the Data Governance process.
- **Authorized Views/Datasets**: Must be approved by the Data Governance process.

### Data Integration and Presentation

- **Integration**: The final view shall be accessible exclusively from the transformation zone and remain within the same project. Adhere to DG rules; do not expose tables from landing to presentation.
- **Presentation Layer**: Comprises views only; include tables, routines, etc., in the transformation zone.

### Terraform and Cloud Storage

- **Access Provisioning**: Do not provision access through Terraform code; provisioning occurs via Data Governance.
- **Cloud Storage**: New storage creations must be approved by Data Governance and follow naming standards.

### Data Security

- **Access Controls**: Implemented at the dataset level, inherited by underlying tables and views.
- **Data Masking**: Ensure accurate and concise descriptions for data masking.

### Compliance

- **Regulations**: Ensure compliance with GDPR, CCPA, and other relevant regulations by maintaining clear and concise column names and descriptions. Clearly indicate identifiers like SCAID, ProID, GUID for compliance consideration.

### Data Quality

- **Accuracy**: Data must be accurate and free from errors.
- **Completeness**: All required data must be captured.
- **Timeliness**: Data must be up-to-date.

### AIML Accuracy

Team uses AIML algorithms to classify the columns to individual data domains; For better accuracy,

- **Consistency**: Use consistent column names, descriptions, and datatypes ("String") across all 53 data domains.
- **Sample Descriptions**: Include sample descriptions for all data domains.

## Catalog Standards 📚

### Introduction

- **Purpose**: To establish standards for data governance and cataloging in the Pro360 data warehouse environment.
- **Scope**: These standards apply to all teams and developers working with the Pro360 data warehouse.

### Metadata Management

- **Requirements**: Ensure metadata is populated in all data objects like tables and views. [Metadata Population Guide](./metadata-guide.md).

Text Metadata:

- **Table/View Description**: Detailed description of the table or view.
- **Column Description**: Detailed description of each column, including data types and expected values.

Label Metadata:

- **steward**: CDSID of Data Steward.
- **owner**: CDSID of Table/View Owner.
- **region**: Geographical Region for the Table/View.
- **env**: Environment of the Table/View.
- **data_source**: Data Source.
- **update_frequency**: Table/View Update frequency.
- **team**: Responsible team.
- **contact**: Contact information.

### Naming Standards

- **Consistency**: Use clear, consistent, descriptive naming conventions for datasets, tables, views, and columns in `lowercase`.
  - **Landing Zone**: `_landing` suffix (e.g., charging_domain_landing).
  - **Transformation Zone**: `_transformation` suffix (e.g., charging_domain_transformation).
  - **Presentation Zone**: `_presentation` suffix for views (e.g., charging_domain_presentation).
- **Tables and Views**: Prefix tables with `t_` and views with `v_` for clarity.

### Data Classification

- **Risk Categories**: Ensure clear and concise descriptions for accurate risk group classification by the data classification team.

### Data Documentation

- **Documentation**: Maintain detailed documentation for data domains and tables, including:
  - Product description
  - Data information
  - Source information
  - Update frequency
  - Region availability
  - Contact information
  - Access instructions

### Search and Discovery

- **Data Catalog**: Ensure tables and views are under domain datasets per Datamesh principles to facilitate search and discovery.

### Region and country column

- All tables are required to have standardized region and country columns.
