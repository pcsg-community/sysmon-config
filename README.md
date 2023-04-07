![pcsg-community-full-logo-sysmon](https://user-images.githubusercontent.com/58658008/229286833-0e6b0600-afdc-4ff2-8ee0-021f49e80835.gif)

**The "PCS Girls Community" presents:**

## A) Summary

Sysmon has two configuration type:

1- Targetting: These configuration's will collect logs of special events and useful for Threat Hunting

2- Tracking: These configuration's will collect more logs (also some noisy logs) to fill dashboards abd useful for SOC and correlation engines.



I create this mixed configuration. I fork sysmon modular and then mix it with other fork's and my knowledge about detection and threat hunting.

*Significant: This configuration contains the protection channel which is called "FileBlockExecutable" and is generated when Sysmon detects and blocks the creation of executable files , Event ID= 27.

*Note: This configuration will raise your events (5x of sysmon modular default configuration), so be careful and re-calculate your license, resource's data lifecycle policie's.*



## B) Fork Information

Florian Roth @Neo23x0

Tobias Michalski @humpalum

Christian Burkard @phantinuss

Nasreddine Bencherchali @nas_bench



## C) Installation (and make it secure)

We want to install sysmon a little different to protect it more. so we will change process name from "sysmon" to "pcsgmon", change drive name to "pcsgdrv" and change service name to "pcsgservice". follow the example:


**1) Get Ready:**

Download last version of Sysmon from [Microsoft](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) or [Sysinternals](https://download.sysinternals.com/files/Sysmon.zip).

Download symon cofig file in here [(Download)](https://github.com/pcsg-community/sysmon-config/blob/main/sysmon-pcsg-daena-default.xml) and copy in you downloaded sysmon folder.

Rename "sysmon64.exe" or "sysmon.exe" to another name, to hide it (with different name) in process list. for example we rename "sysmon64.exe" to "pcsgmon.exe"


**2) Installation**

Run powershell or cmd with Admin Rights (Run as Admin) and change path to your sysmon folder

Install command: `pcsgmon.exe -accepteula -i "sysmon-pcsg-daena-default.xml" -d pcsgdrv`


**3) Change Service**

After install, open "regedit.exe" and go to `Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\pcsgmon`

Now change DisplayName: PCSG Service

And change Description: Enables PCSG process live



*also you can use these steps for your SIEM agent installation*



## Z) Community

👩‍💻 Join Our Community: #PCSGCommunity

Post by Daena: [github.com/Daenaa](https://github.com/Daenaa)

Telegram: [t.me/persiancsgirls](https://t.me/persiancsgirls)

LinkedIn: [linkedin.com/groups/12007305](https://linkedin.com/groups/12007305)
