* Verify user privileges

```
[]pgaddam@ip-172-31-10-79 ~]$ kinit
Password for pgaddam@PGADDAM.COM:

[pgaddam@ip-172-31-10-79 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: pgaddam@PGADDAM.COM

[pgaddam@ip-172-31-10-79 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-10-79.us-west-1.compute.internal@PGADDAM.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-10-79.us-west-1.compute.internal@PGADDAM.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.1)
Driver: Hive JDBC (version 1.1.0-cdh5.9.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables
. . . . . . . . . . . . . . . . . . . .> ;
INFO  : Compiling command(queryId=hive_20170323191414_ba6562df-d5c3-4c73-920a-5a943825d527): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170323191414_ba6562df-d5c3-4c73-920a-5a943825d527); Time taken: 0.793 seconds
INFO  : Executing command(queryId=hive_20170323191414_ba6562df-d5c3-4c73-920a-5a943825d527): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323191414_ba6562df-d5c3-4c73-920a-5a943825d527); Time taken: 0.263 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (1.389 seconds)
```

* Create a Sentry role with full authorization

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170323191818_e6fbfe83-da4c-476d-99b4-42814d55ff3f): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170323191818_e6fbfe83-da4c-476d-99b4-42814d55ff3f); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20170323191818_e6fbfe83-da4c-476d-99b4-42814d55ff3f): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323191818_e6fbfe83-da4c-476d-99b4-42814d55ff3f); Time taken: 0.229 seconds
INFO  : OK
No rows affected (0.352 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170323191919_d725f5ee-520b-42bb-9acf-6b3d54a0104a): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170323191919_d725f5ee-520b-42bb-9acf-6b3d54a0104a); Time taken: 0.08 seconds
INFO  : Executing command(queryId=hive_20170323191919_d725f5ee-520b-42bb-9acf-6b3d54a0104a): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323191919_d725f5ee-520b-42bb-9acf-6b3d54a0104a); Time taken: 0.093 seconds
INFO  : OK
No rows affected (0.185 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP developer;
INFO  : Compiling command(queryId=hive_20170323191919_abfa0e22-c0ba-47f7-b33b-0773e63950f1): GRANT ROLE sentry_admin TO GROUP developer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170323191919_abfa0e22-c0ba-47f7-b33b-0773e63950f1); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20170323191919_abfa0e22-c0ba-47f7-b33b-0773e63950f1): GRANT ROLE sentry_admin TO GROUP developer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323191919_abfa0e22-c0ba-47f7-b33b-0773e63950f1); Time taken: 0.069 seconds
INFO  : OK
No rows affected (0.14 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170323191919_a79d8f7c-f220-4214-b4e2-82ed0dbe0044): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170323191919_a79d8f7c-f220-4214-b4e2-82ed0dbe0044); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20170323191919_a79d8f7c-f220-4214-b4e2-82ed0dbe0044): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323191919_a79d8f7c-f220-4214-b4e2-82ed0dbe0044); Time taken: 0.128 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.258 seconds)
```
* Create Additional test users

```
[george@ip-172-31-10-79 ~]$ kinit
Password for george@PGADDAM.COM:
[george@ip-172-31-10-79 ~]$
[george@ip-172-31-10-79 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1100
Default principal: george@PGADDAM.COM

Valid starting       Expires              Service principal
03/23/2017 19:28:56  03/24/2017 19:28:56  krbtgt/PGADDAM.COM@PGADDAM.COM
	renew until 03/30/2017 19:28:56
[george@ip-172-31-10-79 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-10-79.us-west-1.compute.internal@PGADDAM.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-10-79.us-west-1.compute.internal@PGADDAM.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.1)
Driver: Hive JDBC (version 1.1.0-cdh5.9.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170323193030_1cd16c59-c44d-42a2-9947-920dce1d656f): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170323193030_1cd16c59-c44d-42a2-9947-920dce1d656f); Time taken: 0.054 seconds
INFO  : Executing command(queryId=hive_20170323193030_1cd16c59-c44d-42a2-9947-920dce1d656f): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323193030_1cd16c59-c44d-42a2-9947-920dce1d656f); Time taken: 0.11 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.247 seconds)

```

```
[ferdinand@ip-172-31-10-79 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-10-79.us-west-1.compute.internal@PGADDAM.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-10-79.us-west-1.compute.internal@PGADDAM.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.1)
Driver: Hive JDBC (version 1.1.0-cdh5.9.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170323193939_ec19f067-85b3-416b-a76f-b9f5ddf5de36): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170323193939_ec19f067-85b3-416b-a76f-b9f5ddf5de36); Time taken: 0.078 seconds
INFO  : Executing command(queryId=hive_20170323193939_ec19f067-85b3-416b-a76f-b9f5ddf5de36): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170323193939_ec19f067-85b3-416b-a76f-b9f5ddf5de36); Time taken: 0.135 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.284 seconds)

```


