$ sudo cat /etc/cloudera-scm-server/db.properties


# Copyright (c) 2012 Cloudera, Inc. All rights reserved.
#
# This file describes the database connection.
#

# The database type
# Currently 'mysql', 'postgresql' and 'oracle' are valid databases.
com.cloudera.cmf.db.type=mysql

# The database host
# If a non standard port is needed, use 'hostname:port'
#com.cloudera.cmf.db.host=localhost

# The database name
#com.cloudera.cmf.db.name=cmf

# The database user
#com.cloudera.cmf.db.user=cmf

# The database user's password
#com.cloudera.cmf.db.password=

# The db setup type
# By default, it is set to INIT
# If scm-server uses Embedded DB then it is set to EMBEDDED
# If scm-server uses External DB then it is set to EXTERNAL
com.cloudera.cmf.db.setupType=INIT

head -n1 /var/log/cloudera-scm-server/cloudera-scm-server.log 
2017-07-21 10:32:59,488 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.11.1 (#9 built by jenkins on 20170525-1411 git: 8adcfb8545cb0a35f590717b2626a9ea04948dae)
cat  /var/log/cloudera-scm-server/cloudera-scm-server.log |grep "Started Jetty server"
2017-07-21 10:33:57,053 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty serve.


$ sudo cat /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri Jul 21 10:28:48 EDT 2017
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=localhost
com.cloudera.cmf.db.name=cmdatabase
com.cloudera.cmf.db.user=root
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=123!
