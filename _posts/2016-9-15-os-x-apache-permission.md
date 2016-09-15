---
layout: post
title: OS X Apache permission
published: true
date: '2016-09-15 09:12 +1200'
author: Supply
---
## cd /etc/apache2/users/
`whoami`<br>
`sudo touch [username].conf`

    <Directory "/Users/[username]/Sites/">
    AllowOverride All
    Options Indexes MultiViews FollowSymLinks
    Require all granted
    </Directory>

## cd /etc/apache2/httpd.conf

Remove leading `#` symbol

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


## cd /etc/apache2/extra/httpd-userdir.conf

Remove leading `#` symbol

`Include /private/etc/apache2/users/*.conf`
