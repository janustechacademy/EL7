# EL7
Additional materials and Setup Guide For JANUS Technical Academy Enterprise Linux version 7/8

You will first need to install CentOS on three virtual machines.

Download the CentOS .iso from

http://isoredirect.centos.org/centos/7/isos/x86_64/

Create three virtual machines (VMs), with 2 10GB hardrives each. Name them Class, Lab, and Final.
You can use any virtualization solution you like, for self-study and small classroom environments VMware player is fairly intuitive and has the advantage of being free. You can get it and instructions for creation of VMs here:

https://my.vmware.com/en/web/vmware/free#desktop_end_user_computing/vmware_workstation_player/14_0

https://kb.vmware.com/s/article/2013483

https://kb.vmware.com/s/article/1002

Install CentOS on all three VMs.

Interupt the boot sequence by pressing tab. Add fips=1 to the end of the command line, as detailed in the Booting module. A minimal software installation with no special partitioning is sufficient.
Configure networking to DHCP and Active. During the installation, set the root password and create a second user named student

Copy the materials to each machine:

On each machine, log in as root. Then from the command line run...

yum -y install git
cd /
git clone https://github.com/janustechacademy/EL7
tar -xvf /EL7/setup.tar
On all of the machines run...

/lab/setup_lab.sh
The first two of these will be your class and lab machines.

On the third machine, which will be used only for the final lab, run...

/lab/setup_final.sh
This file is currently broken -- to fix it: vi /lab/setup_final.sh :set fileformat=unix :wq! before running it.
