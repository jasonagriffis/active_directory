## 01 Installing the Domain Controller

PowerShell commands used to configure the DC1 server:

This will find the Active Directory Role so we know the proper name
```shell
Get-WindowsFeature | ? {$_Name -like "AD*"}
````