SSL/TLS
#######

Test TLS connection

    openssl s_client -connect example.com:443 

Check available SSL/TLS algorithms

     nmap --script ssl-cert,ssl-enum-ciphers -p 443 example.com
