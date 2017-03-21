* Teragen Command

```
> time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 100000000 /data/terasort/input
> 7/03/21 19:09:20 INFO mapreduce.Job: Counters: 21
	File System Counters
		FILE: Number of bytes read=276327
		FILE: Number of bytes written=564136
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=0
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=4
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=83
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=596
		Total committed heap usage (bytes)=163577856
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=10000000000

real	2m12.547s
user	2m0.215s
sys	0m7.092s 
```

* Terasort Command

```
>time hadoop jar hadoop-examples.jar terasort /data/terasort/input /data/terasort/output
7/03/21 19:28:00 INFO mapreduce.Job: Counters: 35
	File System Counters
		FILE: Number of bytes read=17788035869
		FILE: Number of bytes written=1582871561503
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1508105708600
		HDFS: Number of bytes written=0
		HDFS: Number of read operations=97173
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=599
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=10400001788
		Input split bytes=45296
		Combine input records=0
		Combine output records=0
		Reduce input groups=0
		Reduce shuffle bytes=9353103288
		Reduce input records=0
		Reduce output records=0
		Spilled Records=167108859
		Shuffled Maps =268
		Failed Shuffles=0
		Merged Map outputs=264
		GC time elapsed (ms)=31154
		Total committed heap usage (bytes)=79757836288
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=10000000000
	File Output Format Counters
		Bytes Written=0
17/03/21 19:28:00 INFO terasort.TeraSort: done

real	10m39.373s
user	8m11.614s
sys	0m41.200s

```
