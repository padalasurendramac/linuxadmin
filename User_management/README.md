#  User creations and checking no login , /bin/bash/ , /bin/sh

## creating user  command syntax:- useradd -m -d /home/<userName> -c "<userName>" <userName> -s /bin/sh or /bin/bash or /bin/nologin  
  ( Look at the above snapshot, we have created a user xyz along with creating a home directory (-m), setting the name of home directory (-d), and a description (-c). -u  userid ) 

  
        [root@localhost ~]# useradd -m -d /home/test -c "test" test -s /bin/sh
        [root@localhost ~]# cat /etc/passwd | tail -1
        test:x:1002:1002:test:/home/test:/bin/sh
         

        Note:- a) passwd file using to identity the shell type
               b) password set command syntax:- passwd <test>
               c) changing shell  command syntax:-   usermod -s /bin/bash <test>
               d) useradd -u 1002 <test>  ( test:x:1002:1002:test:/home/test:/bin/sh )
               
  
## giving sudo permission 
       Add following line  to /etc/sudoers
       <test>    ALL=(ALL)       NOPASSWD: ALL

  
##  .ssh folder permission and ssh key generate and file permissions 
### first create .ssh folder then change ownership and permission below
       mkdir /home/<test>/.ssh
       chown -R <test>:<test> /home/<test>/.ssh
       chmod 700 /home/<test>/.ssh
  
### to generate ssh key
  
      
         #ssh-keygen -b 4096 -t rsa -N '' -f /home/<user>/.ssh/id_rsa
         Note:- above command for generate key
         after permission or ownership  should be below
      
         #root@****:/home/<test>/.ssh# ls -lrt
        total 12
        -rw-r--r-- 1 <test> <test>  753 Dec 30 09:52 id_rsa.pub      ( r+w = 6  r=4 r=4  chmod 644 id_rsa.pub )
        -rw------- 1 <test> <test> 3247 Dec 30 09:52 id_rsa          ( r+w = 6 0 0       chmod 600 id_rsa )
        -rw------- 1 <test> <test>  402 Dec 31 11:32 authorized_keys ( r+w = 6  0  0   chmod   600 authorized_keys
         
         
 ## del user
         userdel -r <test> ( -r include delete user's home directory as well )



## group creating 

      groupadd <test>
      ex:- [root@localhost ~]# groupadd java
           [root@localhost ~]# cat /etc/group | grep java
           java:x:1003:   
## del group 
         groupdel <group>  
         ex:- groupdel  java

## add user to group
         usermod -a -G <group> <userName> 
         example:- [root@localhost ~]# usermod -a -G java   test
                   [root@localhost ~]# cat /etc/passwd | grep test
                   test:x:1002:1002:test:/home/test:/bin/sh
                   [root@localhost ~]# cat /etc/group | grep java
                   java:x:1003:test
         
         
## Remove user from group  ( test=(user) , java =(group) )  
command syntax :- gpasswd -d <user> <group>

                  [root@localhost ~]# groups test
                  test : test java
                  [root@localhost ~]# gpasswd -d test java
                  Removing user test from group java
                  [root@localhost ~]# groups test
                  test : test
                  [root@localhost ~]#

