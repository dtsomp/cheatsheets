# ssh

User-specific ssh client config:

    # $HOME/.ssh/config
    Host 192.168.*.*
      StrictHostKeyChecking no
      UserKnownHostsFile=/dev/null
     
    Host dev
      HostName dev.example.com
      Port 22000
      User fooey
      IdentifyFile ~/.ssh/my.key


