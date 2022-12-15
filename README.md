# persistenthistoryserver

## Create a GCS Bucket
Create a GCS bucket to Store Event Logs from Ephemeral Clusters. 

## Create a PHS Cluster
Create a Persistent History Server and configure it to access the Spark and MapReduce job history files and YARN aggregation logs from Google Cloud Storage (GCS) bucket. 

Run phs.sh to create a persistent history server.

## Create an Ephemeral Cluster
Create an ephemeral cluster and configure it to write the logs to the GCS bucket that the PHS is accessing. 

Run jobcluster.sh to create an ephemeral cluster that logs events to the GCS bucket.

## Submit a MapReduce Job and a Spark Job to the Ephemeral Cluster

* Submit any MapReduce job to the ephemeral cluster. 

Here is a sample DFSIO MapReduce job for testing:

```
hadoop jar hadoop-*test*.jar TestDFSIO -write|-read -nrFiles <no. of output files> -fileSize <size of one file>
```

* You can access the MapReduce History Server UI by navigating to the Web Interfaces section of the PHS Dataproc cluster. 
  
* Submit any Spark Job to the Ephemeral Cluster. 

Here is a sample Terasort Spark Job that you can use for this test: https://github.com/ehiggs/spark-terasort

* You can access the Spark History Server UI by navigating to the Web Interfaces section of the PHS Dataproc cluster. 




