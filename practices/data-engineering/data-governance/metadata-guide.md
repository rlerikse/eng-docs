---
sidebar_position: 3
---

# Top 5 Standard Documentation


**Purpose**: As discussed in the PGPL, we are working to improve the top five governance standards and practices. This initiative enhances accountability and fosters a cohesive approach to data management and compliance across all domains in DataMesh.
1. Publish Descriptions and Labels at the Table/View Level
2. Presentation View creation from Transformation layer Only  and removal of and big query IAM binding 
3. Authorization Datasets and Authorization Views
4. Recommendations for Dataset Creation
5. External Table to Data Lake Table 


## 1. Publish Descriptions and Labels at the Table/View Level
<details>
<summary>Details</summary>
   
### Objective: Publish Descriptions and Labels at the Table/View Level Using GenAI Data Descriptor
### Key Goals
- 1. **Consistency**: Adopt a standardized format for all metadata entries to ensure uniformity across tables and views.
- 2. **Clarity**: Craft clear and informative descriptions that enhance understanding and usability for all stakeholders.
- 3. **Completeness**: Ensure all relevant metadata fields are populated for each table and view to provide comprehensive context and facilitate effective data management.


### 1.a Recommended Metadata Fields on Table And Column 

- **Table/View Description**: A detailed description of the table or view.
- **Column Description**: A detailed description of each column, including data types and expected values.

Steps to Utilize GenAI Data Descriptor:  
Step1: Use the Astro link below to trigger the DAG, and click the play button at the top.  

Astro Link : https://deployments.company.com/uninhabited-nebula-1152/airflow/dags/bigquery_table_description_generator/grid?search=bigquery_table_description_generator

Step2: Please provide the Dataset ID and Table ID for the Dev Pro360 project only, and click 'Trigger' to run the DAG.  
      DAG NAME:  bigquery_table_description_generator

![trigger dag](../../../../static/images/dg/trigger_dag.png)

Step3: Upon successful completion of the run, the output of the DAG will be written to BigQuery.  
       DatasetID: common_domain_landing  
       TableID: bq_table_descriptions  

Step4: Please use the 'Table_descriptions' column for table/view-level LLM descriptions, and the 'Table_schema' column for column-level LLM descriptions.  
      Note: The output will be in properly aligned JSON format. If it is not, please use the JSON formatter at https://jsonformatter.org/ to correct it.  


### 1.b Recommended Lables on Table And Views
- **Steward**: Contact information for the table or view can include a Data Steward, SME, or the Data Engineer responsible for the table. Accepted values: CDSID.  
- **Owner**: Owner of the table/view or the supervisor of the Data Engineer, SME responsible for the table/view.Accepted values: CDSID (LL6 and above).  
- **Country**: The geographical region, such as country or region, is included in the table/view.  "True" (If present ) else "False"
- **Env**: Environment in which the Table/View is present. Accepted Values: Prod, Stg, Dev
- **data_source**: Data source from which the table/view data is loaded or obtained. Accepted Value:File, Data Factory, External File Storage, etc, if addtional add date_source1
- **update_frequency**: Table/View Update frequency. Accepted Values : "Daily", "Hourly", "Monthly", "Weekly-Day", "Weekly-MTF", "real-time", "Ad-hoc-Once"  
- **Team**: The team responsible for or owning the table, view, or data product. Accepted Values "Pro360", "Analytics", Pro360-DITO,  Based on roster 
- **Downstream** = According to this table, is there a possibility of creating a downstream table or view if it is not specified as 'None'. Accepted values: "View" "Table" "None"  



### The above can be implemented with [bigquery labels](https://cloud.google.com/bigquery/docs/labels-intro). Keep in mind the [Requirements for Labels](https://cloud.google.com/bigquery/docs/labels-intro#requirements) to avoid early implementation error



### Populate Metadata Using Terraform

Use the following Terraform script template to populate metadata for BigQuery tables and views:

Terraform

```hcl
resource "google_bigquery_table" "base_view_with_schema_tf" {
  dataset_id          = google_bigquery_dataset.data_catalog.dataset_id
  table_id            = "base_view_with_schema_tf"
  schema              = file("base_view_schema.json")
  description         = jsondecode(file("base_view_metadata.json")).table_description
  labels              = jsondecode(file("base_view_metadata.json")).labels
  deletion_protection = "false"

  view {
    query          = "select * from my_dataset.my_table"
    use_legacy_sql = false
  }
}
```

Schema

```json
[
    {
        "name": "a",
        "type": "STRING",
        "mode": "NULLABLE",
        "description": "This is view column a"
    },
    {
        "name": "b",
        "type": "INTEGER",
        "mode": "NULLABLE",
        "description": "This is view column b"
    },
    ...
]
```

Metadata

```json
{
    "table_description": "This is a table description",
    "labels": {
        "steward": "cdsid",
        "owner": "cdsid",
        "region": "eu",
        "env": "sandbox",
        "data_source": "dummy",
        "update_frequency": "1-year"
    }
}
```

### Verify Metadata

After deploying the Terraform script, verify that the metadata has been correctly populated in BigQuery. Check descriptions and labels to ensure they meet the standards.
</details>

## 2.  Presentation View creation from Transformation layer Only  and removal of and big query IAM binding 
<details>
<summary>Details</summary>

### Objective: To develop and implement a streamlined process for creating presentation views exclusively from the transformation layer for our datamesh architecture, while simultaneously removing unnecessary IAM bindings from BigQuery. 

Stage 1  
Develop a final table and data product in the appropriate domain's transformation zone prior to publishing as a final view in the presentation zone
![etl](../../../../static/images/dg/etl.png)


