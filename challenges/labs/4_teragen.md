* Tgen

```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Ddfs.block.size=67108864 -Dmapreduce.map.memory.mb=512 6553600000 /user/berkeley/terasort/input

Cluster was very slow to execute
```