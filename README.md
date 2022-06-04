# Follina zero day office exploit patch for Windows 10
Patch for the Follina zero day exploit currently effecting MS Office. This patch works on Windows 10, I have not tested it on previous versions of Windows.
The exploit this is patching DOES effect earlier versions of Windows (Both Desktop and Server) so be careful. 

## Patch Notes/Instructions

##### (CVE-2022-30190 - disable the Preview pane)
##### First, make sure to disable the Preview pane in Windows
It is strongly advised to disable the Preview pane in Windows Explorer to remove this attack vector, to do so, follow these instructions: 

1) Open File Explorer.
2) Click on View Tab.
3) Click on Preview Pane to view\hide it.

##### (CVE-2022-30190 - msdt child process)
Make sure to kill the child process if it is currently runnning on your computer. 
This can be done via Task Manager (CTRL+SHIFT+ESC) -> Services (Tab) and Stop the msdt service from running

##### (CVE-2022-30190 - disable msdt)
##### Second, unregister msdt (script included as well as manual instructions)

https://github.com/hereticerik/follina-patch/blob/main/unregister-msdt.reg 
unregister-msdt.reg - Unregister ms-msdt to protect against recent office 0day exploit "Follina".

If you'd like to do this manually without running this registry fix:
1) Run Command Prompt as Administrator.
2) To back up the registry key, execute the command "reg export HKEY_CLASSES_ROOT\ms-msdt ms-msdt.reg"
3) Execute the command "reg delete HKEY_CLASSES_ROOT\ms-msdt /f"

Reboot after this patch and you should be good to go for Windows 10
