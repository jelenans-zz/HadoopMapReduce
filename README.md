HadoopMapReduce
===============

Outputs words which appear at least 100 times in the input in the input file “vanrikki-stool.txt”

****************************************************

** $ javac -classpath ** **/home/hadoop/hadoop-1.2.1/hadoop-core-1.2.1.jar:/home/hadoop/hadoop-1.2.1/lib/commons-cli-1.2.jar -d** **top_count_classes TopCount.java**


**$ jar** **-cvf topcount.jar** **-C top_count_classes/ . ** 

added manifest
adding: org/(in = 0) (out= 0)(stored 0%)
adding: org/hwone/(in = 0) (out= 0)(stored 0%)
adding: org/hwone/TopCount$TokenizerMapper.class(in = 1753) (out= 761)(deflated 56%)
adding: org/hwone/TopCount.class(in = 1853) (out= 991)(deflated 46%)
adding: org/hwone/TopCount$IntSumReducer.class(in = 1768) (out= 754)(deflated 57%)

**$ hadoop jar topcount.jar org.hwone.TopCount input** **output**


14/10/27 17:20:00 INFO input.FileInputFormat: Total input paths to process : 1
14/10/27 17:20:00 INFO util.NativeCodeLoader: Loaded the native-hadoop library
14/10/27 17:20:00 WARN snappy.LoadSnappy: Snappy native library not loaded
14/10/27 17:20:02 INFO mapred.JobClient: Running job: job_201410271713_0002
14/10/27 17:20:03 INFO mapred.JobClient:  map 0% reduce 0%
14/10/27 17:20:46 INFO mapred.JobClient:  map 100% reduce 0%
14/10/27 17:21:10 INFO mapred.JobClient:  map 100% reduce 100%
14/10/27 17:21:23 INFO mapred.JobClient: Job complete: job_201410271713_0002
14/10/27 17:21:23 INFO mapred.JobClient: Counters: 29
14/10/27 17:21:23 INFO mapred.JobClient:   Job Counters 
14/10/27 17:21:23 INFO mapred.JobClient:     Launched reduce tasks=1
14/10/27 17:21:23 INFO mapred.JobClient:     SLOTS_MILLIS_MAPS=48533
14/10/27 17:21:23 INFO mapred.JobClient:     Total time spent by all reduces waiting after reserving slots (ms)=0
14/10/27 17:21:23 INFO mapred.JobClient:     Total time spent by all maps waiting after reserving slots (ms)=0
14/10/27 17:21:23 INFO mapred.JobClient:     Launched map tasks=1
14/10/27 17:21:23 INFO mapred.JobClient:     Data-local map tasks=1
14/10/27 17:21:23 INFO mapred.JobClient:     SLOTS_MILLIS_REDUCES=22221
14/10/27 17:21:23 INFO mapred.JobClient:   File Output Format Counters 
14/10/27 17:21:23 INFO mapred.JobClient:     Bytes Written=85
14/10/27 17:21:23 INFO mapred.JobClient:   FileSystemCounters
14/10/27 17:21:23 INFO mapred.JobClient:     FILE_BYTES_READ=113
14/10/27 17:21:23 INFO mapred.JobClient:     HDFS_BYTES_READ=140945
14/10/27 17:21:23 INFO mapred.JobClient:     FILE_BYTES_WRITTEN=111621
14/10/27 17:21:23 INFO mapred.JobClient:     HDFS_BYTES_WRITTEN=85
14/10/27 17:21:23 INFO mapred.JobClient:   File Input Format Counters 
14/10/27 17:21:23 INFO mapred.JobClient:     Bytes Read=140822
14/10/27 17:21:23 INFO mapred.JobClient:   Map-Reduce Framework
14/10/27 17:21:23 INFO mapred.JobClient:     Map output materialized bytes=113
14/10/27 17:21:23 INFO mapred.JobClient:     Map input records=5153
14/10/27 17:21:23 INFO mapred.JobClient:     Reduce shuffle bytes=113
14/10/27 17:21:23 INFO mapred.JobClient:     Spilled Records=22
14/10/27 17:21:23 INFO mapred.JobClient:     Map output bytes=215587
14/10/27 17:21:23 INFO mapred.JobClient:     Total committed heap usage (bytes)=176099328
14/10/27 17:21:23 INFO mapred.JobClient:     CPU time spent (ms)=11300
14/10/27 17:21:23 INFO mapred.JobClient:     Combine input records=18890
14/10/27 17:21:23 INFO mapred.JobClient:     SPLIT_RAW_BYTES=123
14/10/27 17:21:23 INFO mapred.JobClient:     Reduce input records=11
14/10/27 17:21:23 INFO mapred.JobClient:     Reduce input groups=11
14/10/27 17:21:23 INFO mapred.JobClient:     Combine output records=11
14/10/27 17:21:23 INFO mapred.JobClient:     Physical memory (bytes) snapshot=265932800
14/10/27 17:21:23 INFO mapred.JobClient:     Reduce output records=11
14/10/27 17:21:23 INFO mapred.JobClient:     Virtual memory (bytes) snapshot=1502007296
14/10/27 17:21:23 INFO mapred.JobClient:     Map output records=18890

**$ hadoop fs** **-cat output/part-r-00000**

ei	262
hän	340
ja	455
jo	123
kuin	150
kun	164
mut	100
nyt	178
oli	134
on	264
se	154
