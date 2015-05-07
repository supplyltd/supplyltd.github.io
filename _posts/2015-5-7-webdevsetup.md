---
layout: post
title: Web Dev Setup
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
`brew install memcached`<br>
`brew install php55-memcached`<br>
`brew install imagemagic`<br>
`brew install php55-imagick`

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
</pre>

## Ruby
`brew install rbenv`<br>
`brew install ruby-build`<br>
`rbenv install 2.2.2`

**.bash_profile**
<pre>
# Initialize rbenv
eval "$(rbenv init -)"
</pre>

`rbenv global 2.2.2`<br>
`gem outdated`<br>
`gem cleanup`<br>
`gem update`<br>
`gem install compass`

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
`npm install -g grunt`
