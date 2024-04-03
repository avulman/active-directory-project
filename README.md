# Active Directory Project
[wip]
## Objective
[wip]
## Skills Learned
[wip]
## Tools Used
[wip]

# Steps
## Part 1 - VM Installation
### *Install Oracle VM VirtualBox Manager*
Navigate to https://www.virtualbox.org/, download the compatible version, and install it with dependencies.
### *Install Windows 10*
Visit https://www.microsoft.com/en-ca/software-download/windows10, get "Create Windows 10 installation media", click "Download tool now", choose "Create installation media (USB flash drive, DVD, or ISO file) for another PC", then select "ISO file" and save it. In Oracle VM VirtualBox Manager, click "Add" to create a new VM, name it, choose the previously downloaded Windows 10 ISO, select 4096MB RAM, 1 CPU, 50GB virtual disk, and finish. Start the VM, follow the installation prompts, select "Custom: Install Windows only (advanced)", and let Windows 10 install.
### *Install Kali Linux*
Get Kali Linux from https://www.kali.org/, download the VM version, and also download/install 7-zip from https://www.7-zip.org/. Extract Kali Linux via 7-zip, import it into Oracle VM VirtualBox Manager, and start the VM. 
### *Install Windows Server*
Download Windows Server 2022 ISO from https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022, fill out the form, download "64-bit edition", create a new VM in Oracle VM VirtualBox Manager with the ISO, 4096MB RAM, 1 CPU, 50GB virtual disk, and finish. Start the VM, select "Install now", choose "Windows Server 2022 Standard Evaluation (Desktop Experience)", customize settings, create a password, and finish.
### *Install Splunk Server*
Navigate to https://ubuntu.com/server. In products, Ubuntu Server, download Ubuntu Server, download Ubuntu Server. This lab uses version 22.04.4 LTS. Create a new VM in Oracle VM VirtualBox Manager with the ISO, 8192MB RAM, 2 CPUs, 100GB virtual disk, and finish. Start the VM, select "Try or Install Ubuntu Server", continue through a series of "Done" and "Continue", then fill out the form before continuing the installation. Finally, reboot. Error messages are *expected*. After rebooting, login and run `sudo apt-get update && sudo apt-get upgrade -y`. After this completes, hit "Enter".
### Part 1 - Summary
You should now have Oracle VM VirtualBox Manager installed with four VMs running Windows 10, Kali Linux, Windows Server, and Splunk Server.

## Part 2
### *Setup Network*
Navigate to Tools > Network > NAT Networks > Create. Provide a name and IPv4 Prefix (in this lab, we will use 192.168.10.0/24), then apply. Navigate to your all your VMs > Settings > Network, change "Attached to: *NAT Network*" and assign the name to the NAT Network you just created. Run the Splunk VM and type `sudo nano /etc/netplan/00-installer-config.yaml`. You should modify and save to look like this: <br>
````
network: 
  ethernet:
    enp0s3:
      dhcp4: no
      addresses: [192.168.10.10/24]
      nameservers:
          addresses: [8.8.8.8]
      routes:
          - to: default
            via: 192.168.10.1
  version: 2
````
Then run `sudo netplan apply` to make changes. Now run `ip a`, you should see the IP address set to 192.168.10.10/24. Verify connecting by running `ping google.com`.
### *Install Splunk*
Navigate to https://www.splunk.com/ and download a free trial of Splunk Enterprise for Linux (.deb). Navigate back to Splunk and run `sudo apt-get install virtualbox-guest-additions-iso`. <br><br> Now navigate to Devices > Shared Folders > Shared Folders Settings > Create new Shared Folder. Navigate to the directory where you installed Splunk, check all three boxes, and continue. <br><br> Reboot the virtual machine with `sudo reboot`. Run `sudo apt-get install virtualbox-guest-utils` then reboot once more, and then `sudo adduser <your username> vboxsf`. Run `mkdir share` to create a new directory called "share". <br><br> Now run `sudo mount -t vboxsf -o uid=1000,gid=1000 <directory name where .deb file is located> share/`. <br><br> Verify completion with `ls -la`, "Share" should be highlighted. Navigate to the share directory using `cd share/` and run `ls -la` once more to view all the files listed in that directory. Install splunk by running `sudo dpkg -i splu<hit tab to auto-complete>` <br><br>
Navigate via `cd /opt/splunk/` and run `ls -la`. Change into the user splunk by running `sudo -u splunk bash`. Run `cd bin/`. Run `./start splunk`, to continue press `q` followed by `y` and [ENTER]. <br><br>
To finalize this step, `exit`, `cd bin`, and finally, `sudo ./splunk enable boot-start -user splunk`. This will allow Splunk to start on boot as the user Splunk.
