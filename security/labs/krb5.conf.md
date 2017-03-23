# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 dns_lookup_realm = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 rdns = false
 default_realm = PGADDAM.COM
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac

[realms]
  PGADDAM.COM = {
   kdc = ip-172-31-2-148.us-west-1.compute.internal:88
   admin_server = ip-172-31-2-148.us-west-1.compute.internal:749
  }

[domain_realm]
  .us-west-1.compute.internal = PGADDAM.COM
  us-west-1.compute.internal = PGADDAM.COM
