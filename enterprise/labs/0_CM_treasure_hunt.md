* What is ubertask optimization?
	* 	Enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the 
* Where in CM is the Kerberos Security Realm value displayed?
	*  	Admin->Settings. Under category Kerberos
* Which CDH service(s) host a property for enabling Kerberos authentication?
	* CM, YARN, HDFDS, HUE, OOZIE
* How do you upgrade the CM agents?
	* After upgrading CM Server
	* On agent servers stop cloudera-scm-agent service
	* Updated repo file /etc/yum.repo.d/	 	 
	* $ sudo yum clean all $ sudo yum upgrade 'cloudera-*'
	* $ sudo service cloudera-scm-agent start
* Give the tsquery statement used to chart Hue's CPU utilization?
	* select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
* Name all the roles that make up the Hive service
	* Gateway, WebHCat Sever, Hive Metastore Server, HiveServer2
* What steps must be completed before integrating Cloudera Manager with Kerberos?
	* Setup TLS for communition on cluster 
	
	