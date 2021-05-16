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



