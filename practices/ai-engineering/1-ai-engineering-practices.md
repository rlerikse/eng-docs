# AI Engineering Practices  

## AI Opinionated Stack

This guide summaries the best practices for AI Engineering. The guide is based on the following AI Opinionated Stack:

> ### Front End/Presentation Layer
- <a href="https://sharepoint.company.com/sites/itoinfraservices/SitePages/GCPLooker-LookerStudio.aspx?web=1">Looker & Looker Studio</a>
- <a href="https://sharepoint.company.com/sites/analytic_tools_and_deployment/SitePages/QlikSense-Quick-Start-and-Best-Practices.aspx">QlikSense</a>

> ### Middleware/Infrastructure Layer
- <a href="https://cloud.google.com/">Google Cloud Platform (GCP)</a>
- <a href="https://portal.company.com/apigee-publish">Apigee</a>: An API Gateway, Google Cloud's native API management platform.
- <a href="https://pages.github.company.com/Mach1ML-2-0/MDK-Docs/remote/Astronomer/">Astronomer</a>: A platform for orchestrating, deploying, and scaling data pipelines. Managed Apache Airflow.
- <a href="https://sharepoint.company.com/:w:/r/sites/SDE/_layouts/15/Doc.aspx?sourcedoc=%7b61406AFB-96E6-49C0-B33A-F7DEADD34179%7d&file=AzureADAuthenticationAndAuthorization.docx&action=default&mobileredirect=true&DefaultItemOpen=1">Azure AD/Entra ID</a>: Authentication and Authorization. Microsoft's cloud-based identity and access management service.
- <a href="https://github.com/organization-innersource/devenablement.caas.container-images">Docker</a>: Pre-configured Docker images.
- <a href="https://www.cloudportal.company.com/gcp/project/ecoboost">Google Cloud Run</a>: A fully managed platform that automatically scales your stateless containers. A fully managed serverless platform to deploy and run containerized applications.
- <a href="https://docs.gcp.company.com/docs/services/security/secretmgr/playbook/">Google Could Secret Manager</a>: A secure and convenient storage system for API keys, passwords, certificates, and other sensitive data.
- <a href="https://github.com/organization-innersource/devenablement.caas.tekton">Tekton</a>: A cloud-native solution for building CI/CD pipelines.
- <a href="https://docs.gcp.company.com/docs/support/terraform/teraform-overview/">Terraform</a>: An open-source infrastructure as code software tool that provides a consistent CLI workflow to manage hundreds of cloud services.
- <a href="https://cloud.google.com/pubsub">Google Cloud Pub/Sub</a>: Asynchronous data messaging services.
- <a href="https://cloud.google.com/functions">Google Cloud Functions</a>: A serverless execution environment for building and connecting cloud services.

> ### Data & Analytics Layer
- <a href="https://sharepoint.company.com/sites/AnalyticsArchitecture/SitePages/BQCoE.aspx">BigQuery</a>: A serverless, highly scalable, and cost-effective multi-cloud data warehouse designed for business agility.
- <a href="https://docs.gcp.company.com/docs/services/ai---ml---analytics/dataflow/">Dataflow</a>: A fully managed stream and batch processing service that minimizes latency and processing time.
- <a href="https://docs.gcp.company.com/docs/services/ai---ml---analytics/dataproc/">DataProc</a>: Dataproc is a fully managed and highly scalable service for running Apache Spark.
- <a href="https://pages.github.company.com/Mach1ML-2-0/MDK-Docs/#what-is-mdk">Mach1ML MLOps Development Kit</a>

> ### Programming Layer
- <a href="https://www.python.org/">Python</a>

> ### AI/ML Layer
- <a href="https://console.cloud.google.com/vertex-ai">Vertex AI</a>

> ### MLOps Layer
- <a href="https://pages.github.company.com/Mach1ML-2-0/MDK-Docs/#what-is-mdk">Mach1ML MLOps Development Kit</a>

> ### Code Assist
- <a href="https://sharepoint.company.com/sites/SDE/SitePages/github-copilot">GitHub Copilot</a>

---

Our AI Opinionated Stack is mainly based on <a href="https://www.python.org/">Python</a> and related libraries. We use Google Cloud Platform (GCP) for our cloud infrastructure. We use Vertex AI for our AI/ML platform. 

Fundamental Python Libraries:
- <a href="https://pandas.pydata.org/">Pandas</a>
- <a href="https://numpy.org/">Numpy</a>
- <a href="https://www.dask.org/">Dask</a>
- <a href="https://matplotlib.org/">Matplotlib</a>

### 1. Data Ingestion and EDA
1. #### Data Extract
2. #### Data Preparation
3. #### Exploratory Data Analysis (EDA)
4. #### Data Transformation
5. #### Feature Engineering

> <details>
> <summary>Tech Stack</summary>
> 
> - <a href="https://cloud.google.com/bigquery">BigQuery</a>
> - <a href="https://www.python.org/">Python </a>(with Vertex AI User Managed Notebooks)
> - GCP Buckets
> - BigQuery Tables
> - (Feature Store - BigQuery Tables)
> 
> </details>

### 2. Modeling
#### AI/ML Modeling

><details>
><summary>Tech Stack</summary>
>- Vertex AI User Managed Notebooks
>
>> Python Libraries: 
>> - <a href="https://scikit-learn.org/stable/">Scikit-learn</a>
>> - <a href="https://www.tensorflow.org/">TensorFlow </a>
>> - Boosting and Bagging algorithms (such as <a href="https://xgboost.readthedocs.io/en/stable/">XGBoost</a>, <a href="https://lightgbm.readthedocs.io/en/stable/">LightGBM</a>, <a href="https://catboost.ai/">CatBoost</a>)
>
>> Deep Learning: 
>> - <a href="https://www.tensorflow.org/">TensorFlow</a>
>> - <a href="https://keras.io/">Keras</a>
>> - <a href="https://pytorch.org/">PyTorch</a>
>
>>LLM and Gen AI: 
>> - Google Gemini Pro and Flash 
>> - Google Gemma
>> - Llama
>> - Claude
>> - Mistral
>> - and GCP Model Garden
>> - <a href="https://www.mach1ml.company.com/llm">EnterpriseLLM</a>
></details>

#### Modeling Best Practices
- Model Validation (Cross validation)
- Model optimization
- hyperparameter tuning
- Model evaluation
- Model explainability (SHAP, LIME) (Best practices for model explainability)


### 3. MLOps
#### Deployment & MLOps

> <details>
> <summary>Tech Stack</summary>
> - <a href="https://pages.github.company.com/Mach1ML-2-0/MDK-Docs/#what-is-mdk">Mach1ML MLOps Development Kit</a>
> </details>


We are implementing all CX Steps, this includes:
- Continuous Integration (CI)
- Continuous Deployment and Delivery (CD)
- Continuous Training (CT)
- Continuous Monitoring (CM)

#### Monitoring & Observability

- Model Monitoring
- Data Drift Monitoring
- Model Drift Monitoring
- Model Performance Monitoring
- Model Explainability Monitoring
- Model Fairness Monitoring
- Model Robustness Monitoring
- Experiment Tracking


## Data First Approach

## Model Development

## Experiment Tracking  

## Model Evaluation  

## Model Deployment/Pipeline  

## Version Control  

## Gen AI  
