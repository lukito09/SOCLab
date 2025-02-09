<h1>Building SOC Home Lab</h1>


<h2>Description</h2>
The project goal is to build SOC Lab at home using Pfsense, Active Directory, Windows Workstation, Sysmon and Crowdsec hosted on Virtual Box VM.
<br />


<h2>Program walk-through:</h2>

<p align="center">
Create New VM and load it up with Pfsense ISO Image: <br/>
<img src="https://i.postimg.cc/8c0f1dSB/Image-1.png" height="80%" width="80%" />
<br />
<br />

<p align="Center">
Allocate Memory and CPU: <br/>
<img src="https://i.postimg.cc/rmpSMw4T/Image-2.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
For this lab we will be using 3 Network adapter, one is created by default and the other 2 will be an internal network and will be named GREEN and DMZ : <br/>
<img src="https://i.postimg.cc/8zh9xNMw/Image-3.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/8C43P4y6/image-4.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/sX2LBW80/image-5.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Note: if you encounter at boot up stage - make sure you set the iso type as BSD and subtype as Free BSD <br/>
<img src="https://i.postimg.cc/vT9YgCxB/Image-6.png" height="80%" width="80%" />
<br />
<br />

<p align="Center">
Note: Unchecked floopy from boot order and put Hard Disk as boot priority <br/>
<img src="https://i.postimg.cc/SNCLksR0/Image-7.png" height="80%" width="80%" />
<br />
<br />
  
 Following the instruction will get you to boot up Pfsense successfully
<br />
<br />

<p align="Center">
Once you boot up the machine, Follow the installation process for Pfsense as follows and at the end reboot the machine: <br/>
<img src="https://i.postimg.cc/90Jh7VFc/image-8.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/Vk3cMK10/image-9.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/bNw8jG3r/image-10.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/XYZbpRM0/Image-11.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/DfgFDQQR/Image-12.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/tJC0yfdw/Image-13.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/tJrKg52T/Image-15.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/L4NKv92p/Image-16.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/02jgBTyJ/Image-17.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/vZxJQ59Y/Image-18.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/VLhyQKJZ/Image-19.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/8C8qssBh/Image-20.png" height="80%" width="80%" />
<img src="https://i.postimg.cc/QthwkPzC/Image-21.png" height="80%" width="80%" />
<br />
<br />

<p align="Center">
You will see the screen below to confirm that your pfsense has been installed : <br/>
<img src="https://i.postimg.cc/pTnTtmZ3/Image-22.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Select option 1 to assign the interface: <br/>
<img src="https://i.postimg.cc/C5swFkfr/Image-23.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Assign Wan -> em01, Lan -> em1 and Opt1 -> em2 : <br/>
<img src="https://i.postimg.cc/ryj6w8PH/Image-24.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Select option 2 to set the IP address and As you can see from the below screenshot I have assigned the IP address as 192.168.1.1/24 and this will be your gateway: <br/>
<img src="https://i.postimg.cc/vmSBjpJq/Image-26.png" height="80%" width="80%" />
<br />
<br />

Pfsense Installation is now complete
<br />
<br />

<p align="Center">
Now we want to create an Active Directory for this lab, create a new VM and load up Windows Server 2022 ISO file as follows: <br/>
<img src="https://i.postimg.cc/wxkKjhvH/Image-27.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Allocate Memory and CPU ( adjust as necessary to ensure smooth process): <br/>
<img src="https://i.postimg.cc/HWzKgdZk/Image-28.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
We want to set the Network adapter to internal Network: <br/>
<img src="https://i.postimg.cc/YSNRzzTC/Image-29.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Start the VM and begin installation process: <br/>
<img src="https://i.postimg.cc/zGZT2RCb/Image-30.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
You will see this screen when the setup is successful: <br/>
<img src="https://i.postimg.cc/ZYvcfmGQ/Image-31.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Set up the IP and I set it to use 192.168.1.2 and 192.168.1.1 as gateway: <br/>
<img src="https://i.postimg.cc/7ZjPng0d/Image-32.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Go to Server Manager -> add roles and features and proceed with installing Active Directory Domain Services: <br/>
<img src="https://i.postimg.cc/4y4XxwR7/Image-33.png" height="80%" width="80%" />
<br />
<br />

