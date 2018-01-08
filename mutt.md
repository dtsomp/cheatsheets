# mutt

Change default viewer: 

	# /etc/mailcap or ~/.mailcap
	image/png; ristretto %s; test=test -n "$DISPLAY"

Configuration options:

    set smartwrap               # wraps lines, this is default.
    set markers=no              # *** no '+' ***
    color markers <fg> <bg>     # color markers, if desired


PGP:

    p                           # See PGP options in 'send' screen
    ESC + p                     # Decrypt inline PGP


Viewing files:

    # ~/.mailcap
    text/html; firefox -new-tab %s & sleep 5; test=........
    
Disable new lines:
    
    # This enables "visual" wrapping"
    set wrap
    # This turns off physical line wrapping (ie: automatic insertion of newlines
    set textwdith=0 wrapmargin=0

    # Examine current values
    :verbose set textwidth? wrapmargin?
    ...
    textwidth=72
    Last set from /usr/share/vim/vim74/ftplugin/mail.vim
    wrapmargin=0

Disable new lines permanently:

    mkdir ~/.vim/ftplugin
    cp /usr/share/vim/vim74/ftplugin/mail.vim ~/.vim/ftplugin/
    vi ~/.vim/ftplugin/mail.vim
    # Edit the file and comment out these lines
    # if &tw == 0
    #   setlocal tw=72
    # endif
