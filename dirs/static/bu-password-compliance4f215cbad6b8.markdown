---
layout: page
title: bu-password-compliance
permalink: /static/docs/bu-password-compliance/
---

[**<-back**](/static/docs)  

# BU password policy compliance instructions
## Prerequisites
```bash
sudo apt install libpam-pwquality
sudo vim /etc/pam.d/common-password
```
## Password complexity 
### Length
Find the following line in `/etc/pam.d/common-password` and add to the end after `sha512`:
```bash
                                                               #pasword length  #forbid previous passwords 
password [success=2 default=ignore] pam_unix.so obscure sha512 minlen=14        remember=12
```

### Character requirements
Find the following line in `/etc/pam.d/common-password` and add stuff after `retry=3`:
```bash
                                                #at least 1 UC char  #at least 1 LC char   #at least 1 Special char  #how many classes to use (u, d, o)
password  requisite    pam_pwquality.so retry=3 ucredit=-1           dcredit=-1            ocredit=-1                minclass=3
```
## Password expiry
Set values in `/etc/login.defs`. This only applies to new users, all old ones will need to be updated  manually.
```bash
PASS_MAX_DAYS 60
PASS_MIN_DAYS 0
PASS_WARN_AGE 7
```

Manual updating of old users' password policy:
```bash
sudo chage -M 60 -m 0 -I 7 -W 7 <username>
sudo chage -l <username>
```

