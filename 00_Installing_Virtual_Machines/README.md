## 01 Installing the Domain Controller

PowerShell commands used to configure the DC1 server:
```shell
Get-WindowsFeature | ? {$_Name -like "AD*"}
````