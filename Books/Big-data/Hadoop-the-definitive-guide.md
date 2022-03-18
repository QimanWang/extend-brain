#

reliable scalable platform for storage and analysis. Runs on commodity hardware + open source, it's afforable!

### History

started in Nutch, yahoo found interest

### Problem
More and more data, storage increased over time. But read speed has not increased porportionally to storage. 

4.4mb/s in 1990, 100mb/s in 2015. so instead of reading from one machine, spread data acorss and share among datasets.

but more machines means high chance 1 machine will fail and so we need to replicate data / duplicate copy.

And how to handle combing data back together.
Map reduce! has built-in reliability just like HDFS.

query all data that was not possible before.

Map-reduce is batch processing and takes time to return result. 

HBase uses HDFS as underlying storage. good solution for building applications on.

YARN ( cluster resource manager system) enables new processing models. Allows any distributed program not just map reduce to run on data in a hadoop cluster.

Interactive SQL - HIVE

Iterative processing - ML algos

Stream processing - Storm, Spark Streaming, or Samza

Search - solr


| | Traditional RDBMS	|MapReduce |
| ---- | --- |--- |
|Data size	|Gigabytes	|Petabytes|
|Access |	Interactive and batch	|Batch|
|Updates |	Read and write many times | Write once, read many times|
|Transactions	|ACID	|None|
|Structure	|Schema-on-write	|Schema-on-read|
|Integrity	|High	|Low|
|Scaling	|Nonlinear	|Linear|

seek time is improving more slowly than transfer rate. Seeking is the process of moving the disk’s head to a particular place on the disk to read or write data. It characterizes the latency of a disk operation, whereas the transfer rate corresponds to a disk’s bandwidth.
update on rdbms uses b-tree and seek for update, whereas HDFS uses mapreduce + sort/merge to rebuild.

HDFS is schema on read - avoids costly data loading phase, hadoop is just file copy.

grid computing - spread compute on cluster of machine. but is low-level and network is bottleneck

hadoop tries to colocate data with the computer nodes, data locality. Shared nothing architecture, so failed jobs can easily reschedule on healthy nodes.

