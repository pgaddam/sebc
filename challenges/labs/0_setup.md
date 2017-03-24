* List the cloud provider you are using (AWS, GCE, Azure, other)
	* AWS
* List the nodes you are using by IP address and name

```
52.53.167.226	ip-172-31-4-42.us-west-1.compute.internal
54.183.28.165	ip-172-31-12-51.us-west-1.compute.internal
54.193.74.182	ip-172-31-8-145.us-west-1.compute.internal
54.67.40.49		ip-172-31-7-198.us-west-1.compute.internal
52.53.209.66	ip-172-31-12-203.us-west-1.compute.internal
``` 
* List the Linux release you are using

```
[centos@ip-172-31-4-42 ~]$ cat /etc/centos-release
CentOS Linux release 7.2.1511 (Core)
```
* Demonstrate the disk capacity available on each node is >= 30 GB

```
[centos@ip-172-31-4-42 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  877M   50G   2% /
devtmpfs        7.8G     0  7.8G   0% /dev
tmpfs           7.7G     0  7.7G   0% /dev/shm
tmpfs           7.7G   17M  7.7G   1% /run
tmpfs           7.7G     0  7.7G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000
tmpfs           1.6G     0  1.6G   0% /run/user/0
```

* List the command and output for yum repolist enabled

```
[root@ip-172-31-4-42 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.supremebytes.com
 * extras: mirror.scalabledns.com
 * updates: repos.lax.quadranet.com
repo id                                                                      repo name                                                                      status
base/7/x86_64                                                                CentOS-7 - Base                                                                9,363
extras/7/x86_64                                                              CentOS-7 - Extras                                                                311
updates/7/x86_64                                                             CentOS-7 - Updates                                                             1,111
repolist: 10,785
```

* List the /etc/passwd entries for berkeley and stanford

```
[root@ip-172-31-4-42 centos]# cat /etc/passwd | grep berkeley
berkeley:x:2040:2042::/home/berkeley:/bin/bash
[root@ip-172-31-4-42 centos]# cat /etc/passwd | grep stanford
stanford:x:2020:2020::/home/stanford:/bin/bash
```

* List the /etc/group entries for cardinal and bruins. `Centos version did not have /etc/group. So, used getent `

```
[root@ip-172-31-4-42 centos]# getent group cardinal
cardinal:x:2042:
[root@ip-172-31-4-42 centos]# getent group bruins
bruins:x:2041:

```

* My SQL repo file
 	* mysql57-community-release-el7-9.noarch.rpm