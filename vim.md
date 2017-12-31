# vim

Command mode:

	K 			# Show man page for word under cursor
	:r <filename>		# Insert contents of <filename>
	:r !<command>		# Insert result of shell command
	:make			# Run make using the Makefile in the cwd
    :earlier 5m     # Revert file changes to 5 minutes ago
    :earlier 300s   # Revert file changes to 300 seconds ago

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

Auto-format
    
    # Current file
    gg=G

    # All source files
    :args src/**/*.<ext> | argdo silent execute "normal gg=G" | update

Indentation

    =i{         # Indent the current block of code

Window splitting

    :vspit [/path/to/file]      # Vertical split
    :split [/path/to/file]      # Horizontal split
    ctrl + w w                  # Move to other split
    ctrl + w _                  # Max out height of current split
    ctrl + w |                  # Max out width of current split
    ctrl + w =                  # Normalize all split sizes
    ctrl + w R                  # Swap top/bottom or left/right split
    ctrl + w T                  # Break out window into new tab view
    ctrl + w o                  # Close all other windows in current view
    ctrl + w c                  # Close current window

Window/Tab management

    :ls                         # list windows
    :hide                       # Close window
    :only                       # Close all other windows
    :tabs                       # list tabs and the windows in them
    gt                         # Go to next tab
    gT                         # Go to previous tab

Save/Reload session

    # Save current session
    :mksession my-session.vim

    # Update session file after you've closed/opened tabs
    :mks!

    # Restart session
    vim -S my-session.vim
	

Go directly to last opened file, at last location of cursor

    ctrl+O+O        (double O while pressing ctrl)

Comment out all lines with *pattern*

    :g/pattern/s/^/#/g 
