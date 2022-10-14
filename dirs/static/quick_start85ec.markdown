---
layout: page
title: quick_start
permalink: /static/docs/quick_start/
---

[**<-back**](/static/docs)  

# IntelPA cluster quick-start

## Setting up SSH server
Passwords are disabled on the server, so you need to log in using your SSH publickey. To generate this:
```console
user@local:~$ ssh-keygen
```
Once your publickey is generated copy it from `/home/user/.ssh/id_rsa.pub` and send it to either Kavi(kjayathunge@bournemouth.ac.uk) or Jiajun(jhuang@bournemouth.ac.uk) so you can be added as a user on the cluster. Make sure it is the file ending in `.pub`, don't give away your private key (`id_rsa`)!

Once the account is created, you should be able to login: 
```console
user@local:~$ ssh user@intelpa-2.student.bournemouth.ac.uk
Welcome to Ubuntu 20.04.4 LTS (GNU/Linux 5.14.0-1051-oem x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

2 devices have a firmware upgrade available.
Run `fwupdmgr get-upgrades` for more information.


95 updates can be applied immediately.
To see these additional updates run: apt list --upgradable

New release '22.04.1 LTS' available.
Run 'do-release-upgrade' to upgrade to it.

Last login: Thu Oct 13 13:46:20 2022 from 10.126.53.243
```
This banner message means you've successfully logged on to the server. To set up the SSH 
container that you'll be connecting to your IDE:
```console
user@intelpa-2:~$ cp -r /mnt/intelpa-containers ~ 
user@intelpa-2:~$ chmod -R 700 ~/intelpa-containers
user@intelpa-2:~$ cd ~/intelpa-containers
user@intelpa-2:~$ podman build -f Dockerfile.cli-workspace -t cli-workspace .
user@intelpa-2:~$ ./start_cli_server.sh
```
If all goes well, you should see something like this:
```console
Checking for free network ports in range 1024 to 49151...
This may take a while in (very) rare cases.
Found free port, copy this and use it to configure your IDE's SSH interpreter: 1025
```
Keep a note of the port number, you'll need it for the next step.


## Connecting your editor to the server
Launch your IDE on your local machine. Assuming you are using Pycharm (this should be possible on other 
IDEs such as VSCode as well):

1. Locate the interpreter menu in the bottom right corner of the screen:   
   <img alt="Interpreter selection" src="interpreter.png" width="800"/>
2. Navigate to the SSH interpreter tab and type in the name of the server you wish to connect to. 
   In this example, we use `intelpa-2.student.bournemouth.ac.uk`. Paste in the port number from the 
   previous script and set the Username as `root`.   
   <img src="./ssh_int.png" width="800">
3. Change the paths used by your IDE on the remote machine. By default, the python path is set to `/bin/python`,
   which is not what we want (We're using Miniconda). Change it to `/root/miniconda/bin/python3.9`. We also need to 
   change the mapping of the project root on your local machine to the one on the remote. Currently, it should be
   mapping to the `/tmp/` directory, which is not ideal (this directory is regulary emptied by Linux). Create a 
   directory for your project in the `/home/` directory and change the path mapping to it:  
   <p float="left">
      <img src="./add_int_default.png" width="600"/> 
      <img src="./set_proj_root.png" width="400"/>
   </p>
4. Please make sure your settings look like this before hitting finish.  
   <img src="./interpreter_final.png" width="800">
5. If all goes well, you should see the following message in the bottom left of your screen informing you that 
   your files were successfully transferred:   
   <img src="./successful_transfer.png" width="800"/>