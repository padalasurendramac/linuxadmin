#Ubuntu update for 16 to 18 or 20
-----------------------------------------

   Notes:- 1   apt-get updae # it will downlaod updated related scripts downlaods
   
   
           2.   apt-get upgrade  # it will upgrade the existing packages.
   
           3.  apt-get dist upgrade # it will upgrade the kernel and distribution
           
           
           4. apt-get clean # is using to clean apt.
           
           
           5. apt-get  install -f # is  using to fix the broken package ( like reinstalle)
           
           
           6. particular  kernel update  (  step. download `deb` packgae .stet2. install using  `dkpg -i *.deb` command. ) then type this command `update-grub`
           
           
           7. checking kernel package `dpkg --list | grep linux-image`
           
           
           8. reomve kernel `apt remvove <pacakgeneme>`
           
           
           9. checking kernel command ` uanme -msr` or `uname -r`


            10. checking ubuntu version `lsb_release -a`


###Step:-1 # Run the update command with sudo 
--------------------------
             sudo apt-get update


###Step:- 2  Run the release upgrade command with sudo
-------------------------------------
              sudo do-release-upgrade
             
             After that it will prompt this below msg
#NOTE:- No ssh session failure and no internet connection dropping while upgrading.
    
              This session appears to be running under ssh. It is not recommended
          to perform a upgrade over ssh currently because in case of failure it
          is harder to recover.

          If you continue, an additional ssh daemon will be started at port
          '1022'.
          Do you want to continue?

          Continue [yN]
          
###   Enter “ y “
###Again prompt for another warning msg about firewalls and iptables
            To continue please press [ENTER]
            
###Press “enter”

###Step:-3 :- another warning msg for downloading and installing packages.
                  You have to download a total of 173 M. This download will take about
          21 minutes with a 1Mbit DSL connection and about 6 hours with a 56k
          modem.

          Fetching and installing the upgrade can take several hours. Once the
          download has finished, the process cannot be canceled.

           Continue [yN]  Details [d]
###Enter “ y “
####Note:-  while downloading and upgrading it prompt msg for upgrading the package or keep the local version currently installed.   
###Enter “ N “  for keep the local version currently installed ( package like apache and nagios etc ..)


###Then prompt for remove obsolete package. 
 
              Remove obsolete packages?


            28 packages are going to be removed.

             Continue [yN]  Details [d]
             
###And confirm enter “ y “
####Package configuration msg

   <img src="https://raw.githubusercontent.com/padalasurendramac/linuxadmin/main/Ubuntu_Upgrade/images/keep_the_local_version.png" >




####Select the “ keep the local version currently installed “ then tab to “ ok “

#####Step:-4 Once the upgrade is completed. you’ll be prompted to reboot.

          System upgrade is complete.

          Restart required

          To finish the upgrade, a restart is required.
          If you select 'y' the system will be restarted.

          Continue [yN]


###Enter “ y “ it will reboot the server.
        <img src="https://raw.githubusercontent.com/padalasurendramac/linuxadmin/main/Ubuntu_Upgrade/images/image1.png" >



### Completed the upgradation to Ubuntu 18.04.1 LTS
        
            root@nagios:~# lsb_release -a
            No LSB modules are available.
            Distributor ID: Ubuntu
            Description:    Ubuntu 18.04.5 LTS
            Release:        18.04
            Codename:       bionic