- Ensure that no data products/ tables are created in the landing zone that will be directly exposed to the presentation zone
- Ensure that no data products/tables are created from cross-projects, as views should only pull data from the respective development environment.

![etl1](../../../../static/images/dg/etl1.png)


Stage 2  

Governance team : The Datamesh architecture can manage all BigQuery permissions for tables and views for both end users and data engineers.  

Action Items for Data Engineers  
Step 1: Submit all users, IAM groups, and service accounts added via BigQuery IAM binding code to the governance team for integration into the data mesh and appropriate access provisioning.  

Step 2: Obtain confirmation from the Data Governance team regarding the addition of users, IAM groups, and service accounts to the data mesh.

Step 3: Remove all IAM bindings from Terraform as code.  

Following are some example of IAM Binding that would need removal: 
![trigger dag](../../../../static/images/dg/iam_binding.png)


</details>

## 3.  Authorization Datasets and Authorization Views
<details>
<summary>Details</summary>

### Objective:Governance team is responsible for managing authorization datasets and authorized views that ensures secure and efficient access to data, enabling compliance with governance policies while empowering users to derive insights from the right datasets.

The governance team has integrated all authorized datasets across all domains to enable end customers to access the right data from the presentation zone.
![auth_dataset](../../../../static/images/dg/auth_dataset.png)
Action Items for Data Engineers  
1. **Remove Authorized Datasets**: Please eliminate any authorized datasets in all pro360 projects across development, staging, and production environments.
2. **Remove Authorized Views**: Ensure that any authorized views in all pro360 projects for development, staging, and production are also removed.

![auth_view](../../../../static/images/dg/auth_view.png)


</details>

## 4.  Recommendations for Dataset Creation
<details>
<summary>Details</summary>
   
### Objective: Dataset creation is the responsibility of the data governance team to ensure proper integration into the data mesh.

![domain_dataset](../../../../static/images/dg/domain_dataset.png)

Action Items for Data Engineers  
1. **Approval for Dataset Creation**: Please refrain from creating any additional datasets without prior approval from the data governance team to ensure compliance with established data management policies.
2. **Remove Non-Domain Datasets**: Identify and eliminate all non-domain datasets across all environments (development, staging, and production) to maintain data integrity and alignment with governance standards.


![non_domain_dataset](../../../../static/images/dg/non_domain_dataset.png)



</details>

## 5.  External Table to Data Lake Table 
<details>
<summary>Details</summary>
  
**Overview**: A BigLake table lets you use access delegation to query structured data in Cloud Storage. Access delegation decouples access to the BigLake table from access to the underlying data store.
Usecase – Policy Tags are not supported for plain Bigquery external  tables, instead Biglake tables are recommended.

 ### General Differences Between Bigquery External and Biglake Tables:
BigQuery External Tables
- Purpose: Allow you to query data stored outside of BigQuery, such as in Google Cloud Storage, Bigtable, or Google Drive.
- Access: Requires permissions to both the external table and the external data source.
- Performance: Generally slower compared to querying data stored directly in BigQuery due to the need to access external storage.
- Limitations: Read-only, meaning you cannot modify the data. Data consistency is not guaranteed if the underlying data changes during a query.
  
BigLake Tables
- Purpose: Designed to unify data lakes and warehouses, allowing you to query structured data in external data stores with enhanced security and performance features.
- Access: Uses access delegation, meaning users can query the data without needing direct access to the underlying storage. This allows for more granular security controls, such as row- and column-level access.
- Performance: Offers features like query acceleration through metadata caching, which can improve query performance.
- Flexibility: Supports both BigQuery and open-source engines, providing a consistent and secure way to access data across different storage systems



 ### Create Cloud Resource Connections  
The data governance team has already established the connections; please use the following connections for the BigLake table.  
Dev: us.pro360-dev-biglake-connection
Stage: us.pro360-stg-biglake-connection
prod: us.pro360-prod-biglake-connection

 ### BigQuery BigLake Table Creation
```hcl
resource "google_bigquery_table" "bigquery-biglake-table" {
  dataset_id = "<DATASET_ID>"
  table_id   = "<TABLE_ID>"
  external_data_configuration {
    autodetect    = true
    source_format = "<TABLE_FORMAT>"
    connection_id = "<CONNECTION_ID>"
    source_uris   = [<GCS_FILE_PATH>]
    metadata_cache_mode = "AUTOMATIC"
  }
  max_staleness = "0-0 0 10:0:0"
  deletion_protection = false
}
```
Parameters:  
TABLE_FORMAT: Specify the format of your external table (e.g., CSV, PARQUET).  
GCS_FILE_PATHH: The path to your storage bucket files.  
STALENESS_INTERVAL: The maximum allowable staleness of data in your table.  
CACHE_MODE: Specify the cache mode to be used (e.g., REFRESH, USE_CACHE).
CONNECTION_ID: Use the existing connections creted by the governance team respective to the environment.
</details>



## A. Check out the sample assets in Bigquery

### Go through the [`./terraform`](https://github.company.com/SSUHAGIY/data_catalog_tests/tree/main/terraform) folder for usage example

- organization-d13928e08e83902cd13e1445.data_catalog.base_table_tf (Base Table with column descriptions and metadata)
- organization-d13928e08e83902cd13e1445.data_catalog.base_view_no_schema_tf (View without explicit schema/metadata – no column descriptions)
- organization-d13928e08e83902cd13e1445.data_catalog.base_view_with_schema_tf (View with explicit schema/metadata – includes column descriptions)

## B. References

- [BigQuery Table Refrence](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#Table)
- [BigQuery Table Schema](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#tableschema)
- [Terraform Google Provider - bigquery_table](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/bigquery_table)
- [BigQuery Documentation](https://cloud.google.com/bigquery/docs/introduction)
