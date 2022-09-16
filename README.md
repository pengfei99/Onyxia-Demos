# Onyxia-Demos

In this repo, we provide some ready to run code that uses services in the service catalog of the [datalab](https://datalab.sspcloud.fr/home)

You can use it to illustrate the basic functionalities of the datalab

## 1 Basic data analytic services

### 1.1 R studio service

The R folder contains:

- read_s3_data.Rmd: A notebook that reads data from minio (datalab default object storage), and calculate some basic stats

### 1.2 Jupyter service

The Python folder contains:

- read_s3_data.ipynb: A notebook that reads data from minio (datalab default object storage), and calculate some basic stats. This notebook uses basic python lib such as pandas, s3fs.

## 2. Advance data analytic services

When data volume become important, you can't use the traditional tools to analyze them. Datalab provides services to treat them (e.g. Spark, trino, Pinot, etc. )

### 2.1 Spark for big data analytics
 
The Spark folder contains:

- spark_data_curation.ipynb: A notebook that illustrate a data curation workflow. If **hive-metastore** is enabled, the curated table will be referenced automatically in the [data catalog](https://atlas.lab.sspcloud.fr/index.html#!/search)
