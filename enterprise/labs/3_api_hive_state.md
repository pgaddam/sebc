* Stop Hive

```
curl -X POST -u pgaddam:cloudera http://localhost:7180/api/v1/clusters/pgaddam/services/hive/commands/stop

  "id" : 934,
  "name" : "Stop",
  "startTime" : "2017-03-23T01:13:42.731Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

```

* Stop command progress

```
curl -u pgaddam:cloudera http://localhost:7180/api/v15/commands/934
{
  "id" : 934,
  "name" : "Stop",
  "startTime" : "2017-03-23T01:13:42.731Z",
  "endTime" : "2017-03-23T01:13:44.676Z",
  "active" : false,
  "success" : true,
  "resultMessage" : "Successfully stopped service.",
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  },
  "children" : {
    "items" : [ {
      "id" : 937,
      "name" : "Stop",
      "startTime" : "2017-03-23T01:13:42.737Z",
      "endTime" : "2017-03-23T01:13:44.101Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVESERVER2-bdf4c6870b89d58197e3b0d17647bdc4"
      }
    }, {
      "id" : 935,
      "name" : "Stop",
      "startTime" : "2017-03-23T01:13:42.733Z",
      "endTime" : "2017-03-23T01:13:44.675Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVESERVER2-1fbb184d3d4539b7efff3c9a5ba322c8"
      }
    }, {
      "id" : 936,
      "name" : "Stop",
      "startTime" : "2017-03-23T01:13:42.735Z",
      "endTime" : "2017-03-23T01:13:44.675Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-WEBHCAT-1fbb184d3d4539b7efff3c9a5ba322c8"
      }
    }, {
      "id" : 938,
      "name" : "Stop",
      "startTime" : "2017-03-23T01:13:42.738Z",
      "endTime" : "2017-03-23T01:13:44.094Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVEMETASTORE-bdf4c6870b89d58197e3b0d17647bdc4"
      }
    }, {
      "id" : 939,
      "name" : "Stop",
      "startTime" : "2017-03-23T01:13:42.739Z",
      "endTime" : "2017-03-23T01:13:44.669Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVEMETASTORE-1fbb184d3d4539b7efff3c9a5ba322c8"
      }
    } ]
  },
  "canRetry" : false
}

```

* Start Hive

```
[centos@ip-172-31-10-79 cm_api]$ curl -X POST -u pgaddam:cloudera http://localhost:7180/api/v15/clusters/pgaddam/services/hive/commands/start
{
  "id" : 941,
  "name" : "Start",
  "startTime" : "2017-03-23T01:14:56.632Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

```
* Hive Status

```
centos@ip-172-31-10-79 cm_api]$ curl -u pgaddam:cloudera http://localhost:7180/api/v15/clusters/pgaddam/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-10-79.us-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-10-79.us-west-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_WEBHCATS_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}

```