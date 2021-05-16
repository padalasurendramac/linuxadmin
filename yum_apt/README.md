   or


 

#   how to find isntalled packages 
   yum list installed   # centos 7   
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

------

particular version ubuntu ex:  sudo apt-get install apache2=2.2.20-1ubuntu1   
                        linux centos  ex:- sudo yum install httpd-2.4.6-6  




==========================================================-


