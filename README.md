# LSUClient-Orchestrator
A front end GUI for LSUClient written in Clickteam Fusion 2.5

LSUClient Orchestrator is a front-end for Jantari's LSUClient PowerShell module (https://github.com/jantari/LSUClient) for managing Lenovo patches and updates on Lenovo computers running Microsoft Windows 10 and above.
DISCLAIMER: I wrote this tool in my spare time to make it easier to work with the LSUClient PowerShell module. I am merely a hobbyist scripter who has a full time career as a Network Admin. I AM NOT RESPONSIBLE FOR ANYTHING THAT CAN GO WRONG WITH THIS SCRIPT IN YOUR ENVIRONMENT SHOULD YOU CHOOSE THE RISK TO USE IT IN YOUR PRODUCTION ENVIRONMENT. I AM NOT RESPONSEABLE FOR LOSS OF DATA, FUNDS OR PRODUCTIVITY IF YOU CHOOSE TO RUN THIS IN YOUR'S OR YOUR ORGANIZATIONS ENVIRONMENT IF SOMETHING DOES GO WRONG. 
You will be on your own.
License:
There isn’t one. You are free to take this code and modify it as you please, the binary for the GUI is already complied into EXE for instant use. But if you have Clickteam Fusion 2.5 you can modify the source .mfa file anyway you would like. The rest of the modules are written in Windows Batch or PowerShell. You can sell this as your own product or incorporate it into one of your own products, I do not care.
This GUI allows a degree of customization through registry settings once it is installed with the installer batch script, setup.bat. You can choose to use the default registry settings included or run the setup.bat installer with the 2nd parameter after it -NODEFAULTSETTINGS to forgo the defaults and allow any registry settings you push through group policy, an RMM or a script to take place of the defaults.

Installation Examples:
setup.bat can be run with the follow examples to install on a machine:
setup.bat - installs with desktop icon and default registry settings
setup.bat -NODESKTOPICON -NODEFAULSETTINGS - installs without a desktop icon and without default registry settings loaded
setup.bat NULL -NODEFAULTSETTINGS - installs without default registry settings
setup.bat -NODESKTOPICON - installs without a desktop icon
How To Uninstall:
Uninstall.bat will remove the LSUClient Orchestrator tool from your machine. Or you can go into Control Panel and then Add/Remove programs to uninstall it.
Explanation of Registry Settings:
[HKEY_LOCAL_MACHINE\SOFTWARE\LSUOrch]
"LoggingEnabled" – If set to 1 logging is enabled. 1 is default.
"DeleteLogDays" – Delete logs older than X amount of days. 30 is default.
"Rounds" – How many update rounds the LSUClient module should perform. Default is 3.
"NotifyUser" – Notify the current user of updates, pending reboots or installs via msg.exe. Default is 0, disabled.
"DisableUpdates" – Disable installing or checking updates. Default is 1, enabled.
"DeadlinesEnabled" -Enable installation deadlines on any new updates received. Default is 0, disabled.
"DeadlineDays" -Set X number of days from time new updates are discovered to when they should be forced to install. Default is 0.
"ConfigLock" -Lock users from being able to change these registry settings through the GUI. This applies to both users and administrators in windows. If set to 1, enabled, you will need to change your settings from ether group policy or an RMM only, unless you set this value back to 0 via group policy, an RMM, a script or regedit.

