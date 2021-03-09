# Jupyter notebook with Spark master, 2 workers and a Cassandra database
This repo contains a working environment that allows you to use PySPark in combination with Cassandra and Spark.

## Build a specific version of bitnami-spark
We need to match the Python and Spark version between the spark and jupyter containers.
- `jupyter/pyspark-notebook:29edefbcb06a` is a Jupyter container with Pythin 3.8.8 and Spark 3.0.2
- `bitnamy-spark` will be modified to include Python 3.8.8 (instead of 3.6), it already includes Spark 3.0.2
First build the custom `bitnami-spark` image with:
```sh
cd ./bitnami-docker-spark-custom/3/debian-10
docker build -t custom-bitnami-spark .
```

## Startup the environment
```sh
docker-compose up
```
Wait until Cassandra, Spark-Master, the two Spark-Workers and Jupyter have been started and fire up a notebook.

## Vermont notebook
The vermont notebook and data is based upon: https://levelup.gitconnected.com/using-docker-and-pyspark-134cd4cab867  
Link to dataset: https://data.vermont.gov/Finance/Vermont-Vendor-Payments/786x-sbp3  
Place the csv in `/jupyter/data`.