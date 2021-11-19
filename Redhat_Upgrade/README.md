# RedHat Upgrade OS and Kernel
------
Note:- a) exclude packages while upgarde ( yum update --exclude=ansible\* --exclude=nginx* )

       b) broken packages while upgarde ( yum update --exclude=ansible\* --exclude=nginx* --skip-broken )
       
        Below error:- You could try using --skip-broken to work around the problem
                    You could try running: rpm -Va --nofiles --nodigest

## Step:-1 Clean yum packages   
	    Command:- yum clean all

## Step:-2  Checking Current  OS ( REDHAT ) and Kernel version 
       Command:- hostnamectl    
### Example:- 
         [root@ip-172-30-4-152 ~]# hostnamectl
       Static hostname: ip-172-30-4-152.us-west-1.compute.internal
             Icon name: computer-vm
               Chassis: vm
            Machine ID: ec2cd0581319d849059883a41e8d2753
               Boot ID: 556cfd79dc1a4b889cd72afc886fe83b
        Virtualization: kvm
      Operating System: Red Hat Enterprise Linux Server 7.7 (Maipo)
           CPE OS Name: cpe:/o:redhat:enterprise_linux:7.7:GA:server
                Kernel: Linux 3.10.0-1062.12.1.el7.x86_64
          Architecture: x86-64

## Step:-3  Checking available packages command ( redhat and kernel ) 
         Command:- yum check-update redhat-release-serve*

##  Command:- yum check-update kernel* 
         Note:- above command not required ( kernel is dependency package )

##  Step:-5 Updating release and kernel
         Command:- yum update redhat-release-server
          Command:- yum update kernel
 ### Note:- above command not required ( kernel is dependency package )

## Step:-4 Reboot  instance after upgrade 
     
        Command:- reboot

## Step:- 5 verifying versions 
        Command:- hostnamectl
