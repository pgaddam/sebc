* Create a precious directory in HDFS; copy the ZIP course file into it.

```
> hdfs dfs -mkdir /data/precious
> hdfs dfs -moveFromLocal /var/lib/hadoop-hdfs/SEBC-Master.zip /data/precious

```

* Enable snapshots for precious

```
>hdfs dfsadmin -allowSnapshot /data/precious
```


* Create a snapshot called sebc-hdfs-test

```
> hdfs dfs -createSnapshot /data/precious sebc-hdfs-test
```


* Delete the directory

```
The directory /data/precious cannot be deleted since /data/precious is snapshottable and already has snapshots
```

* Delete the ZIP file

```
> hdfs dfs -rm -r /data/precious/SEBC-Master.zip
```


* Restore the deleted file

```
>bash-4.2$ hdfs dfs -ls -R /data/precious/.snapshot
	drwxr-xr-x   - hdfs supergroup          0 2017-03-21 22:11 /data/precious/.snapshot/sebc-hdfs-test
	-rw-r--r--   3 hdfs supergroup     518308 2017-03-21 21:46 /data/precious/.snapshot/sebc-hdfs-test/SEBC-	Master.zip

> bash-4.2$ hdfs dfs -cp /data/precious/.snapshot/sebc-hdfs-test/SEBC-Master.zip /data/precious
> bash-4.2$ hdfs dfs -ls /data/precious
	Found 1 items
	-rw-r--r--   3 hdfs supergroup     518308 2017-03-21 22:44 /data/precious/SEBC-Master.zip
```