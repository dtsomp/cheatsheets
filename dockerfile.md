# Dockerfiles

## Build

    docker build -t="<name>" .

## Structure

    FROM ubuntu:16:04   # base image
    MAINTAINER Firstname Lastname <my@email.com>

    # Metadata
    LABEL version="1.0" role="web server"

    # Build-time arguments
    ARG build
    ARG webapp_user=user

    # env variables during build and exec
    ENV RVM_PATH /home/rvm/
    # cd to path
    WORKDIR /opt/webapp

    # Installation steps
    RUN <shell command>

    # Expose public port
    EXPOSE 80  

    # Create volume on startup 
    VOLUME ["/opt/project"]

    # Add files (they need to be in the build context dir)
    ADD cert.pem /etc/ssl/certs/cert.pem

    # user/group to run this container
    USER nginx
    USER user:group
    
    # Run when container is launched - only one CMD is allowed
    CMD /bin/true
    CMD ["/bin/bash", "-l"]

    # Run when container is launched
    # can not be overuled, any cmds during 'docker run' will be appended as arguments
    ENTRYPOINT ['/usr/sbin/nginx', '-g', 'deamon off;']

    HEALTCHECK --interval=10s --timeout=1m --retries=5m CMD curl http://localhost || exit 1
