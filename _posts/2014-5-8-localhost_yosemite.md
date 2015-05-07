---
layout: post
title: Localhost Yosemite
---
## Start Apache
`sudo apachectl start`

## Apache version
`httpd -v`

## /etc/apache2/users/
`whoami`<br>
`sudo touch [username].conf`

<pre>
&lt;Directory "/Users/[username]/Sites/"&gt;
AllowOverride All
Options Indexes MultiViews FollowSymLinks
Require all granted
&lt;/Directory&gt;
</pre>

### permisssion
-rw-r--r--  1 [username]  wheel  xxx  x xxx xx:xx [username].conf<br>
`sudo chmod 644 [username].conf`<br>
-rw-r--r--  1 root  wheel  xxx  x xxx xx:xx [username].conf : Result

## /etc/apache2/httpd.conf

`LoadModule authz_core_module libexec/apache2/mod_authz_core.so` : Uncomment(Uncommented on a clean install)<br>
`LoadModule authz_host_module libexec/apache2/mod_authz_host.so` : Uncomment(Uncommented on a clean install)<br>
`LoadModule userdir_module libexec/apache2/mod_userdir.so` : Uncomment<br>
`Include /private/etc/apache2/extra/httpd-userdir.conf` : Uncomment<br>
`LoadModule rewrite_module libexec/apache2/mod_rewrite.so` : Uncomment<br><br>

`Include /private/etc/apache2/extra/httpd-vhosts.conf` : Uncomment<br>
`LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so` : Uncomment<br>

## /etc/apache2/extra/httpd-userdir.conf
`Include /private/etc/apache2/users/*.conf` : Uncomment<br>

## /etc/apache2/extra/httpd-vhosts.conf
<pre>
&lt;VirtualHost *:80&gt;
DocumentRoot "/Users/[username]/Sites/"
ServerName localhost
&lt;/VirtualHost&gt;
</pre>

<pre>
&lt;VirtualHost *:80&gt;
ServerAdmin [useremail]
DocumentRoot "/Users/[username]/Sites/[project]"
ServerName local.xxx
&lt;/VirtualHost&gt;
</pre>

## /etc/hosts
127.0.0.1 local.xxx

## Restart Apache
`sudo apachectl restart`

