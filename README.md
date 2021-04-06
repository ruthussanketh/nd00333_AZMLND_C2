# Operationalising Machine Learning

## Overview
This project consists of two parts. The aim of the first part is to configure, deploy and consume an ML production model using Azure. The aim of the second part is to create, publish and consume a pipeline. The Bank Marketing dataset is used to train the models in the first and the second parts. The model and the pipeline will both be deployed to their REST endpoints. After deployment, other systems can interact with the deployed services by sending HTTP requests to their endpoints. 

## Architectural Diagram

![](images/architecture.PNG)

Part 1 - Azure ML Studio
1. Checking if the dataset is registered in the Azure workspace for the Automated ML Experiment
2. Using Automated ML to determine the best model (VotingEnsemble)
3. Deploying the best model so that it can be consumed
4. Consuming the REST endpoint to interact with the trained model

Part 2 - SDK
1. Using the same dataset registered in Azure workspace for Part 1
2. Creating an ML pipeline with AutoML step and running the experiment
3. Publishing the pipeline so that it can be consumed
4. Consuming the REST endpoint to interact with the pipeline

## Main Steps

1.	Authentication
2.	Automated ML Experiment
3.	Deployment of the Best Model
4.	Enabling the Application 
5.	Swagger Documentation
6.	Consuming Model Endpoints
7.	Creating and Publishing a Pipeline
8.	Documentation

## Step 1: Authentication 
Authentication is required to ensure uninterrupted flow of operations. This step was not necessary for the lab workspace provided by Udacity.

## Step 2: Automated ML Experiment 
The experiment iteratively produces different ML models and determines the best one, which in this case was found to the VotingEnsemble model.

Step 2.1 The Registered Bankmarketing Dataset
![](images/registered_dataset.PNG)

Step 2.2 The Completed Experiment
![](images/completed_experiment.PNG)

Step 2.3 The Best Model
![](images/best_model.PNG)

## Step 3: Deployment of the Best Model
Now we published the model so that it can be consumed by others.

## Step 4: Enabling Application Insights and Logging 
Once the model is deployed Application Insights was enabled and logs were retireved locally. Application Insightsis is an Azure service that provides key performance information about the deployed service.

Step 4.1 Enabled Applications Insights
![](images/application_insights_enabled.PNG)

Step 4.2 Running the logs.py Script
![](images/logs_py.PNG)

## Step 5: Swagger Documentation
Swagger makes documentation easier by describing the API, what requests it accepts, inputs and endpoints  

Step 5.1 Swagger Running on Localhost
![](images/swagger.PNG)

Step 5.2 Swagger - HTTP API Methods and Responses
![](images/swagger1.PNG)

Step 5.3 Swagger - HTTP API Methods and Responses (cont'd)
![](images/swagger2.PNG)

Step 5.4 Swagger - HTTP API Methods and Responses (cont'd)
![](images/swagger3.PNG)

## Step 6: Consuming Model Endpoints
The REST endpoint is consumed to interact with the trained model via requests.

Step 6.1 endpoint.py Producing JSON Output
![](images/endpoint_output.PNG)

## Step 7: Creating and Publishing a Pipeline
An ML pipeline was created with AutoML, the experiment was run and the pipeline published. Once the pipeline is published, others can consume the REST endpoint to rerun the pipeline from any HTTP library on any platform.

Step 7.1 Creation of the Pipeline
![](images/pipeline_created.PNG)

Step 7.2 Published Pipeline under the Pipeline Endpoint Tab
![](images/pipeline_published.PNG)

Step 7.3 The Bankmarketing Dataset with the AutoML Module
![](images/bankmarketing_automl.PNG)

Step 7.4 The Published Pipeline Overview Including Active Satatus and REST Endpoint 
![](images/published_pipeline_overview.PNG)

Step 7.5 RunDetails Widget Showing Step Runs 
![](images/run_details.PNG)

Step 7.6 Scheduled and Running Pipeline 
![](images/running_pipeline.PNG)

## Step 8: Documentation 
A screencast was made showing the entire process of the working ML application, which can be accessed here.

## Future Works
For better predictive ability of a model, some improvements that can be made are  - 
1. The class imbalance that was detected during the model training can be mitigated by experimenting with other metrics suitable for the problem such as F1 score.
2. Models used during the Automated ML Experiment can be managed to allow only the ones we think will be effective. 
3. k-fold cross validation can be performed so that a model gets a better generalisation ability. 
4. Feature selection and feature engineering can, too, improve the performance. 
