---
layout: post
title: Local Dev Setup
published: true
date: '2016-09-15 10:17 +1200'
author: Supply
---
## Open Terminal
`cd ~`

## Show hidden files
`defaults write com.apple.finder AppleShowAllFiles TRUE && killall Finder`

## SSH Key : 
`ssh-keygen -t rsa -C "[useremail]"`

## Install Homebrew
`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`<br>

## Copy and paste [.bash_profile](http://supplyltd.github.io/blog/bash-profile) in /Users/[username]

## Install Packages

### GIT
`brew install git`

**Copy and paste [.gitignore_global](http://supplyltd.github.io/blog/gitignore-global) in /Users/[username]**

`touch .gitconfig`<br>
`nano .gitconfig`

<pre>
[user]
	name = [userrealname]
	email = [useremail]
[color]
	ui = true
[core]
	excludesfile = ~/.gitignore_global
</pre>

### PHP
`brew tap homebrew/dupes`<br>
`brew tap homebrew/versions`<br>
`brew tap homebrew/homebrew-php`<br>
`brew install php56`<br>

`nano /etc/apache2/httpd.conf`

<pre>
LoadModule php5_module /usr/local/opt/php56/libexec/apache2/libphp5.so
</pre>

`nano /usr/local/etc/php/5.6/php.ini`

<pre>
date.timezone = Pacific/Auckland
memory_limit = 2048M
</pre>

**packages**

`brew install fabric`<br>
`brew install composer`<br>
`brew install memcached`<br>
`brew install php56-memcache`<br>
`brew install imagemagick`<br>
`brew install php56-imagick`<br>
`brew install optipng`

### mySQL

`brew install mysql`

### Ruby
`brew install chruby`<br>
`brew install ruby-install`<br>
`ruby-install ruby x.x.x`<br>

`nano .bash_profile`

<pre>
# Ruby
source /usr/local/share/chruby/chruby.sh
chruby x.x.x
</pre>

`source ~/.bash_profile`

### NODE
`brew install node`

`nano .bash_profile`

<pre>
# NODE PATH
export NODE_PATH="/usr/local/lib/node"
export PATH="/usr/local/share/npm/bin:$PATH"
</pre>

`source ~/.bash_profile`

`npm install -g bower`<br>
`npm install -g gulp-cli`<br>
`npm install -g grunt-cli`<br>
`npm install -g uglify-js`

## Services
`brew tap homebrew/services`<br>
`brew services start mysql`<br>
`brew services start memcached`

## SSL
`cd /etc/apache2/`<br>
`sudo openssl req -new -key server.key -out server.csr`
`sudo openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt`
`sudo openssl rsa -in server.key -out server.key`
`sudo apachectl restart`


