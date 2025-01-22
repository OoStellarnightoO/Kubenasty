# Kubenasty

This is a step by step instruction on using Minikube on an Ubuntu host (on VMware), creating a custom docker image of Apache 2.4.49 with enabled logging, and creating Persistent Volume to store the logs on minikube.

## Creating the Custom Docker Image of Apache 2.4.49 (PicoCMS WIP)

1) Create Dockerfile [Docker file here](https://github.com/OoStellarnightoO/Kubenasty/blob/main/Apache/Dockerfile)

2) In the same directory as the Dockerfile, create Custom Apache 2.4.49 config file with cgi-bin enabled for RCE testing purposes (Apache 2.4.49 is vulnerable to RCE if cgi-bin is enabled) [httpd.conf here](https://github.com/OoStellarnightoO/Kubenasty/blob/main/Apache/httpd.conf)

## Creating the Persistent Volume YAML file

3) 
