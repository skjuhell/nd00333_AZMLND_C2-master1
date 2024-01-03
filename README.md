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

![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/registered_datasets.png)
In the screenshot we see the data set is ready and can be used in the next step for AutoML.

2. AutoML run:

- Configure parameters such as compute cluster, machine learning task type (e.g., classification), exit criterion, etc.
- Train various models on the uploaded dataset using these configurations.

![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/automl.png)

Here, we made one run with and one run without early stopping to reduce computation times, the results are the same however.
Once the training process has finished, we can have a look at the model performance

![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/best_model.png)
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/model_metrics.png)
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/model_metrics2.png)


3. Deploy the best model:

- Select the top-performing model from the AutoML run.
- Deploy it into production using Azure Container Instance (ACI).

Once the model is deployed you can find it in the model section.
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/registered_models.png)


4. Enable logging and Application Insights:

- Configure during the model deployment process or later via a Python script.
- Monitor and track deployed model performance, as well as the number of successful and failed requests.

We first authenticate to be able to access our workspace
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/login.png)

Once this was successful we enable the logging and get
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/logs_enabled.png)
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/aplicaation_insights_enabled.png)


5. Consume Model Endpoints:

- Generate a REST endpoint upon deploying the model.
- Enable interaction with the deployed model by sending requests and receiving predictions.

Further we want to use swagger to interact with our application. Therefore we execute the 'swagger.sh' and 'serve.py' scripts. We adapted the path of the container instance to run port 9000.
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/swagger_api.png)
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/swagger_api2.png)
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/swagger_api3.png)
We can test the setup by running the endpoint.py script which sends a post request for two samples, the model is supposed to predict.
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/endpoints.png)
Since we get back to predictions (yes,no) we know our endpoint is working.


6. Create and Publish a Pipeline:

- Utilize the Azure Python SDK in conjunction with a Jupyter Notebook.
- Require a config.json file in the working directory.
- Automate the entire process of model training and deployment using pipelines.

By iterating through the provided notebook and making adaptions where needed, we create and publish a pipeline for the model. The first screenshot shows the pipeline running.
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/pipeline2.png)
In the lower screenshot you can also see the status of the pipeline marked as active and the REST endpoint.
![](https://github.com/skjuhell/nd00333_AZMLND_C2-master1/blob/main/screenshots/pipeline.png)

 


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
