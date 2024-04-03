# Active Directory Project
[wip]
## Objective
[wip]
## Skills Learned
[wip]
## Tools Used
[wip]

# Do it Yourself
## Steps - Part 1
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

## Steps - Part 2
