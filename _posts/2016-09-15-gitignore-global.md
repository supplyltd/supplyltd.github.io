---
layout: post
date: '2016-09-15 11:48 +1200'
author: Supply
published: true
---
## Copy and paste to /Users/[username]/.gitignore_global

    # Fix $PATH for homebrew
    homebrew=/usr/local/bin:/usr/local/sbin
    export PATH=$homebrew:$PATH

    # aliases
    alias ar="sudo apachectl restart"
    alias ll="ls -la"
    alias sh="defaults write com.apple.finder AppleShowAllFiles TRUE && killall Finder"
    alias hh="defaults write com.apple.finder AppleShowAllFiles FALSE && killall Finder"

    ulimit -n 1024

`source .bash_profile`
