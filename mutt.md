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
