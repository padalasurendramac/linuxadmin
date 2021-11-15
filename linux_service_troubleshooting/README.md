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


Example:1 

###  systemctl list-units --type=service OR  systemctl --type=service
   ![image](https://user-images.githubusercontent.com/53860717/141718446-9ded7c0c-381a-47ab-a2af-3d3c1fa24782.png)


###  systemctl list-units --type=service --state=active  OR  systemctl --type=service --state=active
    ![image](https://user-images.githubusercontent.com/53860717/141718521-a62b3108-374e-4407-8027-44944ea79360.png)

###  systemctl list-units --type=service --state=running  OR systemctl --type=service --state=running

    ![image](https://user-images.githubusercontent.com/53860717/141718571-274d1bc6-31fd-4c3a-bed2-d73ad7774cd7.png)

