## Configure a Template for Windows 11 Workstations

01. Download the [Windows 11 Evaluation](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)

02. Create a new virtual machine, Windows 10 or higher, name it whatever you'd like your template to be named

03. Before powering the machine on, open the configuration settings so we can make the VM compatible to run Windows 11
	- Go to the _Options_ tab, choose _Access Control_ to encrypt the system, you'll have to choose a password
	- Under _Advanced_, select to _Enable Template mode_ and lower down _Enable Secure Boot_ in the UEFI options
	- Back on the _Hardware_ tab choose _Add..._ and pick the _Trusted Platform Module_ make sure you have at least 4 cores on the processor and a minimum of 8 GB of RAM
	- _Don't forget to set the ISO image into the CD/DVD drive_

04. Power on the VM, and install Windows 11 and configure the local admin account, install VMware Tools once that's completed

05. Power off the VM and create a snapshot of the initial installation