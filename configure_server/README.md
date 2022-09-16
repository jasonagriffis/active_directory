## Configuring the new Domain Controller

Now that we have a fresh clone-able server, we can use it to create the actual Domain Controller

01. Right click on the template, go to _Manage_ > _Clone_

02. Clone from an existing snapshot

03. Decide whether you'd rather have a linked clone, or full clone

04. Rename the machine to what you want it to be called on your AD Domain, but store it in its own file location

05. Once the machine is finished cloning, power up your new server

06. From the SConfig menu:
	- Choose option 2 to rename the machine from within the operating system
	- Choose option 8 to set a **static** IP address for the server
		- You can sub-net this to your choosing, just make sure you take note so all the machines can communicate together
		- Set the DNS to point at the same IP address you configured

07. Install the Active Directory Domain Services role
	- The following will install the role
	```shell
	Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools
	```
	- Create the AD Forest and Domain
	```shell
	Install-ADDSForest -DomainName <your_domain_name> -InstallDNS
	```
	- You'll be prompted to set a Safe Mode Administrator Password
	- If all goes well, the server will reboot and be the Domain Controller
