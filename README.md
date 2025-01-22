# Kubenasty

This is a step by step instruction on using Minikube on an Ubuntu host (on VMware), creating a custom docker image of Apache 2.4.49 with enabled logging, and creating Persistent Volume to store the logs on minikube.

## Creating the Custom Docker Image of Apache 2.4.49

1) Create Dockerfile
```bash
#Dockerfile
FROM httpd:2.4.49

# RUN commands (without returning to user root, the apt install commands will fail due to lack of perms)
COPY httpd.conf /usr/local/apache2/conf/httpd.conf

# git clone to tmp folder first because it will run into issues trying to clone to /usr/local/apache2/htdocs as it already exists
RUN apt-get update && apt-get install -y git && \
    git clone https://github.com/picocms/Pico.git /tmp/pico && \
    cp -r /tmp/pico/* /usr/local/apache2/htdocs/ && \
    rm -rf /tmp/pico && \
    chmod -R 755 /usr/local/apache2/htdocs/ && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Expose the default HTTP port
EXPOSE 80

```
2) In the same directory as the Dockerfile, create Custom Apache 2.4.49 config file with cgi-bin enabled for RCE testing purposes (Apache 2.4.49 is vulnerable to RCE if cgi-bin is enabled)

```bash

```

3) 
4) 
