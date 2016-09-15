---
layout: post
title: OS X Apache permission
published: true
date: '2016-09-15 09:12 +1200'
author: Supply
---
## /etc/apache2/users/
`cd /etc/apache2/users/`<br>
`whoami`<br>
`sudo touch [username].conf`<br>
`sudo nano [username].conf`

    <Directory "/Users/[username]/Sites/">
    AllowOverride All
    Options Indexes MultiViews FollowSymLinks
    Require all granted
    </Directory>

## /etc/apache2/httpd.conf

`sudo nano /etc/apache2/httpd.conf` and remove leading `#` symbol

`LoadModule authz_core_module libexec/apache2/mod_authz_core.so` : Removed on a clean install<br>
`LoadModule authz_host_module libexec/apache2/mod_authz_host.so` : Removed on a clean install<br>
`LoadModule userdir_module libexec/apache2/mod_userdir.so`<br>
`Include /private/etc/apache2/extra/httpd-userdir.conf`<br>
`LoadModule rewrite_module libexec/apache2/mod_rewrite.so`<br>
`Include /private/etc/apache2/extra/httpd-vhosts.conf`<br> 
`LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so`

**SSL**

`LoadModule socache_shmcb_module libexec/apache2/mod_socache_shmcb.so`<br>
`LoadModule ssl_module libexec/apache2/mod_ssl.so`<br>
`Include /private/etc/apache2/extra/httpd-ssl.conf`


## /etc/apache2/extra/httpd-userdir.conf

`sudo nano /etc/apache2/extra/httpd-userdir.conf` and remove leading `#` symbol

`Include /private/etc/apache2/users/*.conf`