<p align="Center">
Keep other setting as default and  click close: <br/>
<img src="https://i.postimg.cc/GtMTLHVR/Image-34.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Now at the top right corner click on the exclamation mark and Click Promote this server to a domain controller: <br/>
<img src="https://i.postimg.cc/FRz4tzy3/Image-35.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Set the domain as follows: <br/>
<img src="https://i.postimg.cc/g2GcSYTq/Image-36.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Set the password and checked the DNS server: <br/>
<img src="https://i.postimg.cc/ncptZ3Gn/Image-37.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Set the NetBIOS name as SOC and keep other configuration as default and click next and install: <br/>
<img src="https://i.postimg.cc/NFbCQkQ0/Image-38.png" height="80%" width="80%" />
<br />
<br />

Now we have Active Directory Server, We will use BadBlood to populate the AD with misconfiguration so we can do analysis:
<br />
<br />
-Download it on the AD ( in this case I have pre-downloaded the Bad Blood and put it on my Desktop folder)

-Extract it

-Launch Powershell as administrator

-Go to Badblood folder

-Launch Invoke-BadBlood.ps1


<p align="Center">
 <br/>
<img src="https://i.postimg.cc/ThM1Yg0Z/Image-39.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Proceed with Bad Blood Installation: <br/>
<img src="https://i.postimg.cc/rpPr206L/Image-40.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
At the end of the installation you can run the following command to get the number of User and Group created by Bad Blood: <br/>
<img src="https://i.postimg.cc/KYR1fG1p/Image-41.png" height="80%" width="80%" />
<br />
<br />

  End of Active Directory Setup 
<br />
<br />
<p align="Center">
Create our Workstation( I will be using Windows 10 for this lab): <br/>
<img src="https://i.postimg.cc/wB6Vjsby/Image-42.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Proceed with installation: <br/>
<img src="https://i.postimg.cc/MKVNcVtd/Image-43.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Once set up complete, set the Network IPv4 : <br/>
<img src="https://i.postimg.cc/zftcmjXX/Image-44.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Rename the PC and domain joined the PC: <br/>
<img src="https://i.postimg.cc/kg5NrdVK/Image-45.png" height="80%" width="80%" />
<br />
<br />

<p align="Center">
You will get this notification once it's successful and reboot the machine: <br/>
<img src="https://i.postimg.cc/q7svjNkL/Image-46.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Go back to the system properties and you will see soc.lab as domain : <br/>
<img src="https://i.postimg.cc/d0y4XKXn/Image-47.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Download Sysmon to the workstation to monitor and log system activity: <br/>
<img src="https://i.postimg.cc/xTZGS4LZ/Image-48.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Installed Sysmon via powershell: <br/>
<img src="https://i.postimg.cc/8CN78RX3/Image-49.png" height="80%" width="80%" />
<br />
<br />

Pre-Requisite: Make sure you have created a free account in Crowd Sec
<p align="Center">
The next step is to install crowd sec, you want to install this on both your AD server and workstation, download the msi file: <br/>
<img src="https://i.postimg.cc/QCQMnVks/Image-51.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Download and start the .msi file: <br/>
<img src="https://i.postimg.cc/PJ2gxjdY/Image-52.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
  Click Finish
 <br/>
<img src="https://i.postimg.cc/651q4g0f/Image-53.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
  Go to Crowdsec folder under program files:
 <br/>
<img src="https://i.postimg.cc/1z0yBjpT/Image-54.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
  Run powershell as admin from this folder and run the following command:
 <br/>
<img src="https://i.postimg.cc/5Nv9jyXb/Image-55.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Open the acquis.yaml file in "C:\ProgramData\CrowdSec\config" and add the following : <br/>
<img src="https://i.postimg.cc/sXkdRP9S/Image-56.png" height="80%" width="80%" />
<br />
<br />
<p align="Center">
Login to your CrowdSec account and under the security engines and follow the instruction to install the agent, once you install the agent you will be able to see the machine in AD : <br/>
<img src="https://i.postimg.cc/yxHQPLyf/Image-57.png" height="80%" width="80%" />
<br />
<br />

<h2> End of Soc Home Lab and have fun with it</h2>

