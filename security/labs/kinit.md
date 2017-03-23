* Test user authentication

```

>pgaddam@ip-172-31-10-79 ~]$ kinit
Password for pgaddam@PGADDAM.COM:

>[pgaddam@ip-172-31-10-79 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: pgaddam@PGADDAM.COM

Valid starting       Expires              Service principal
03/23/2017 09:12:51  03/24/2017 09:12:51  krbtgt/PGADDAM.COM@PGADDAM.COM
	renew until 03/30/2017 09:12:51
	
>[pgaddam@ip-172-31-10-79 ~]$ kvno krbtgt/PGADDAM.COM@PGADDAM.COM
krbtgt/PGADDAM.COM@PGADDAM.COM: kvno = 1

	
```