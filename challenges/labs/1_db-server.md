
[ec2-user@ip-172-31-22-116 ~]$ hostname
ip-172-31-22-116.us-west-2.compute.internal

sudo cat /etc/cloudera-scm-server/db.properties
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


[ec2-user@ip-172-31-22-116 ~]$ mysql --version
mysql  Ver 15.1 Distrib 5.5.52-MariaDB, for Linux (x86_64) using readline 5.1


+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| cmdatabase         |
| hive               |
| hue                |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| scm                |
| rman               |
+--------------------+
