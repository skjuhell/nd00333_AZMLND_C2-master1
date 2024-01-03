*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.


# Operationalizing Machine Learning

 I executed a comprehensive machine learning project on Microsoft Azure. Employing the Bank Marketing Dataset, I trained a model with Azure Machine Learning Studio's AutoML feature. After deploying it through Azure Container Instance (ACI), I consumed the model via REST endpoints. Additionally, I automated the entire workflow by creating, publishing, and consuming a pipeline.

## Architectural Diagram
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/workflow.png)

## Key Steps
The diagram above illustrates the sequential flow of operations from initiation to completion. Let's delve into each step:

1.Register the Dataset:

- Upload the dataset into Azure Machine Learning Studio.
- Accomplished either by providing a URL or uploading directly from a local folder.

2. AutoML run:

- Configure parameters such as compute cluster, machine learning task type (e.g., classification), exit criterion, etc.
- Train various models on the uploaded dataset using these configurations.

3. Deploy the best model:

- Select the top-performing model from the AutoML run.
- Deploy it into production using Azure Container Instance (ACI) or Azure Kubernetes Service (AKS).

4. Enable logging and Application Insights:

- Configure during the model deployment process or later via a Python script.
- Monitor and track deployed model performance, as well as the number of successful and failed requests.

5. Consume Model Endpoints:

- Generate a REST endpoint upon deploying the model.
- Enable interaction with the deployed model by sending requests and receiving predictions.

6. Create and Publish a Pipeline:

- Utilize the Azure Python SDK in conjunction with a Jupyter Notebook.
- Require a config.json file in the working directory.
- Automate the entire process of model training and deployment using pipelines.

*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
