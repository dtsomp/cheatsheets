# mutt

Change default viewer: 

	# /etc/mailcap or ~/.mailcap
	image/png; ristretto %s; test=test -n "$DISPLAY"
