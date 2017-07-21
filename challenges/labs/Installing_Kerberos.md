Installing Kerberos on Redhat 7
https://gist.github.com/ashrithr/4767927948eca70845db

sudo yum -y install ntp
sudo ntpdate 0.rhel.pool.ntp.org
sudo systemctl start  ntpd.service
sudo systemctl enable ntpd.service
sudo yum -y install krb5-server krb5-libs

$sudo vim /etc/krb5.conf

# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = ANGELO337.HQ
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 rdns = false
 udp_preference_limit = 1000000
 default_tkt_enctypes = des-cbc-md5 des-cbc-crc des3-cbc-sha1
 default_tgs_enctypes = des-cbc-md5 des-cbc-crc des3-cbc-sha1
 permitted_enctypes = des-cbc-md5 des-cbc-crc des3-cbc-sha1
# default_realm = EXAMPLE.COM
 default_ccache_name = KEYRING:persistent:%{uid}

[realms]
    ANGELO337.HQ = {
        kdc = angelo337.hq:88
        admin_server = angelo337.hq:749
        default_domain = angelo337.hq
    }
# EXAMPLE.COM = {
#  kdc = kerberos.example.com
#  admin_server = kerberos.example.com
# }

[domain_realm]
     .angelo337.hq = ANGELO337.HQ
     angelo337.hq = ANGELO337.HQ
# .example.com = EXAMPLE.COM
# example.com = EXAMPLE.COM
#
[logging]
    kdc = FILE:/var/log/krb5kdc.log
    admin_server = FILE:/var/log/kadmin.log
    default = FILE:/var/log/krb5lib.log
    
    


$sudo vim /var/kerberos/krb5kdc/kdc.conf

default_realm = ANGELO337.HQ
[kdcdefaults]
 v4_mode = nopreauth
 kdc_ports = 0
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
 ANGELO337.HQ = {
  kdc_ports = 88
  kdc_tcp_ports = 88
   admin_keytab = /etc/kadm5.keytab
  database_name = /var/kerberos/krb5kdc/principal
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  key_stash_file = /var/kerberos/krb5kdc/stash
  max_life = 1d
  max_renewable_life = 7d 0h 0m 0s
  master_key_type = des3-hmac-sha1
  #master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes256-cts:normal aes128-cts:normal des3-hmac-sha1:normal arcfour-hmac:normal camellia256-cts:normal camellia128-cts:normal des-hmac-sha1:normal des-cbc-md5:normal des-cbc-crc:normal
  default_principal_flags = +preauth

 }



$ sudo vim /var/kerberos/krb5kdc/kadm5.acl

*/admin@ANGELO337.HQ	*

$ sudo kdb5_util create -r ANGELO337.HQ -s

Loading random data
Initializing database '/var/kerberos/krb5kdc/principal' for realm 'ANGELO337.HQ',
master key name 'K/M@ANGELO337.HQ'
You will be prompted for the database Master Password.
It is important that you NOT FORGET this password.
Enter KDC database master key: 
Re-enter KDC database master key to verify: 
kdb5_util: File exists while creating database '/var/kerberos/krb5kdc/principal'


####
##$ sudo kadmin.local
## Authenticating as principal root/admin@ANGELO337.HQ with password.
## kadmin.local: Can not fetch master key (error: Key table entry not found). while initializing kadmin.local interface
## 
##  just remove all files under 
##  sudo rm /var/kerberos/krb5kdc/*
##  sudo rm /var/kerberos/krb5kdc/*.*
##
## and reissue this command $ sudo kdb5_util create -r ANGELO337.HQ -s

$sudo kadmin.local
kadmin.local:  addprinc root/admin
kadmin.local: addprinc saturn
kadmin.local:  addprinc haley
kadmin.local:  addprinc cloudera-scm
kadmin.local:  ktadd -k /var/kerberos/krb5kdc/kadm5.keytab kadmin/admin
kadmin.local:  ktadd -k /var/kerberos/krb5kdc/kadm5.keytab kadmin/changepw
# https://www.cloudera.com/documentation/enterprise/5-7-x/topics/cm_sg_s3_cm_principal.html#xd_583c10bfdbd326ba--6eed2fb8-14349d04bee--772d
kadmin.local:   addprinc -pw *******! cloudera-scm/admin@ANGELO337.HQ



$ sudo systemctl start krb5kdc.service
$ sudo systemctl start kadmin.service
$ sudo systemctl enable krb5kdc.service
$ sudo systemctl enable kadmin.service
$ sudo kadmin.local
kadmin.local:  addprinc -randkey host/angelo337.hq
kadmin.local:  ktadd host/angelo337.hq
$ sudo yum -y install krb5-workstation

IN ALL HOST INSTALL
sudo yum -y install krb5-workstation krb5-libs
sudo yum -y install openldap-clients
