


#  Linux working  time usefull commands
### for checking number for lines

    
    cat test.txt | wc -l
    56
    
    ls  -lrth |  wc -l
    
 ### to find linux  last of file
    tail -5f  cat  test.txt    or    cat text.txt  | tail -5f  or  ls -lrth | tail -3f
    
 ##### to find first lines:-
    head -n 3 cat test.txt   or   cat test.txt   | head -n 4    or ls -lrth | head -n 5
    
 ####  how to check  folder memory size
    root@ip-172-31-3-35:/etc# du -sh ssh/
      344K    ssh/
               for all for gige or meta   
               du -sh *  |  grep G
               du -sh *   |  grep M
   
 ### for disk size checking 
    df  -Th
    
###   memoery check
     free -m
     
     note:- if machine ram full check  the service like nagios or regular restart service we can restart so buffer cache will be clean
      systemctl  restart nagios  or systemctl restart nginx
      
###   checking active serice
      systemctl --type=service
      
####  independ  checking meminfo and cpu info
     cat /proc/meminfo   # for memory
     cat /proc/cpuinfo    #  for cpu
     
###  selinux status
   [vagrant@vagrantdev ~]$ sestatus
    SELinux status:                 enabled
    SELinuxfs mount:                /selinux
    Current mode:                   permissive
    Mode from config file:          permissive
    Policy version:                 24
    Policy from config file:        targeted
                   ------or-----
     [vagrant@vagrantdev ~]$ getenforce
        Permissive
    
#    to set selinux we have to options vi /etc/selinux/config  ===check to  disalbed
or command 

    setenforce 0  #  for disable     setenforce 1  #   foe enable

###  user creating
     useradd -m user   #  create user or if nologin    -->  useradd -m -s /bin/nologin  user   ## for checking user logins /etc/passwd   and already crated user 
     modification        usermod -s /usr/sbin/nologin user   # no shalll  useradd -m --shall 
     
     then set passwod
     passwd user
     
#### ssh key gen from root user
    ssh-keygen -b 4096 -t rsa -N '' -f /home/$user/.ssh/id_rsa



#### user permission while create user
                    create 
                    then given ownner shit to# chown -R $user:$user /home/%user/.ssh
                    then given permission to# chmod 700 /home/$user/.ssh

                    drwx------  2 spadala spadala 4096 Jan 14 09:04 .ssh




                    Note:-  id_rsa.pub   is # chmod 644  id_rsa.pub

                    root@bastion:/home/spadala/.ssh# ls -lrt
                    total 12
                    -rw-r--r-- 1 spadala spadala  753 Dec 30 09:52 id_rsa.pub
                    -rw------- 1 spadala spadala 3247 Dec 30 09:52 id_rsa
                    -rw------- 1 spadala spadala  402 Dec 31 11:32 authorized_keys
                    note:-  chmod 600 authorized_keys  

   
    
