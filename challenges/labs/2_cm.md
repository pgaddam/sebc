* Yum repo list

```
[root@ip-172-31-12-51 yum.repos.d]# ls /etc/yum.repos.d
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-Media.repo    CentOS-Vault.repo      mysql-community.repo
CentOS-CR.repo    CentOS-fasttrack.repo  CentOS-Sources.repo  cloudera-manager.repo  mysql-community-source.repo

```

* scm_prepare_database.sh

```
[root@ip-172-31-12-51 yum.repos.d]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-4-42.us-west-1.compute.internal -utemp -ptemp@Training --scm-host ip-172-31-12-51.us-west-1.compute.internal scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!

```
