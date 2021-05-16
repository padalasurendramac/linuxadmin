   or


 

#   how to find isntalled packages 
         yum list installed   # centos 7    example :- yum list apache*   for all apache name packages to find or  yum list | grep nginx


         apt  list  --installed  # ubuntu

 # how to update packages
    yum update  <package>  # centos 
    apt --only-upgrade  <package>  #  ubuntu
    
#     installation package
        yum install  <package>   #  centos     remove   yum remove [package_name]  or yum erase [package_name] 

        apt install < package>   #  ubuntu      remove   :--  1.   sudo apt-get remove gimp     # forcely  sudo apt-get --purge remove gimp  

#    how to check avilable package with version 
        simple command:-  1...  yum list available solr

       2......yum --showduplicates list httpd | expand    

----
$ yum --showduplicates list httpd | expand
         Loaded plugins: fastestmirror, langpacks, refresh-packagekit
         Loading mirror speeds from cached hostfile
          * fedora: mirror.steadfast.net

         Available Packages
         httpd.x86_64                        2.4.6-6.fc20                         fedora 
         httpd.x86_64                        2.4.10-1.fc20                        updates
 ----- 
      jai@frank-Jai:~$ apt-cache showpkg chromium
      Package: chromium
      Versions: 

      Reverse Depends: 
        mozplugger,chromium 10.0.648.114~r75702-1~
        chromium-bsu,chromium 0.9.14
        chromium-bsu,chromium 0.9.14
      Dependencies: 
      Provides: 
      Reverse Provides: 
------



#  particular version ubuntu ex:  sudo apt-get install apache2=2.2.20-1ubuntu1   1   
                        linux centos  ex:- sudo yum install httpd-2.4.6-6  
                        apt-get  --only-upgrade install package




==========================================================-

#   update checking

         [root@centos7 ~]# yum check-update
         Loaded plugins: fastestmirror
         Loading mirror speeds from cached hostfile

         bash.x86_64                             4.2.46-20.el7_2        updates
         dbus.x86_64                             1:1.6.12-14.el7_2      updates
         dbus-libs.x86_64                        1:1.6.12-14.el7_2      updates
         device-mapper-persistent-data.x86_64    0.6.2-1.el7_2          updates
         glibc.x86_64                            2.17-106.el7_2.8       updates
         glibc-common.x86_64                     2.17-106.el7_2.8       updates
         initscripts.x86_64                      9.49.30-1.el7_2.3      updates
         kernel.x86_64                           3.10.0-327.28.3.el7    updates
         kernel-tools.x86_64                     3.10.0-327.28.3.el7    updates
         kernel
     
--------------------------------
#    yum repolist showing  for only enable list usee yum repolist or all use  yum repolist all

         [root@centos7 ~]# yum repolist all

         repo id                      repo name                   status
         base/7/x86_64                CentOS-7 - Base             enabled: 9,007
         base-debuginfo/x86_64        CentOS-7 - Debuginfo        disabled
         base-source/7                CentOS-7 - Base Sources     disabled
         c7-media                     CentOS-7 - Media            disabled
         centosplus/7/x86_64          CentOS-7 - Plus             disabled
         ...


#  to add  repo
            yum-config-manager --add-repo="https://mirror.aarnet.edu.au/pub/centos/7"

# to enable
         yum --enablerepo=disabled-repo install package-example
         
         
#   for searching package
                     [root@centos7 ~]# yum search php
                     ===================================================================================== N/S matched: php ======================================================================================
                     graphviz-php.x86_64 : PHP extension for graphviz
                     php.x86_64 : PHP scripting language for creating dynamic web sites
                     php-bcmath.x86_64 : A module for PHP applications for using the bcmath library
                     php-cli.x86_64 : Command-line interface for PHP
                     php-common.x86_64 : Common files for PHP
                     php-dba.x86_64 : A database abstraction layer module for PHP applications
                     php-devel.x86_64 : Files needed for building PHP extensions
                     php-embedded.x86_64 : PHP library for embedding in applications
                     php-enchant.x86_64 : Enchant spelling extension for PHP applications
                     php-fpm.x86_64 : PHP FastCGI Process Manager
                     
  # For package info
            yum info httpd
            
            
  #   For yum history checking
                 [root@centos7 ~]# yum history
               ID     | Login user      | Date and time    | Action(s)      | Altered
               ------------------------------------------------------------------------
               5 | root            | 2016-08-29 14:32 | Install        |    1
                 4 | root            | 2016-08-29 14:28 | Install        |    1
                 3 | root            | 2016-08-29 14:28 | Erase          |    1
                 2 | root            | 2016-08-29 14:28 | Install        |    5
                 1 | System          | 2016-08-29 14:17 | Install        |  298
                 
                 
  #          particular number yum history

                 [root@centos7 ~]# yum history info 15
               Transaction ID : 15
               Begin time     : Mon Aug 29 15:20:57 2016
               Begin rpmdb    : 341:c62a7835aef7986909a89bc51d654acf51b8d756
               End time       :                           (0 seconds)
               End rpmdb      : 340:8701e1360e8e5403f96a5cc61994740ba7d8daf8
               User           : root 
               Return-Code    : Success
               Command Line   : remove httpd -y
               Transaction performed with:
                   Installed     rpm-4.11.3-17.el7.x86_64                      @anaconda
                   Installed     yum-3.4.3-132.el7.centos.0.1.noarch           @anaconda
                   Installed     yum-plugin-fastestmirror-1.1.31-34.el7.noarch @anaconda
               Packages Altered:
                   Erase httpd-2.4.6-40.el7.centos.4.x86_64 @updates
               history info
               
  #  clean cache command
              root@centos7 ~]# yum clean all
            Loaded plugins: fastestmirror
            Cleaning repos: base extras updates
            Cleaning up everything
            Cleaning up list of fastest mirrors
            
 #            for autoclean cache
                [root@centos7 ~]# time yum makecache
               Loaded plugins: fastestmirror, langpacks
               base                                            | 3.6 kB  00:00:00
               extras                                          | 3.4 kB  00:00:00
               updates                                         | 3.4 kB  00:00:00
               (1/12): base/7/x86_64/group_gz                  | 155 kB  00:00:00
               (2/12): extras/7/x86_64/prestodelta             |  72 kB  00:00:00
               (3/12): extras/7/x86_64/filelists_db            | 426 kB  00:00:00
               (4/12): extras/7/x86_64/primary_db              | 160 kB  00:00:00
               (5/12): base/7/x86_64/filelists_db              | 6.2 MB  00:00:01
               (6/12): extras/7/x86_64/other_db                | 652 kB  00:00:00
               (7/12): base/7/x86_64/other_db                  | 2.3 MB  00:00:01
               (8/12): updates/7/x86_64/prestodelta            | 698 kB  00:00:00
               (9/12): base/7/x86_64/primary_db                | 5.3 MB  00:00:01
               (10/12): updates/7/x86_64/filelists_db          | 4.4 MB  00:00:01
               (11/12): updates/7/x86_64/primary_db            | 7.1 MB  00:00:01
               (12/12): updates/7/x86_64/other_db              |  61 MB  00:00:07
               Determining fastest mirrors
                * base: centos.mirror.crucial.com.au
                * extras: centos.mirror.crucial.com.au
                * updates: centos.mirror.crucial.com.au
               Metadata Cache Created

               real    0m40.785s
               user    0m32.504s
               sys     0m1.937s
               
  #             
 
            
            
               


