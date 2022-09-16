## Creating a Server Template in VMware Workstation

00. Have VMware Workstation installed and enough hard drive space to create several virtual machines

01. Download the [Windows Server 2022 Evaluation](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)

02. Configure a new virtual machine as follows:
	- Select a typical configuration
	- For "Guest Operating System Installation," choose to install the operating system later
	- _Select a Guest Operating System_
		- Microsoft Windows
		- Windows Server 2019
	- Name your virtual machine whatever you'd like, I chose _Base Server (Windows Server 2022)_ as I plan to use the initial install as a template to clone from
	- I left the maximum disk size as the default, it's only a lab and I don't need to create a huge file
	- **Before you click finish**
		- Customize the Hardware
			- _New CD/DVD (SATA)_ select the ISO for the evaluation under _Use ISO image file:_
			- _Network Adapter_ set to _Host-only_, we don't want our lab exposed to the network

03. Power on the virtual machine to begin installing Windows Server 2022

04. For added difficulty, and to force myself to learn PowerShell commands for server administration, I opted to restrict the installation to Server Core with no Desktop Experience

05. After installation completes you'll be prompted to enter a password

06. In the **VMware Workstation** menu, select _VM_ > _Install VMware Tools_ to load them into the D: drive

07. Run the following PowerShell command to install VMware Tools silently
```shell
D:\setup64.exe /S /v "/qn REBOOT=R ADDLOCAL=ALL"
```

08. Power off the virtual machine, edit its settings and go to _Options_ > _Advanced_ to select **Enable Template Mode (to be used for cloning)**

09. Right click on the machine in the library, and create a snapshot