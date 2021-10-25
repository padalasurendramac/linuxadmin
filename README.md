


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

   

##Screen using in linux

              #  To  create use below commmand    (-S)
              screen  -S  <name>
              #  deattach to screen using ctrl+a Then d
              # to kill the session  ctrl+a  then k
              # Forcefully deattach to use this below command
              screen -r -d <name>
              #  to checking screen name list
              screen -ls
              # to attach  the screen
              screen -r <name>
              
              # to kill the session 
              screen -X -S "<name>" quit
              
# how to checking proccess  on linux

       # command
       ps -ef  or top
       
       or ps -ef | grep <name of the service>
       # to kill the service
       kill -9 <proccessID>
       
# Checking the servie with port

   lsof -i:5004


# Finding the port number with pid:-

    ps aux | grep 1809
    83    root  1809 0.0 0.323504 12222 may28 0:06 node  --max-old-size=8192  index.js KC InternalLEXAnalyzerService-KC
    then 
    
    netstat -lntp | grep 1809
    tc6  0  0 ::8086   :::*
    
    
#    sed commmand using to delete line with one word of the sentence  in that lines.
      
       sed  -i '/kb-filename.xml/d' filename.txt
       
#       sed command using to replace word one to another for only first line of that word in that file

       sed -i 's/from/to/g' filename.txt
       
#       sed command for all lines

         sed -i 's/from/to/gI' filename.txt
    
    
#    diff command using to compare two files

        [root@ip-172-31-19-194 ~]# cat test.txt
        i
        was
        first
        Programmer
        of
        mine
        [root@ip-172-31-19-194 ~]# cat text1.txt
        i
        was
        secound
        Programmer_sec
        of
        mine
        [root@ip-172-31-19-194 ~]# 

           [root@ip-172-31-19-194 ~]# diff test.txt text1.txt
            3,4c3,4
            < first
            < Programmer
            ---
            > secound
            > Programmer_sec
            [root@ip-172-31-19-194 ~]# 

   #    Grep words and delete lines

      grep '<word1>\|<word2>' file.txt | wc -l
      sed -i '/<word1>\|<word2>/d'  file.txt

  #    Linux read and write permissions
     
                           owner     group      other
      read  (r)             4          4          4
      write  (w)            2          2          2
      execute  (x)           1          1          1

      chmod -R 440 file.txt
