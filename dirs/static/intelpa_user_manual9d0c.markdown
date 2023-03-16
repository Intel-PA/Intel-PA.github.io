---
layout: page
title: intelpa_user_manual
permalink: /static/intelpa_user_manual/
---

[**<-back**](/static)  

# Intel-PA user manual

In order to keep the base image of the machines in the Intel-PA cluster as simple as possible, none
of the user accounts on the system will be part of the sudo group. For this reason, please use
Podman, a containerisation tool that lets you install and run software with full authority inside
and isolated environment.

For the rest of this document, we will assume that you are working on intelpa-1, replace any
instances of this with the actual hostname as the case may be.

## Using podman
Podman is a direct replacement for Docker that we're using instead of the latter for technical
reasons. If you have experience using Docker there should be no learning curve, just use `podman`
where you would `docker`. 

Display running containers:
```bash
$ podman ps
```

Building from Dockerfile contained in the current directory:
```bash
$ podman build -t image_name .
```

Test run of a container that uses the GPU:
```bash
$ podman run --rm --gpus all nvidia/cuda:11.0.3-base-ubuntu20.04 nvidia-smi
```

## GUI applications
The machines have been set up with a VNC(virtual network computing) server, which allows you to
forward graphics over network, which is useful for running any GUI applications such as IDEs and
visaulising graphical output from your work.


A minimal example of how to set this up is as follows, assuming you have the following directory
structure:
### On the Intel-PA machine
```bash
guidemo/
  ├Dockerfile
  └docker-compose.yml
```
Where Dockerfile is as follows:
```Dockerfile
FROM ubuntu:latest
RUN apt-get update && apt-get install -y gedit xauth
RUN echo "Hello from Docker container with ID: $HOSTNAME" > newfile
RUN cat newfile
CMD ["gedit", "newfile"]
```
and docker-compose.yml is:
```yaml
version: "3"
services:
  app:
    image: dockergui:latest
    build: .
    environment:
      - DISPLAY=${DISPLAY}
      - XAUTHORITY=/tmp/.docker.xauth
    volumes:
      - /tmp/.X11-unix:/tmp/.X11-unix
      - /tmp/.docker.xauth:/tmp/.docker.xauth
    network_mode: host
```
Then, start the VNC server if you haven't already:
```bash
$ vncserver :i -localhost no
$ Password: 
$ confirm: 
```
where `i` is an integer associated with the display you wish to connect. Be aware that
other people on the machine may have chosen a particular value and you may need to try a few out to
find one that is free. You also need to set a password for accessing this screen.

### On your personal device
Assuming you are on the Bournemouth University network (either on campus or via VPN), you can do the following from your client machine:
```bash
$ sudo apt-get install tigervnc-viewer
$ xtigervncviewer intelpa-1:i
```
This will open a GUI application that will prompt you for the password that you set in the previous
section. If all goes well, you will be looking at a Ubuntu desktop. At this point you can run the
container we specified in our Dockerfile in the previous section:
```bash
$ cd guidemo
$ podman-compose up
```
This should open up a `gedit` window with some text indicating that it successfully ran the
container and opened a graphical application. You can use a similar workflow to adapt it to your
needs for any GUI application.
