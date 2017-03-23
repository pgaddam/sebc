* Report the latest available version of the API

```
curl -u pgaddam:cloudera http://localhost:7180/api//version
v15

```

* Report the CM version

```
[centos@ip-172-31-10-79 cm_api]$ curl -u pgaddam:cloudera http://localhost:7180/api/v15/clusters/pgaddam
{
  "name" : "cluster",
  "displayName" : "pgaddam",
  "version" : "CDH5",
  "fullVersion" : "5.9.1",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "clusterUrl" : "http://ip-172-31-10-79.us-west-1.compute.internal:7180/cmf/clusterRedirect/cluster",
  "hostsUrl" : "http://ip-172-31-10-79.us-west-1.compute.internal:7180/cmf/clusterRedirect/cluster/hosts",
  "entityStatus" : "GOOD_HEALTH",
  "uuid" : "99539f9c-5e96-4d90-9de4-b91907179de1"
}
```

* List all CM users

```
[centos@ip-172-31-10-79 cm_api]$ curl -u pgaddam:cloudera http://localhost:7180/api/v15/users
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "pgaddam",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```
* Report the database server in use by CM

```
[root@ip-172-31-10-79 test_user]# curl -u pgaddam:cloudera http://localhost:7180/api/v15/cm/scmDbInfo
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```