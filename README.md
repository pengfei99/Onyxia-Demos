# Onyxia-Demos

In this repo, we provide some ready to run code that uses services in the service catalog of the [datalab](https://datalab.sspcloud.fr/home)

You can use it to illustrate the basic functionalities of the datalab

## 1 Basic data analytic services

### 1.1 R studio service

The R folder contains:

- [read_s3_data.Rmd](R/read_s3_data.Rmd): A notebook that reads data from minio (datalab default object storage), and calculate some basic stats

### 1.2 Jupyter service

The Python folder contains:

- [read_s3_data.ipynb](Python/read_s3_data.ipynb): A notebook that reads data from minio (datalab default object storage), and calculate some basic stats. This notebook uses basic python lib such as pandas, s3fs.

## 2. Advance data analytic services

When data volume become important, you can't use the traditional tools to analyze them. Datalab provides services to treat them (e.g. Spark, trino, Pinot, etc. )

### 2.1 Spark for big data analytics

#### Spark on cpu

The Spark folder contains:

- [spark_data_curation.ipynb](Spark/spark_data_curation.ipynb): A notebook that illustrate a data curation workflow. If **hive-metastore** is enabled, the curated table will be referenced automatically in the [data catalog](https://atlas.lab.sspcloud.fr/index.html#!/search). 

#### Spark on gpu 

To run spark on gpu, the docker image requires special dependencies. So we need to launch a special service called **Rapidsai**. The work directory is **rapidsai/work**, You need to clone your notebook there. 

- [spark_on_gpu.ipynb](Spark/spark_on_gpu.ipynb): A notebook that illustrate how to use gpu to do calculations. 

Note the jupyter service in datalab proivdes a **spark ui**, but it's deactivate by default. You need to activate when you launched the service. 

### 3 Data Engineering

#### 3.1 Workflow automation

Onyxia provides **argo workflow** as our workflow automation service. If you have complexe or repeatable workflow, we recommand you strongly to use this service.
 
In the `argo_workflow` folder, you can find a [script](argo_workflow/argo_client_install.sh) to install the argo-workflow client

You can find a [argo-workflow spec](argo_workflow/pokemon_data_pipeline.yaml) that automate a etl data pipeline which reads data from a file, then clean it and save it to s3 and/or database.  

## 4. Machine Learning

### 4.1 Tensorflow and pytorch

Onyxia provides a **Tensorflow** service (jupyter with tensorflow related libraries). We can train model both with `cpu` and `gpu`.

This [notebook](TensorFlow/tensorflow_gpu.ipynb) uses gpu to train a NN to do image classification

### 4.2 MLOPs

This [notebook](https://github.com/pengfei99/MLOPS/blob/main/mlops_tutorial.ipynb) shows how to do MLOPS with the services which are provided by Onyxia.

## 5. BI
### 5.1 Superset
### 5.2 Trino

## 6. Hosting custom applications

Onyxia also allow users to deploy their own applications. 



