# Operationalizing-Machine-Learning-With-Azure

<p>We use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. We also create, publish, and consume a pipeline.</p>

<img alt="project overview" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/projectoverview.png">

# Architectural Diagram

<img alt="Architecture Diagram" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/Architecture%20Diagram.png">

# Key Steps

<h3>Deploy model in Azure ML Studio</h3>
<p> We first register a dataset and create an automl run. Once the run is complete, we can deploy the best model. After deployment, the model is registered and Endpoint is available for us to use. We then enable application insights for this EP with help of logs.py script. After that we make use of swagger URI provided in the EP and run both swagger.sh and serve.py so we can see the swagger documentation (It gives us a place to check what paths are available and the expected requests and responses). We run endpoint.py which send request to REST URI and valid JSON response can be seen in the output. Additionally, we use apache benchmark to get the stats of the EP.
  
Register Dataset
<img alt="dataset registered" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/dataset.png">

AutoML Run Complete
<img alt="automl complete" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/automl-completed.png">

AutoML best Model
<img alt="automl best model" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/bestmodel.png">
<img alt="voting Ensemble" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/votingEnsemble.png">

Deployed AutoML best Model
<img alt="project overview" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/automlbestModeldeployed.png">

Enable Application Insights
<img alt="model deployed" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/ApplicationInsightsEnabled.png">

Log outputs - <a target="_blank" href="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/logsOutput.txt" >fulloutput</a>
<img alt="logs.py output" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/logsOuput.png">

Swagger Documentation
<img alt="swagger runs in localhost" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/swaggerRuns.png">
<img alt="methods in swagger documentation" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/swagger2methods.png">
<img alt="health check for the deployed docker image" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/simplehealthtestresponse.png">

Consume EndPoint
endpoint.py output
<img alt="endpoint.py output" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/endpointOutput.png">
benchmark.sh output - <a target="_blank" href="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/benchmark%20output.txt" >fulloutput</a>
<img alt="apache benchmark output" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/benchmarkoutput1.png">
<img alt="apache benchmark stats" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/benchmarkoutput2.png">

<h3>Pipeline</h3>
<p>We create and publish a pipeline containing an automl module and the dataset. The pipeline is invoked using the pipeline REST EP(The last run will have finished status in Screencast)</p>

Create and publish a pipeline
<img alt="pipeline EP is active" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/pipelineEP.png">
<img alt="pipeline steps" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/bankmarketingDatasetWithAutomlModule.png">
<img alt="pipeline overview" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/publishedpipelineoverview.png">

Configure a pipeline with the Python SDK
<img alt="pipeline steps in jupyter notebook" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/stepRunsInJupyterNotebook.png">

Use a REST endpoint to interact with a Pipeline
<img alt="pipeline EP is active" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/pipelineEPrunning.png">
<img alt="pipeline REST EP is running" src="https://github.com/GowthamiWudaru/Operationalizing-Machine-Learning-With-Azure/blob/main/images_for_readme/pipelineRestEPrun.png">

# Future work

<p>As of now, we only have automl run in the pipeline. We can add the deploy best model(if the primary metric is in required range) to the pipeline and also add a simple health check for the REST EP</p>

# Screen Recording

[![Youtube video](https://img.youtube.com/vi/-51AFtFoShg/0.jpg)](https://www.youtube.com/watch?v=-51AFtFoShg)

