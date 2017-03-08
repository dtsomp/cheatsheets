# mutt

Change default viewer: 

	# /etc/mailcap or ~/.mailcap
	image/png; ristretto %s; test=test -n "$DISPLAY"

Configuration options:

    set smartwrap               # wraps lines, this is default.
    set markers=no              # *** no '+' ***
    color markers <fg> <bg>     # color markers, if desired

PGP options (when in send screen):

    press 'p' for options
