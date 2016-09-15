---
published: true
layout: post
date: '2016-09-15 11:32 +1200'
author: Supply
---

[Mackup](https://github.com/lra/mackup)

## Install
`brew install mackup`

`cd ~`<br>
`touch .mackup.cfg`<br>
`nano .mackup.cfg`

	[storage]
    engine = dropbox
	path = [your mackup directory in dropbox]

	[applications_to_sync]
	bash
	git
	mackup
	ssh
    
    [configuration_files]
    .gitignore_global

# Backup
`mackup backup`

# Restroe
`mackup restore`
