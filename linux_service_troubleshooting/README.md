# Checking the service unit list and failure service
=========

### running service
    ansible@****:~$ systemctl list-units --type=service --state=running  | grep ssh
    ssh.service                                    loaded active running OpenBSD Secure Shell server

### active service
    ansible@****:~$ systemctl list-units --type=service --state=active| grep ssh
    ssh.service                                    loaded active running OpenBSD Secure Shell server
   
###  only list 
    ansible@****:~$ systemctl list-units --type=service   | grep ssh
    ssh.service                                    loaded active running OpenBSD Secure Shell server
   
-----
## troubleshooting particular service 

### step:-1 Run journalctl -f   ( on new terminal )

### step:-2 Now restart or start the failure service on another termnial in the same instance ( systemctl start ssh.service ) or ( systemctl restart ssh.service )


