---
layout: post
title: OS X Apache permission
published: true
date: '2016-09-15 09:12 +1200'
author: Supply
---
## cd /etc/apache2/users/
`whoami`

`sudo touch [username].conf`

<pre>
&lt;Directory "/Users/[username]/Sites/"&gt;
AllowOverride All
Options Indexes MultiViews FollowSymLinks
Require all granted
&lt;/Directory&gt;
</pre>

## cd /etc/apache2/httpd.conf
`LoadModule authz_core_module libexec/apache2/mod_authz_core.so` : Uncomment(Uncommented on a clean install)

`LoadModule authz_host_module libexec/apache2/mod_authz_host.so` : Uncomment(Uncommented on a clean install)

`LoadModule userdir_module libexec/apache2/mod_userdir.so` : Uncomment

`Include /private/etc/apache2/extra/httpd-userdir.conf` : Uncomment

`LoadModule rewrite_module libexec/apache2/mod_rewrite.so` : Uncomment

`Include /private/etc/apache2/extra/httpd-vhosts.conf` : Uncomment

`LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so` : Uncomment

**SSL**

`LoadModule socache_shmcb_module libexec/apache2/mod_socache_shmcb.so` : Uncomment

`LoadModule ssl_module libexec/apache2/mod_ssl.so` : Uncomment

`Include /private/etc/apache2/extra/httpd-ssl.conf` : Uncomment


## cd /etc/apache2/extra/httpd-userdir.conf
`Include /private/etc/apache2/users/*.conf` : Uncomment


