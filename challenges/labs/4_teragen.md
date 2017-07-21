
hdfs dfs -chown saturn /user/saturn
hdfs dfs -chown haley /user/haley


$ hdfs dfs -ls /user
Found 9 items
drwxr-xr-x   - admin  admin               0 2017-07-20 19:51 /user/admin
drwxr-xr-x   - haley  supergroup          0 2017-07-20 20:14 /user/haley
drwxr-xr-x   - hdfs   supergroup          0 2017-07-20 19:43 /user/hdfs
drwxrwxrwx   - mapred hadoop              0 2017-07-20 19:17 /user/history
drwxrwxr-t   - hive   hive                0 2017-07-20 19:18 /user/hive
drwxrwxr-x   - hue    hue                 0 2017-07-20 19:19 /user/hue
drwxrwxr-x   - oozie  oozie               0 2017-07-20 19:19 /user/oozie
drwxr-xr-x   - saturn supergroup          0 2017-07-20 20:23 /user/saturn
drwxr-x--x   - spark  spark               0 2017-07-20 19:18 /user/spark



time sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapred.map.tasks=12  -Ddfs.blocksize=33554432  51200000  /user/saturn/tgen5

17/07/21 12:18:45 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-156.us-west-2.compute.internal/172.31.18.156:8032
17/07/21 12:18:46 INFO terasort.TeraGen: Generating 51200000 using 12
17/07/21 12:18:46 INFO mapreduce.JobSubmitter: number of splits:12
17/07/21 12:18:46 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/07/21 12:18:46 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1500649139480_0006
17/07/21 12:18:46 INFO impl.YarnClientImpl: Submitted application application_1500649139480_0006
17/07/21 12:18:46 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-156.us-west-2.compute.internal:8088/proxy/application_1500649139480_0006/
17/07/21 12:18:46 INFO mapreduce.Job: Running job: job_1500649139480_0006
17/07/21 12:18:53 INFO mapreduce.Job: Job job_1500649139480_0006 running in uber mode : false
17/07/21 12:18:53 INFO mapreduce.Job:  map 0% reduce 0%
17/07/21 12:19:11 INFO mapreduce.Job:  map 38% reduce 0%
17/07/21 12:19:12 INFO mapreduce.Job:  map 58% reduce 0%
17/07/21 12:19:14 INFO mapreduce.Job:  map 59% reduce 0%
17/07/21 12:19:15 INFO mapreduce.Job:  map 61% reduce 0%
17/07/21 12:19:16 INFO mapreduce.Job:  map 64% reduce 0%
17/07/21 12:19:17 INFO mapreduce.Job:  map 75% reduce 0%
17/07/21 12:19:18 INFO mapreduce.Job:  map 83% reduce 0%
17/07/21 12:19:23 INFO mapreduce.Job:  map 85% reduce 0%
17/07/21 12:19:24 INFO mapreduce.Job:  map 88% reduce 0%
17/07/21 12:19:29 INFO mapreduce.Job:  map 89% reduce 0%
17/07/21 12:19:30 INFO mapreduce.Job:  map 93% reduce 0%
17/07/21 12:19:37 INFO mapreduce.Job:  map 98% reduce 0%
17/07/21 12:19:38 INFO mapreduce.Job:  map 99% reduce 0%
17/07/21 12:19:39 INFO mapreduce.Job:  map 100% reduce 0%
17/07/21 12:19:39 INFO mapreduce.Job: Job job_1500649139480_0006 completed successfully
17/07/21 12:19:39 INFO mapreduce.Job: Counters: 33
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1531598
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1025
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters 
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=384441
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=384441
		Total vcore-milliseconds taken by all map tasks=384441
		Total megabyte-milliseconds taken by all map tasks=393667584
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1619
		CPU time spent (ms)=118210
		Physical memory (bytes) snapshot=4319223808
		Virtual memory (bytes) snapshot=19271147520
		Total committed heap usage (bytes)=6597115904
		Peak Map Physical memory (bytes)=382636032
		Peak Map Virtual memory (bytes)=1617891328
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=109963291816450258
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=5120000000

real	0m55.442s
user	0m4.836s
sys	0m0.237s


$ sudo hdfs dfs -ls /user/saturn/tgen5
Found 13 items
-rw-r--r--   3 hdfs supergroup          0 2017-07-21 12:19 /user/saturn/tgen5/_SUCCESS
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00000
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00001
-rw-r--r--   3 hdfs supergroup  426666600 2017-07-21 12:19 /user/saturn/tgen5/part-m-00002
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00003
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00004
-rw-r--r--   3 hdfs supergroup  426666600 2017-07-21 12:19 /user/saturn/tgen5/part-m-00005
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00006
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00007
-rw-r--r--   3 hdfs supergroup  426666600 2017-07-21 12:19 /user/saturn/tgen5/part-m-00008
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00009
-rw-r--r--   3 hdfs supergroup  426666700 2017-07-21 12:19 /user/saturn/tgen5/part-m-00010
-rw-r--r--   3 hdfs supergroup  426666600 2017-07-21 12:19 /user/saturn/tgen5/part-m-00011



hdfs fsck -blocks /user/saturn

Connecting to namenode via http://ip-172-31-18-156.us-west-2.compute.internal:50070
FSCK started by ec2-user (auth:SIMPLE) from /172.31.25.116 for path /user/saturn at Fri Jul 21 12:21:48 EDT 2017
..................................Status: HEALTHY
 Total size:	25600010000 B
 Total dirs:	7
 Total files:	34
 Total symlinks:		0
 Total blocks (validated):	780 (avg. block size 32820525 B)
 Minimally replicated blocks:	780 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		5
 Number of racks:		1
FSCK ended at Fri Jul 21 12:21:48 EDT 2017 in 31 milliseconds


The filesystem under path '/user/saturn' is HEALTHY



