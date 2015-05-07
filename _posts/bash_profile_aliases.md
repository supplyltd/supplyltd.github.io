## /Users/[username]
`touch .bash_profile`

**.bash_profile**
<pre>
alias ar="sudo apachectl restart"
alias ll="ls -la"
alias sh="defaults write com.apple.finder AppleShowAllFiles TRUE && killall Finder"
alias hh="defaults write com.apple.finder AppleShowAllFiles FALSE && killall Finder"

alias swc="sass --style compressed --watch"
alias swcd="sass --style compressed --watch scss:css"
alias cw="compass watch"

alias cc="app/console cache:clear"
alias ac="app/console"

ulimit -n 1024
</pre>
`source .bash_profile`
