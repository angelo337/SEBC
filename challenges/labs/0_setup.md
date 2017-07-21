cloud provider : AWS
ec2-34-212-79-201.us-west-2.compute.amazonaws.com   34.212.79.201
ec2-34-213-23-76.us-west-2.compute.amazonaws.com  	34.213.23.76
ec2-34-213-53-11.us-west-2.compute.amazonaws.com	34.213.53.11
ec2-52-25-79-25.us-west-2.compute.amazonaws.com		52.25.79.25
ec2-52-26-19-216.us-west-2.compute.amazonaws.com	52.26.19.216
ec2-52-41-245-153.us-west-2.compute.amazonaws.com	52.41.245.153


cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.3 (Maipo)
[ec2-user@ip-172-31-25-248 ~]$ sudo df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       80G  1.4G   79G   2% /
devtmpfs         15G     0   15G   0% /dev
tmpfs            15G     0   15G   0% /dev/shm
tmpfs            15G   17M   15G   1% /run
tmpfs            15G     0   15G   0% /sys/fs/cgroup
tmpfs           3.0G     0  3.0G   0% /run/user/1000
[ec2-user@ip-172-31-25-248 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                                      status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastructure 2.0 Client Confi      6
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux Server 7 (RPMs)       14,598
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux Server 7 RH Common (R    228
repolist: 14,832

List the /etc/passwd 
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash


List the /etc/group
comets:x:1001:haley
planets:x:1002:saturn





