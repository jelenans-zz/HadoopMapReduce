HadoopMapReduce
===============

Outputs words which appear at least 100 times in the input in the input file “vanrikki-stool.txt”

****************************************************
$ hadoop namenode -format

****************************************************

14/10/27 15:19:38 INFO namenode.NameNode: STARTUP_MSG: 
/************************************************************
STARTUP_MSG: Starting NameNode
STARTUP_MSG:   host = ubuntu/127.0.1.1
STARTUP_MSG:   args = [format]
STARTUP_MSG:   version = 1.2.1
STARTUP_MSG:   build = https://svn.apache.org/repos/asf/hadoop/common/branches/branch-1.2 -r 1503152; compiled by 'mattf' on Mon Jul 22 15:23:09 PDT 2013
STARTUP_MSG:   java = 1.7.0_65
************************************************************/
14/10/27 15:19:39 INFO util.GSet: Computing capacity for map BlocksMap
14/10/27 15:19:39 INFO util.GSet: VM type       = 64-bit
14/10/27 15:19:39 INFO util.GSet: 2.0% max memory = 1013645312
14/10/27 15:19:39 INFO util.GSet: capacity      = 2^21 = 2097152 entries
14/10/27 15:19:39 INFO util.GSet: recommended=2097152, actual=2097152
14/10/27 15:19:41 INFO namenode.FSNamesystem: fsOwner=hadoop
14/10/27 15:19:42 INFO namenode.FSNamesystem: supergroup=supergroup
14/10/27 15:19:42 INFO namenode.FSNamesystem: isPermissionEnabled=true
14/10/27 15:19:42 INFO namenode.FSNamesystem: dfs.block.invalidate.limit=100
14/10/27 15:19:42 INFO namenode.FSNamesystem: isAccessTokenEnabled=false accessKeyUpdateInterval=0 min(s), accessTokenLifetime=0 min(s)
14/10/27 15:19:42 INFO namenode.FSEditLog: dfs.namenode.edits.toleration.length = 0
14/10/27 15:19:42 INFO namenode.NameNode: Caching file names occuring more than 10 times 
14/10/27 15:19:43 INFO common.Storage: Image file /tmp/hadoop-hadoop/dfs/name/current/fsimage of size 112 bytes saved in 0 seconds.
14/10/27 15:19:43 INFO namenode.FSEditLog: closing edit log: position=4, editlog=/tmp/hadoop-hadoop/dfs/name/current/edits
14/10/27 15:19:43 INFO namenode.FSEditLog: close success: truncate to 4, editlog=/tmp/hadoop-hadoop/dfs/name/current/edits
14/10/27 15:19:43 INFO common.Storage: Storage directory /tmp/hadoop-hadoop/dfs/name has been successfully formatted.
14/10/27 15:19:43 INFO namenode.NameNode: SHUTDOWN_MSG: 
/************************************************************
SHUTDOWN_MSG: Shutting down NameNode at ubuntu/127.0.1.1
************************************************************/

****************************************************
$ start-all.sh

****************************************************

starting namenode, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-namenode-ubuntu.out
localhost: starting datanode, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-datanode-ubuntu.out
localhost: starting secondarynamenode, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-secondarynamenode-ubuntu.out
starting jobtracker, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-jobtracker-ubuntu.out
localhost: starting tasktracker, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-tasktracker-ubuntu.out
starting namenode, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-namenode-ubuntu.out
localhost: starting datanode, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-datanode-ubuntu.out
localhost: starting secondarynamenode, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-secondarynamenode-ubuntu.out
starting jobtracker, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-jobtracker-ubuntu.out
localhost: starting tasktracker, logging to /home/hadoop/hadoop-1.2.1/libexec/../logs/hadoop-hadoop-tasktracker-ubuntu.out

****************************************************
$ hadoop dfsadmin -safemode leave

Safe mode is OFF


****************************************************
$ hadoop fs -mkdir input

****************************************************

$ hadoop fs -put vanrikki-stool.txt input



****************************************************

$ javac -classpath /home/hadoop/hadoop-1.2.1/hadoop-core-1.2.1.jar:/home/hadoop/hadoop-1.2.1/lib/commons-cli-1.2.jar -d top_count_classes TopCount.java 

****************************************************

$ jar -cvf topcount.jar -C top_count_classes/ . 

****************************************************

added manifest
adding: org/(in = 0) (out= 0)(stored 0%)
adding: org/hwone/(in = 0) (out= 0)(stored 0%)
adding: org/hwone/TopCount$TokenizerMapper.class(in = 1753) (out= 761)(deflated 56%)
adding: org/hwone/TopCount.class(in = 1853) (out= 991)(deflated 46%)
adding: org/hwone/TopCount$IntSumReducer.class(in = 1768) (out= 754)(deflated 57%)

****************************************************

$ hadoop jar topcount.jar org.hwone.TopCount input output 

****************************************************

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

****************************************************


$ hadoop fs -cat output/part-r-00000 

****************************************************

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
