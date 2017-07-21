
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


time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -Dmapred.map.tasks.speculative.execution=false -Ddfs.block.size=32M 51200000 tgen512m

real	1m24.723s
user	0m5.198s
sys	0m0.247s

$ hdfs dfs -ls /user/saturn/tgen512m
Found 9 items
-rw-r--r--   3 saturn supergroup          0 2017-07-20 20:24 /user/saturn/tgen512m/_SUCCESS
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00000
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00001
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00002
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00003
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00004
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00005
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00006
-rw-r--r--   3 saturn supergroup  640000000 2017-07-20 20:24 /user/saturn/tgen512m/part-m-00007

$ hdfs fsck -blocks /user/saturn
Connecting to namenode via http://ip-172-31-16-27.us-west-2.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.16.27 for path /user/saturn at Thu Jul 20 20:38:45 EDT 2017
.........Status: HEALTHY
 Total size:	5120000000 B
 Total dirs:	3
 Total files:	9
 Total symlinks:		0
 Total blocks (validated):	160 (avg. block size 32000000 B)
 Minimally replicated blocks:	160 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Thu Jul 20 20:38:45 EDT 2017 in 7 milliseconds


The filesystem under path '/user/saturn' is HEALTHY

$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-16-27.us-west-2.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.16.27 for path /user/saturn at Thu Jul 20 20:38:24 EDT 2017
.........Status: HEALTHY
 Total size:	5120000000 B
 Total dirs:	3
 Total files:	9
 Total symlinks:		0
 Total blocks (validated):	160 (avg. block size 32000000 B)
 Minimally replicated blocks:	160 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Thu Jul 20 20:38:24 EDT 2017 in 13 milliseconds


The filesystem under path '/user/saturn' is HEALTHY
