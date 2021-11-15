# Disk_space checking and directory, clearing
==============================

## Disk_space comand syntax:- df -Th ( h ( human readable)

      [root@localhost ~]# df -Th
      Filesystem     Type      Size  Used Avail Use% Mounted on
      devtmpfs       devtmpfs  237M     0  237M   0% /dev
      tmpfs          tmpfs     244M     0  244M   0% /dev/shm
      tmpfs          tmpfs     244M  4.5M  240M   2% /run
      tmpfs          tmpfs     244M     0  244M   0% /sys/fs/cgroup
      /dev/sda1      xfs        40G  3.1G   37G   8% /
      tmpfs          tmpfs      49M     0   49M   0% /run/user/1000
      [root@localhost ~]#

##  Checking directory   command syntax:- du -sh * ( h human reable, * = current all directories, /etc = only etc directory )

      [root@localhost etc]# du -sh * 
      0       xinetd.d
      24K     yum
      4.0K    yum.conf
      40K     yum.repos.d
      
##  for mega byte  just grep M  

      [root@localhost etc]# du -sh * | grep M
      16K     NetworkManager
      1.0M    pki
      19M     selinux
      8.0M    udev
      
##  for gigabyte  just grep G 

      [root@localhost etc]# du -sh * | grep G
      1.0G    pki
      8.0G    udev

## cleaning logs file using echo command syntax:- echo "" yum.log
      [root@localhost log]# ls -lrth messages
      -rw-------. 1 root root 321K Nov 15 12:23 messages
      [root@localhost log]# echo "" > messages
      [root@localhost log]# ls -lrth messages
      -rw-------. 1 root root 1 Nov 15 12:31 messages
      
## cleaning the download cache packages command syntax :- yum clean all

      [root@localhost log]# ls -lrth messages
      -rw-------. 1 root root 321K Nov 15 12:23 messages
      [root@localhost log]# echo "" > messages
      [root@localhost log]# ls -lrth messages
      -rw-------. 1 root root 1 Nov 15 12:31 messages
      
 ### Note:- yum cache path to identify from yum.conf ( /etc/yum.conf ) 2. to auto remove cache check keepcache  value 0 to 1
 
      [root@localhost yum]# cat /etc/yum.conf | grep cache
      cachedir=/var/cache/yum/$basearch/$releasever
      
      
      




