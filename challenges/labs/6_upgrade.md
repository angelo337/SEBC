cd /etc/yum.repo.d
cd /etc/yum.repos.d
vim cloudera-manager.repo
sudo yum 
sudo yum clean all
sudo yum update
service cloudera-scm-server stop
service cloudera-scm-agent stop
sudo yum upgrade cloudera-manager-server cloudera-manger-daemons cloudera-manager-agent
sudo yum upgrade cloudera-manager-server cloudera-manager-daemons cloudera-manager-agent
service cloudera-scm-server start
service cloudera-scm-agent start

