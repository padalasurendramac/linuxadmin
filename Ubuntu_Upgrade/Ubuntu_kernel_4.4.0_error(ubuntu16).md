##Ubuntu kernel  4.4.0 error
------------------------------------------------------
##step:-1
-------------------------------------
        Download kernel packages:-
      $ wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.0/linux-headers-5.0.0-050000_5.0.0-050000.201903032031_all.deb
      $ wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.0/linux-headers-5.0.0-050000-generic_5.0.0-050000.201903032031_amd64.deb
      $ wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.0/linux-image-unsigned-5.0.0-050000-generic_5.0.0-050000.201903032031_amd64.deb
      $ wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.0/linux-modules-5.0.0-050000-generic_5.0.0-050000.201903032031_amd64.deb


##step:-2
----------------------------------
     # install kernel 5.0 packages
      sudo dpkg -i *.deb
      #Than update grub
      update-grub

##step:-3 reboot
-----------------------
     # enter below comment to update kernel and update ubuntu to 18 ( latest ) 
      apt-get dist upgrade
	 
##step:-4 after distribustion updation needs to restart server
-----------------------

Refer link
   https://www.tecmint.com/upgrade-kernel-in-ubuntu/

	  

