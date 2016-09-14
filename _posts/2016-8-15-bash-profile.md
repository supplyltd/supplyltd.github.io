---
layout: post
title: .bash_profile
published: true
date: '2016-09-15 11:00 +1200'
author: Supply
---

## Copy and paste in /Users/[username]
<pre>
# Fix $PATH for homebrew
homebrew=/usr/local/bin:/usr/local/sbin
export PATH=$homebrew:$PATH

# aliases
alias ar="sudo apachectl restart"
alias ll="ls -la"
alias sh="defaults write com.apple.finder AppleShowAllFiles TRUE && killall Finder"
alias hh="defaults write com.apple.finder AppleShowAllFiles FALSE && killall Finder"

ulimit -n 1024
</pre>
`source .bash_profile`
