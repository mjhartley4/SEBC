#Cloud Provider: 
Amazon Web Services

IP Addresses and Names:
```
Clouderann - 13.55.193.92 (Public) 172.31.3.136 (Private)
Clouderann2 - 52.64.138.94
Clouderadn - 52.63.242.102
clouderadn2 - 52.63.219.22
clouderadn3 - 52.64.2.92
```
Linux Operating System:
```
Red Hat Enterprise Linux 7.3#
```
#Demonstrate Disk Capacity on Clouderann:#
```
[ec2-user@ip-172-31-3-136 ~]$ df
Filesystem     1K-blocks    Used Available Use% Mounted on
/dev/xvda2      52416492 1002836  51413656   2% /
devtmpfs         7598116       0   7598116   0% /dev
tmpfs            7486292       0   7486292   0% /dev/shm
tmpfs            7486292   16636   7469656   1% /run
tmpfs            7486292       0   7486292   0% /sys/fs/cgroup
tmpfs            1497260       0   1497260   0% /run/user/1000
```
#Yum Repolist Enabled Output#:
```
[ec2-user@ip-172-31-3-136 ~]$ yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Could not contact CDS load balancer rhui2-cds01.ap-southeast-2.aws.ce.redhat.com, trying others.
Could not contact any CDS load balancers: rhui2-cds01.ap-southeast-2.aws.ce.redhat.com, rhui2-cds02.ap-southeast-2.aws.ce.redhat.com.
```
#Add Users:#
```
useradd -u 2300 cate
useradd -u 2900 jemaine
```
#Add Groups:#
```
groupadd aussies
groupadd kiwis
usermod -g kiwis jemaine
usermod -g aussies cate
```
```
id cate
uid=2300(cate) gid=2902(aussies) groups=2902(aussies)
```
sudo yum install nano

#List the /etc/passwd entries for cate and jemaine:#
```
sudo nano /etc/passwd
cate:x:2300:2902::/home/cate:/bin/bash
jemaine:x:2900:2901::/home/jemaine:/bin/bash
```
List the /etc/group entries for kiwis and aussies:#
```
sudo nano /etc/group
kiwis:x:2901:
aussies:x:2902:
```

