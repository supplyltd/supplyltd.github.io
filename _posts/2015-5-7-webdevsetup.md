---
layout: post
title: Web Dev Setup
published: true
---





## Show hidden files
`defaults write com.apple.finder AppleShowAllFiles TRUE && killall Finder`

## SSH Key
`ssh-keygen -t rsa -C "[useremail]"`

## Homebrew
`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`<br>
`brew doctor`

**.bash_profile**
<pre>
# Fix $PATH for homebrew
homebrew=/usr/local/bin:/usr/local/sbin
export PATH=$homebrew:$PATH
</pre>

## PHP
`brew tap homebrew/dupes`<br>
`brew tap homebrew/versions`<br>
`brew tap homebrew/homebrew-php`<br>
`brew options php55`<br>
`brew install php55 --with-apache`

**Extensions**<br>
`brew install fabric`<br>
`brew install composer`<br>
`brew install memcached`<br>
`brew install php55-memcache`<br>
`brew install imagemagick`<br>
`brew install php55-imagick`<br>
`brew install optipng`

**/etc/apache2/httpd.conf**
<pre>
LoadModule php5_module /usr/local/opt/php55/libexec/apache2/libphp5.so
</pre>

## mySQL
`brew install mysql`<br>
`brew info mysql`

## Services
`brew tap homebrew/services`<br>
`brew services start mysql`<br>
`brew services start memcached`

## GIT
`brew install git`

**.gitconfig**
<pre>
[user]
	name = [userrealname]
	email = [useremail]
[color]
	ui = true
[core]
	excludesfile = /Users/[username]/.gitignore_global
</pre>

**.gitignore_global**<br>
The Octocat has [a Gist containing some good rules](https://gist.githubusercontent.com/octocat/9257657/raw/c91b435be351fcdff00f6f97f20824d0286b99ef/.gitignore) to add to this file.

**/usr/local/etc/php/5.5/php.ini**
<pre>
date.timezone = Pacific/Auckland
memory_limit = 1024M
</pre>

## Ruby
`brew install chruby`<br>
`brew install ruby-install`<br>
`ruby-install ruby 2.2.3`<br>

**.bash_profile**
<pre>
# Ruby
source /usr/local/share/chruby/chruby.sh
chruby 2.2.3
</pre>

`gem outdated`<br>
`gem cleanup`<br>
`gem update`<br>
`gem install compass`<br>
`gem install bundler`

## NODE
`brew install node`

**.bash_profile**
<pre>
# NODE PATH
export NODE_PATH="/usr/local/lib/node"
export PATH="/usr/local/share/npm/bin:$PATH"
</pre>

`npm install -g bower`<br>
`npm install -g gulp`<br>
`npm install -g grunt-cli`<br>
`npm install -g uglify-js
