# Spark in the cloud (with Databricks)

## 1. Getting Started
For this tutorial, we are going to use Databricks - the commercialization of spark
as a cloud based service from some of the original designers. Using Databricks makes
setup very easy, and the free tier is enough to explore Spark functionality.

  1. **Before class** please create a [Databricks Community Edition](https://accounts.cloud.databricks.com/registration.html#signup/community) account.  [This](https://www.youtube.com/watch?v=WaxMj5_SLUI) 3 min video provides a quick overview of Databricks and how to setup up a cluster and notebook.
  2. Databricks makes it easy to create a basic free cluster (6GB of RAM). On the left panel click the *Clusters* icon and then the *Create Cluster* button. Follow the prompts to create a cluster.  In free mode, clusters will become deactivate after 2h of inactivity.
  3. Import our *Spark Tutorial Notebook*.
      1. Copy our spark_tutorial URL found
      [here](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/371142130727624/2056133347430741/653376218961520/latest.html).
      A completed version of this tutorial can can be found in the *1_spark_tutorial.ipynb* file in this repository
      or find the python source
      [here](https://github.com/mbalazin/cse599c-17sp-tutorials/blob/master/spark/py_src/1_spark_tutorial.py).
      1. Click on Workspaces on the left to open up your file explore.
      1. Click on the down arrow next to Workspaces at the top of the column and select Import.
      1. Select the URL radio button and past in the URL.
      1. Click on Import to finish importing our tutorial notebook.
  4. Your notebook should open up but is not attached to a cluster.  In the top left,
     where it says *Detached*, click on the menu dropdown and select the cluster
     you created earlier. (If no cluster is there, you can create one from the dropdown).

## 2. Spark and Databricks Tutorial

  For this section of the tutorial, we will both upload our own csv file to Databricks as well as use common datesets provided by Databricks (a list of which can be [listed like this](https://docs.databricks.com/user-guide/faq/databricks-datasets.html).

  1. Upload mallard.csv dataset from previous tutorials.

      1. If you don't already have a local copy of mallard.csv download it with curl.

          ```
          curl -O https://s3-us-west-2.amazonaws.com/cse599c-sp17/mallard.csv
          ```

      2. On the left panel, click the *Tables* icon to open the Table Explorer.
      3. Click *Create Table*, and select *File* as the data source.
      4. Upload the *mallard.csv* file.
          1. **Important:** once the file is uploaded, a file path such as */FileStore/tables/s3siau3s1492133966611/mallard.csv* will appear under it. Copy this file path into the *mallardFilePath* variable in your notebook.

  Documentation for the pyspark moduals used in this section can be found here:
      1. [RDD API](http://spark.apache.org/docs/2.1.0/api/python/pyspark.html#pyspark.RDD)
      1. [DataFrame API](http://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html#pyspark.sql.DataFrame)
      1. [SQL Functions](http://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html#module-pyspark.sql.functions)

## 3. Spark ML Example

  The spark ML example will use two datasets already in the */databricks-datasets/* file system.

  To start the ML example, import the
  [Spark ML Notebook](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/371142130727624/2056133347430889/653376218961520/latest.html)
  into your Databricks instance.

  A full completed version of this example can be found in the *2_spark_ml.ipynb* file in this repository.
  Or find the python source
  [here](https://github.com/mbalazin/cse599c-17sp-tutorials/blob/master/spark/py_src/2_spark_ml.py).

## 4. Graph processing (GraphX).

  In the graph processing Spark tutorial, we will explore more built-in features of Spark (as provided by Databricks). This section uses the same datasets from the ML example.
  
  First, we need to import GraphFrame library. To do that, follow following steps:

  1. Go to home screen of [community databricks](https://community.cloud.databricks.com) 
  2. Click on *Library* link in the *New* section of home page.
  3. Select *Maven Coordinate* as the source on the create library page.
  4. Click on *Search Spark Packages and Maven Central* button.
  5. A pop-up box will open. Wait for it to load the list of available packages.
  6. Search for *graphframes* once the list is loaded.
  7. Select *0.4.0-spark2.1-s_2.10* from Releases dropbox. Remember that the last three digits represent the version of spark you are running on your cluster. Make sure it matches with what version you are running. You can look for it on *Clusters* page (link in left panel) under active clusters.
  8. Click on *+ Select* to select the package.
  9. Click on *Create Library* to add it your cluster.
      
      1. That is all you need to do to add the package to your cluster.
      

  To start the GraphX example, import the
  [Spark GraphX Notebook](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/371142130727624/2056133347430954/653376218961520/latest.html)
  into your Databricks instance. You can use
  [GraphFrames documentation](https://graphframes.github.io/api/python/graphframes.html#subpackages)
  for programming in python and expand this notebook. If you want to just use scala then use this
  [GraphX documentation](http://spark.apache.org/docs/latest/graphx-programming-guide.html).

  A full completed version of this example can be found in the *3_spark_graphx.ipynb* file in this repository.
  Or find the python source
  [here](https://github.com/mbalazin/cse599c-17sp-tutorials/blob/master/spark/py_src/3_spark_graphx.py).

## 5. Streaming

  To start the streaming example, import the
  [Spark Streaming Notebook](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/371142130727624/2056133347430856/653376218961520/latest.html)
  into your Databricks instance.

  A full completed version of this example can be found in the *4_spark_streaming.ipynb* file in this repository.
  Or find the python source
  [here](https://github.com/mbalazin/cse599c-17sp-tutorials/blob/master/spark/py_src/4_spark_streaming.py).
