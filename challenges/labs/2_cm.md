[root@ip-172-31-22-116 ec2-user]# ls /etc/yum.repos.d

cloudera-manager.repo  redhat-rhui-client-config.repo  rhui-load-balancers.conf
redhat.repo            redhat-rhui.repo

$ sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -u root -p123qweZ! cmdatabase root 123qweZ!  
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
