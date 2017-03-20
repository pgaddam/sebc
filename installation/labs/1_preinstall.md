####1  VM Swapiness
The following commands were run on all 5 nodes
* Check vm.swapiness
	
		cat /proc/sys/vm/swappiness
		30
* Change vm.swapiness to 1
		
		sudo sysctl -w vm.swappiness=1
		echo "vm.swappiness=1" >> /etc/sysctl.conf
	
####2 Mount attributes
	
		[root@ip-172-31-10-79 yum.repos.d]# df -h
		Filesystem      Size  Used Avail Use% Mounted on
		/dev/xvda1       30G  2.7G   28G   9% /
		devtmpfs        7.8G     0  7.8G   0% /dev
		tmpfs           7.7G     0  7.7G   0% /dev/shm
		tmpfs  	        7.7G   17M  7.7G   1% /run
		tmpfs           7.7G     0  7.7G   0% /sys/fs/cgroup
		tmpfs           1.6G     0  1.6G   0% /run/user/1000
		/dev/xvdb        30G   45M   28G   1% /data/0
		

		[root@ip-172-31-10-79 yum.repos.d]# cat /etc/fstab
		#/etc/fstab
		#Created by anaconda on Mon Feb 22 17:08:22 2016
		#Accessible filesystems, by reference, are maintained under '/dev/disk'
		#See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
		#
		UUID=ef6ba050-6cdc-416a-9380-c14304d0d206 /                       xfs     defaults        0 0
		/dev/xvdb /data/0 auto noatime,noexec,nodiratime 0 0
	
####3 Reserve Space Setting

		[root@ip-172-31-6-199 centos]# tune2fs -l /dev/xvdb
			tune2fs 1.42.9 (28-Dec-2013)
			Filesystem volume name:   <none>
			Last mounted on:          <not available>
			Filesystem UUID:          9e6cb4c9-5120-4bbf-ac56-827c0c99db52
			Filesystem magic number:  0xEF53
			Filesystem revision #:    1 (dynamic)
			Filesystem features:      has_journal ext_attr resize_inode dir_index filetype needs_recovery extent 64bit flex_bg sparse_super large_file huge_file uninit_bg dir_nlink extra_isize
			Filesystem flags:         signed_directory_hash
			Default mount options:    user_xattr acl
			Filesystem state:         clean
			Errors behavior:          Continue
			Filesystem OS type:       Linux
			Inode count:              1966080
			Block count:              7864320
			Reserved block count:     393216
			Free blocks:              7696867
			Free inodes:              1966069
			First block:              0
			Block size:               4096
			Fragment size:            4096
			Group descriptor size:    64
			Reserved GDT blocks:      1024
			Blocks per group:         32768
			Fragments per group:      32768
			Inodes per group:         8192
			Inode blocks per group:   512
			Flex block group size:    16
			Filesystem created:       Mon Mar 20 19:11:45 2017
			Last mount time:          Mon Mar 20 19:12:04 2017
			Last write time:          Mon Mar 20 19:12:04 2017
			Mount count:              1
			Maximum mount count:      -1
			Last checked:             Mon Mar 20 19:11:45 2017
			Check interval:           0 (<none>)
			Lifetime writes:          132 MB
			Reserved blocks uid:      0 (user root)
			Reserved blocks gid:      0 (group root)
			First inode:              11
			Inode size:	          256
			Required extra isize:     28
			Desired extra isize:      28
			Journal inode:            8
			Default directory hash:   half_md4
			Directory Hash Seed:      38f8af66-02e3-4c4a-a629-fe2b09d89198
			Journal backup:           inode blocks
####4 Disable transparent hugepage support

		[root@ip-172-31-6-199 centos]# echo 'never' > /sys/kernel/mm/transparent_hugepage/enabled
		[root@ip-172-31-6-199 centos]# echo 'never' > /sys/kernel/mm/transparent_hugepage/defrag`
####5 List Network interface configuration

		[root@ip-172-31-6-199 centos]# ifconfig
		eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        	inet 172.31.6.199  netmask 255.255.240.0  broadcast 172.31.15.255
        	inet6 fe80::4b0:b5ff:fe20:f302  prefixlen 64  scopeid 0x20<link>
        	ether 06:b0:b5:20:f3:02  txqueuelen 1000  (Ethernet)
        	RX packets 994  bytes 80937 (79.0 KiB)
        	RX errors 0  dropped 0  overruns 0  frame 0
        	TX packets 847  bytes 100229 (97.8 KiB)
        	TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
        lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        	inet 127.0.0.1  netmask 255.0.0.0
        	inet6 ::1  prefixlen 128  scopeid 0x10<host>
	        loop  txqueuelen 1  (Local Loopback)
    	    RX packets 6  bytes 416 (416.0 B)
        	RX errors 0  dropped 0  overruns 0  frame 0
        	TX packets 6  bytes 416 (416.0 B)
        	TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0 
        	
####6 Show correct forward and reverse host lookups

			root@ip-172-31-2-148 centos]# nslookup ip-172-31-6-199.us-west-1.compute.internal
			Server:		172.31.0.2
			Address:	172.31.0.2#53

			Non-authoritative answer:
			Name:	ip-172-31-6-199.us-west-1.compute.internal
			Address: 172.31.6.199

			[root@ip-172-31-2-148 centos]# nslookup 172.31.6.199
			Server:		172.31.0.2
			Address:	172.31.0.2#53

			Non-authoritative answer:
			199.6.31.172.in-addr.arpa	name = ip-172-31-6-199.us-west-1.compute.internal.

			Authoritative answers can be found from:


####7 Show the nscd service is running
		
		root@ip-172-31-10-79 centos]# nscd -g
		nscd configuration:

              0  server debug level
             9s  server runtime
              5  current number of threads
             32  maximum number of threads
              0  number of times clients had to wait
             no  paranoia mode enabled
           3600  restart internal
              5  reload count
        passwd cache:
			yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
            600  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/passwd for changes
        group cache:
        	yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
           3600  seconds time to live for positive entries
             60  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/group for changes
        hosts cache:
		    yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
           3600  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/hosts for changes
        services cache:
        	yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
          28800  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/services for changes
        netgroup cache:
			yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
          28800  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/netgroup for changes
            
         SELinux AVC Statistics:
         	  1  entry lookups
              0  entry hits
              1  entry misses
              0  entry discards
              1  CAV lookups
              0  CAV hits
              0  CAV probes
              1  CAV misses 
              
####7 Show the ntpd service is running

		[root@ip-172-31-10-79 centos]# ntpstat
		synchronised to NTP server (69.89.207.199) at stratum 3
		time correct to within 1028 ms
		polling server every 64 s

             
              

              