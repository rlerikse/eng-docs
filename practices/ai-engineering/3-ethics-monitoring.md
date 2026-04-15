# Ethics and Monitoring  

# Model Monitoring

## ML/AI Model Monitoring Best Practices

Monitoring ML model performance is crucial to ensure that the model is performing as expected in the production. 
To be able to successfully productionize a ML system, first we need to understand ML system behavior, keep the intendent behavior above a predefined threshold during products lifetime. This can be achieved by monitoring the model performance and data quality.

It is possible to name 3 components (in addition to infrastructure) that determine the ML system behavior and performance:

1. **Data** (The dataset (or datasets) was used to train the model).

2. **Model** (Output of ML algorithm which was trained on the dataset. It represents the learned patterns in the data).

3. **Code** (The code that is used to train the model, preprocess the data, and make predictions. And it is also includes the required implementation to build ML pipeline. (Implementation of the model, data preprocessing, feature engineering, CI/CD pipelines, system integration, etc.))

### What needs to be monitored?

**Functional Level Monitoring** (More important for Data Scientists, these requires visibility into the data passing into model, metrics and understanding of the model predictions and outputs)

1. Input Data Monitoring (Training dataset and model input dataset)

    - Data quality
    - Data drift (changes in data distribution and statistical properties)

2. Model

    - Model drift (decay of a model's predictive power due to alternations in the real world environment)
    - Versions

3. Outputs

    - Ground truth
    - Prediction drift (If there is a drastic change in the model's predictions)

**Operational Level Monitoring** (More important for DevOps and engineers, ensure the ML system is healthy and operational. Monitoring traditional software metrics)

1. ML System Performance (Memory usage, latency, CPU/GPU usage, etc.)

2. Pipelines

    - Data pipeline
    - Model pipeline

3. Cost


### Best Practices

1. Monitor and check the input data. Perform required transformations before feeding data into ML system for predictions. If input data is not the required data range or type perform the exception handling routine.

    - **Data Quality:** Maintain data integrity, validate data before model input. Check against source data changes (such as schema changes)
    - **Data Drift:** Monitor data distribution between production data and training data. Understand natural drift in real world data and trigger retrain schedule.

2. Model should maintain a performance level above a predefined threshold.  Monitor model performance for every prediction. 

    - **Model Drift:** Monitor model performance over time. If the model performance drops below a predefined threshold, trigger retraining schedule.
    - **Model Versions:** Keep track of model versions. Monitor the performance of each model version.

3. Monitor Model output and compare every output with the required KPIs.

    - **Ground Truth:** Monitor the ground truth data and compare it with model predictions.
    - **Prediction Drift:** Monitor the model predictions. If there is a drastic change in the model's predictions, trigger retraining schedule.

4. Monitor the system performance in hardware level, if there is any unexpected changes in Memory usage, system latency and CPU/GPU use, inspect closely.

5. Always monitor Data Pipeline and Model Pipeline closely.

6. Measure the age of the model, older models tent to perform purely, have a retraining schedule.

7. Monitor the feature generation processes.

## Monitoring  

## Hallucinations & Guardrails  

## AI Ethics  
