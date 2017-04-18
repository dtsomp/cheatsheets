# apt cheatsheet


## PPAs 

Add a PPA key
    
    apt-key adv --keyserver keyserver.ubuntu.com --recv fb7b395f 

## Work with packages

    # Download only
    apt-get download packagename

    # Check contents
    dpkg -c packagename
    
    # Unpack 
    ar -x packagename
    tar zxvf control.tar.gz
    tar Jxvf data.tar.gz

    # Find which package a file belongs to:
    dpkg -S /usr/bin/ls


