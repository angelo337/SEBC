cloud provider : AWS

IP address                 DNS name   
34.209.1.17                ec2-34-209-1-17.us-west-2.compute.amazonaws.com


cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.3 (Maipo)

df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       80G  3.9G   77G   5% /

yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                           repo name                                                         status
rhui-REGION-client-config-server-7/x86_64         Red Hat Update Infrastructure 2.0 Client Configuration Server 7        6
rhui-REGION-rhel-server-releases/7Server/x86_64   Red Hat Enterprise Linux Server 7 (RPMs)                          14,598
rhui-REGION-rhel-server-rh-common/7Server/x86_64  Red Hat Enterprise Linux Server 7 RH Common (RPMs)                   228
repolist: 14,832

List the /etc/passwd 
haley:x:2900:2900::/home/haley:/bin/bash
saturn:x:2800:2800::/home/saturn:/bin/bash

List the /etc/group
comets:x:1001:haley
planets:x:1002:saturn
