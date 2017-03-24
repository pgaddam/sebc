* Tgen

```
> hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=12  -Dmapreduce.map.memory.mb=512 -Ddfs.block.size=67108864 65536000 /user/berkeley/tgen

17/03/24 22:50:40 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1465322
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1025
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=580078
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=580078
		Total vcore-seconds taken by all map tasks=580078
		Total megabyte-seconds taken by all map tasks=593999872
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=3511
		CPU time spent (ms)=148400
		Physical memory (bytes) snapshot=2432061440
		Virtual memory (bytes) snapshot=13530562560
		Total committed heap usage (bytes)=3106406400
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=6553600000

real	1m16.941s
user	0m5.333s
sys	0m0.260s


[berkeley@ip-172-31-0-85 ~]$ hdfs dfs -ls /user/berkeley/tgen
Found 13 items
-rw-r--r--   3 berkeley bruins          0 2017-03-24 22:50 /user/berkeley/tgen/_SUCCESS
-rw-r--r--   3 berkeley bruins  546133400 2017-03-24 22:50 /user/berkeley/tgen/part-m-00000
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00001
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00002
-rw-r--r--   3 berkeley bruins  546133400 2017-03-24 22:50 /user/berkeley/tgen/part-m-00003
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00004
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00005
-rw-r--r--   3 berkeley bruins  546133400 2017-03-24 22:50 /user/berkeley/tgen/part-m-00006
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00007
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00008
-rw-r--r--   3 berkeley bruins  546133400 2017-03-24 22:50 /user/berkeley/tgen/part-m-00009
-rw-r--r--   3 berkeley bruins  546133300 2017-03-24 22:50 /user/berkeley/tgen/part-m-00010


[berkeley@ip-172-31-0-85 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.reduce.memory.mb=512 -Dmapred.reduce.tasks=12 /user/berkeley/tgen /user/berkeley/tgenout

17/03/24 22:55:47 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=2915186090
		FILE: Number of bytes written=5782035043
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=6553616308
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=360
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters
		Launched map tasks=108
		Launched reduce tasks=12
		Data-local map tasks=108
		Total time spent by all maps in occupied slots (ms)=1044966
		Total time spent by all reduces in occupied slots (ms)=360271
		Total time spent by all map tasks (ms)=1044966
		Total time spent by all reduce tasks (ms)=360271
		Total vcore-seconds taken by all map tasks=1044966
		Total vcore-seconds taken by all reduce tasks=360271
		Total megabyte-seconds taken by all map tasks=1070045184
		Total megabyte-seconds taken by all reduce tasks=368917504
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Map output bytes=6684672000
		Map output materialized bytes=2852009381
		Input split bytes=16308
		Combine input records=0
		Combine output records=0
		Reduce input groups=65536000
		Reduce shuffle bytes=2852009381
		Reduce input records=65536000
		Reduce output records=65536000
		Spilled Records=131072000
		Shuffled Maps =1296
		Failed Shuffles=0
		Merged Map outputs=1296
		GC time elapsed (ms)=26160
		CPU time spent (ms)=770220
		Physical memory (bytes) snapshot=60431249408
		Virtual memory (bytes) snapshot=183890210816
		Total committed heap usage (bytes)=71922352128
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=6553600000
	File Output Format Counters
		Bytes Written=6553600000
17/03/24 22:55:47 INFO terasort.TeraSort: done

real	2m27.631s
user	0m7.273s
sys	0m0.266s

```