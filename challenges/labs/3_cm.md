* HDFS USer

```
[hdfs@ip-172-31-12-51 ~]$ hadoop fs -mkdir /user/berkeley
[hdfs@ip-172-31-12-51 ~]$ hadoop fs -chown berkeley:bruins /user/berkeley
[hdfs@ip-172-31-12-51 ~]$ hadoop fs -mkdir /user/stanford
[hdfs@ip-172-31-12-51 ~]$ hadoop fs -chown stanford:cardinal /user/stanford
[hdfs@ip-172-31-12-51 ~]$ hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - berkeley bruins            0 2017-03-24 18:27 /user/berkeley
drwxrwxrwx   - mapred   hadoop            0 2017-03-24 18:07 /user/history
drwxrwxr-t   - hive     hive              0 2017-03-24 18:14 /user/hive
drwxrwxr-x   - hue      hue               0 2017-03-24 18:15 /user/hue
drwxrwxr-x   - oozie    oozie             0 2017-03-24 18:16 /user/oozie
drwxr-xr-x   - stanford cardinal          0 2017-03-24 18:27 /user/stanford

```

* API output

```
[root@ip-172-31-12-51 yum.repos.d]# curl -u admin:admin http://localhost:7180/api/v14/hosts
{
  "items" : [ {
    "hostId" : "5d4c8cc6-88a1-4b26-bbef-b1f835063643",
    "ipAddress" : "172.31.12.203",
    "hostname" : "ip-172-31-12-203.us-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-51.us-west-1.compute.internal:7180/cmf/hostRedirect/5d4c8cc6-88a1-4b26-bbef-b1f835063643",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16389443584
  }, {
    "hostId" : "d19a8423-49f0-4cfe-bd96-dea7fa4571e7",
    "ipAddress" : "172.31.12.51",
    "hostname" : "ip-172-31-12-51.us-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-51.us-west-1.compute.internal:7180/cmf/hostRedirect/d19a8423-49f0-4cfe-bd96-dea7fa4571e7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16389443584
  }, {
    "hostId" : "315ead7e-60a5-4311-aa53-741eb6693412",
    "ipAddress" : "172.31.4.42",
    "hostname" : "ip-172-31-4-42.us-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-51.us-west-1.compute.internal:7180/cmf/hostRedirect/315ead7e-60a5-4311-aa53-741eb6693412",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16389443584
  }, {
    "hostId" : "1dc00cd5-062f-4553-bb19-701a0078a6d5",
    "ipAddress" : "172.31.7.198",
    "hostname" : "ip-172-31-7-198.us-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-51.us-west-1.compute.internal:7180/cmf/hostRedirect/1dc00cd5-062f-4553-bb19-701a0078a6d5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16389443584
  }, {
    "hostId" : "8def8c04-c2ac-4f48-a656-4ad49f1de1f1",
    "ipAddress" : "172.31.8.145",
    "hostname" : "ip-172-31-8-145.us-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-51.us-west-1.compute.internal:7180/cmf/hostRedirect/8def8c04-c2ac-4f48-a656-4ad49f1de1f1",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16389181440
  } ]
}

```