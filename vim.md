# vim

Command mode:

	K 			# Show man page for word under cursor

Insert mode:

	Ctrl+t 			# Indent right
	Ctrl+d			# Indent left
	
Config:

	set expandtab		# (turn tabs into spaces)
	set tabstop=4		# (1 tab = 4 spaces)
	set shiftwidth=4	# Set indentation to 4 spaces

On the command line

	
	# Compare local and remote file
	vimdiff /local/file scp://user@host//remote/file
