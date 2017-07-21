 
 hdfs dfs -ls /user
Found 5 items
drwxrwxrwx   - mapred hadoop          0 2017-07-20 19:17 /user/history
drwxrwxr-t   - hive   hive            0 2017-07-20 19:18 /user/hive
drwxrwxr-x   - hue    hue             0 2017-07-20 19:19 /user/hue
drwxrwxr-x   - oozie  oozie           0 2017-07-20 19:19 /user/oozie
drwxr-x--x   - spark  spark           0 2017-07-20 19:18 /user/spark

Create user directories in HDFS

sudo su
su hdfs

hdfs dfs -mkdir /user/saturn
hdfs dfs -mkdir /user/haley

hdfs dfs -ls /user
Found 9 items
drwxr-xr-x   - admin  admin               0 2017-07-20 19:51 /user/admin
drwxr-xr-x   - hdfs   supergroup          0 2017-07-20 20:14 /user/haley
drwxr-xr-x   - hdfs   supergroup          0 2017-07-20 19:43 /user/hdfs
drwxrwxrwx   - mapred hadoop              0 2017-07-20 19:17 /user/history
drwxrwxr-t   - hive   hive                0 2017-07-20 19:18 /user/hive
drwxrwxr-x   - hue    hue                 0 2017-07-20 19:19 /user/hue
drwxrwxr-x   - oozie  oozie               0 2017-07-20 19:19 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2017-07-20 20:14 /user/saturn
drwxr-x--x   - spark  spark               0 2017-07-20 19:18 /user/spark


output from the CM API call 
http://54.69.115.200:7180/api/v14/hosts
{
  "items" : [ {
    "hostId" : "99d5ffe1-44a8-4f84-bddd-5c8ce42daef5",
    "ipAddress" : "172.31.16.27",
    "hostname" : "ip-172-31-16-27.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-26-41.us-west-2.compute.internal:7180/cmf/hostRedirect/99d5ffe1-44a8-4f84-bddd-5c8ce42daef5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31185264640
  }, {
    "hostId" : "38976b4e-e576-43ac-830b-e03f89573093",
    "ipAddress" : "172.31.19.5",
    "hostname" : "ip-172-31-19-5.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-26-41.us-west-2.compute.internal:7180/cmf/hostRedirect/38976b4e-e576-43ac-830b-e03f89573093",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31185264640
  }, {
    "hostId" : "203bed3e-e101-4e0b-b490-a59d4158ce06",
    "ipAddress" : "172.31.21.153",
    "hostname" : "ip-172-31-21-153.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-26-41.us-west-2.compute.internal:7180/cmf/hostRedirect/203bed3e-e101-4e0b-b490-a59d4158ce06",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31185264640
  }, {
    "hostId" : "538054ec-12c6-43f0-a466-5d9d06e54eda",
    "ipAddress" : "172.31.22.135",
    "hostname" : "ip-172-31-22-135.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-26-41.us-west-2.compute.internal:7180/cmf/hostRedirect/538054ec-12c6-43f0-a466-5d9d06e54eda",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31185264640
  }, {
    "hostId" : "ba994719-a532-4524-aa47-77ebc9f8edec",
    "ipAddress" : "172.31.37.159",
    "hostname" : "ip-172-31-37-159.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-26-41.us-west-2.compute.internal:7180/cmf/hostRedirect/ba994719-a532-4524-aa47-77ebc9f8edec",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331913728
  } ]
}

output from the CM API call 
http://54.69.115.200:7180/api/v8/clusters/angelo337/services
{
  "items" : [ ]
}
