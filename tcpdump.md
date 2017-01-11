# tcpdump

ASCII dump, look into unencrypted traffic

    tcpdump -i eth0 -A host example.com
    tcpdump -i eth0 -A host example.com and port 80


- -n    do not resolve hostnames
- -S    absolute TCP sequence numbers
- -vv   Very Verbose output
- -A    print ASCII output
- -X    print hex and ASCII output
- -s <value>    capture <value> bytes of each packet. 0 for all.

Deep packet viewing

    tcpdump -i eth0 -nvvXSs0 host dtsomp.homeip.net

Capture to file

    tcpdump -i eth0 -nvvXSs0 host dtsomp.homeip.net -w /tmp/dump.pcap

