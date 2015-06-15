---
published: true
---


# Install
`brew install mackup`

# ~/
## Configure .mackup.cfg

	[storage]
    engine = file_system
	path = [dropbox_directory]/_sync
	directory = Mackup

	[applications_to_sync]
	bash
	git
	mackup
	sequel-pro
	ssh
	transmit

# Backup
`mackup backup`

# Restroe
`mackup restore`
