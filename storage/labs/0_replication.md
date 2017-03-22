* DISTCP from Dinesh cluster

```
> hadoop distcp -pb hdfs://54.234.145.149:8020/ /user/centos/jastidinesh/teragen /data/jastidinesh

> bash-4.2$ hdfs fsck /data/pgaddam -files -blocks
Connecting to namenode via http://ip-172-31-10-79.us-west-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.10.79 for path /data/pgaddam at Wed Mar 22 03:30:32 UTC 2017
/data/pgaddam <dir>
/data/pgaddam/_SUCCESS 0 bytes, 0 block(s):  OK

/data/pgaddam/part-m-00000 500000000 bytes, 15 block(s):  OK
0. BP-84945595-172.31.10.79-1490075518898:blk_1073744899_4075 len=33554432 Live_repl=3
1. BP-84945595-172.31.10.79-1490075518898:blk_1073744900_4076 len=33554432 Live_repl=3
2. BP-84945595-172.31.10.79-1490075518898:blk_1073744901_4077 len=33554432 Live_repl=3
3. BP-84945595-172.31.10.79-1490075518898:blk_1073744902_4078 len=33554432 Live_repl=3
4. BP-84945595-172.31.10.79-1490075518898:blk_1073744903_4079 len=33554432 Live_repl=3
5. BP-84945595-172.31.10.79-1490075518898:blk_1073744904_4080 len=33554432 Live_repl=3
6. BP-84945595-172.31.10.79-1490075518898:blk_1073744905_4081 len=33554432 Live_repl=3
7. BP-84945595-172.31.10.79-1490075518898:blk_1073744906_4082 len=33554432 Live_repl=3
8. BP-84945595-172.31.10.79-1490075518898:blk_1073744907_4083 len=33554432 Live_repl=3
9. BP-84945595-172.31.10.79-1490075518898:blk_1073744908_4084 len=33554432 Live_repl=3
10. BP-84945595-172.31.10.79-1490075518898:blk_1073744909_4085 len=33554432 Live_repl=3
11. BP-84945595-172.31.10.79-1490075518898:blk_1073744910_4086 len=33554432 Live_repl=3
12. BP-84945595-172.31.10.79-1490075518898:blk_1073744911_4087 len=33554432 Live_repl=3
13. BP-84945595-172.31.10.79-1490075518898:blk_1073744912_4088 len=33554432 Live_repl=3
14. BP-84945595-172.31.10.79-1490075518898:blk_1073744913_4089 len=30237952 Live_repl=3

Status: HEALTHY
 Total size:	500000000 B
 Total dirs:	1
 Total files:	2
 Total symlinks:		0
 Total blocks (validated):	15 (avg. block size 33333333 B)
 Minimally replicated blocks:	15 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Wed Mar 22 03:30:32 UTC 2017 in 2 milliseconds

> /data/jastidinesh/teragen/part-m-00003 131200000 bytes, 4 block(s):  OK
0. BP-84945595-172.31.10.79-1490075518898:blk_1073745175_4351 len=33554432 Live_repl=3
1. BP-84945595-172.31.10.79-1490075518898:blk_1073745176_4352 len=33554432 Live_repl=3
2. BP-84945595-172.31.10.79-1490075518898:blk_1073745177_4353 len=33554432 Live_repl=3
3. BP-84945595-172.31.10.79-1490075518898:blk_1073745178_4354 len=30536704 Live_repl=3

Status: HEALTHY
 Total size:	524800000 B
 Total dirs:	2
 Total files:	5
 Total symlinks:		0
 Total blocks (validated):	16 (avg. block size 32800000 B)
 Minimally replicated blocks:	16 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Wed Mar 22 03:32:47 UTC 2017 in 1 milliseconds


The filesystem under path '/data/jastidinesh' is HEALTHY

```
