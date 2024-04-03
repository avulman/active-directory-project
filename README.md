# Active Directory Project
[wip]
## Objective
[wip]
## Skills Learned
[wip]
## Tools Used
[wip]

# Steps
## Part 1
### *Download and install Oracle VM VirtualBox Manager*
Access https://www.virtualbox.org/ to download and install the version of VirtualBox compatible with your operating system. Install the dependencies as needed. <br>
### *Download Windows 10 ISO file*
Access https://www.microsoft.com/en-ca/software-download/windows10, scroll down to "Create Windows 10 installation media" and click "Download tool now". Accept "Applicable notices and license terms", advance and select "Create installation media (USB flash drive, DVD, or ISO file) for another PC". Change settings as needed, advance, and select "ISO file" as the media to use. Save this file in any location you desire, just be aware we will be accessing it later to use as our OS on the virtual machine. S <br>
### *Create a VM*
Open up Oracle VM VirtualBox Manager, and create a new VM by clicking "Add", found at the top of the window. Name it anything you desire, and select the ISO image as the Windows.io file we previously installed. For this lab, we will also check "Skip Unattended Installation". Advance to hardware, where 4096MB and 1 CPU will suffice. Be aware this will use your system resources, so adjust as necessary. Advance and leave the Virtual Hard disk at 50GB, and advance. Review your selections on the summary page before clicking on "Finish". <br>
### *Power up and begin Windows installation*
Power on the VM by clicking the green arrow at the top of the window labeled "Start". You should now have your VM running and we will begin to install the OS. Select your settings as needed, then click "Next" and "Install now". Then select "I don't have a product key", choose "Windows 10 Pro" from the list, and click "Next". Accept the license terms, and click "next". In this lab, we will be using the "Custom: Install Windows only (advanced)" option. Select "next", and now Windows 10 should begin installing in the background. <br>
### *Download and install Kali Linux and 7-zip, as well as power up Kali Linux*
Access https://www.kali.org/ and select "Download". Then locate and select the recommended "Virtual Machines". For this lab, select either the 64 or 32-bit installation as needed, and download the recommended "VirtualBox". This will begin downloading a 7-zip file, in which you will need to also navigate to https://www.7-zip.org/, download and install 7-zip. Once Kali Linux is finished installing, locate its installation, right-click the file, hover over "7-zip", and select "Extra to "kali-linux-..." Once it's finished extracting, locate and open the folder, then double-click the file with the ".vbox" extension (should be the blue icon). Double-clicking this should automatically import it into Oracle VM VirtualBox Manager. You can then power on the Kali Linux VM by clicking "Start". <br>
### *Install Windows Server*
Access https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022 and click "Download the ISO". Fill out the information form and click "Download now". Click "64-bit edition" under ISO downloads. This may take some time to download. One it's finished downloading, navigate back to Oracle VM VirtualBox Manager, select "New", and give it any name you desire. For ISO Image, select the ".iso" file that we just downloaded. Next, make sure "Skip Unattended Installation" is checked, and then advance. For hardware, 4096MB with 1 CPU will suffice, and hard disk at 50GB will be just fine. After all of this is configured, select "Next", review the summary to ensure everything is configured how you desire, then "Finish". <br>
### *Power on and configure Windows Server*
As done with our other virtual machines, select "Start" to power on the VM. Select "Next" and "Install now". For OS, select the 2nd option which should be "Windows Server 2022 Standard Evaluation (Desktop Experience)". Click "Next", accept the terms and conditions, "Next" again, and as done previously with the Windows 10 installation, select "Custom". Finally, select "Next" to begin the installation. As soon it's finished installing, begin customizing the settings by creating a password. Select "Finish"
