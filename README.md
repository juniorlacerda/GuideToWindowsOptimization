![Windows logo](https://cdn.discordapp.com/attachments/745657576779415666/1086782666499690536/windows.png)
# Guide to Windows Optimization
Windows Optimization Guide: Tips and Tricks to Improve Performance

**Note:** This guide aims to assist you in optimizing your Windows system to reduce issues such as lag, stuttering, and others. It is important to keep in mind that any changes made to your system are your own responsibility and may come with associated risks. Therefore, it is strongly recommended that you exercise caution and fully understand the potential impact of each optimization before implementing it.

### To get started, follow these steps to create a System Restore Point on Windows:

1. Click on the Start button and type "Create a restore point" in the search bar.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a8d3bc63-188f-4704-8669-e392e7c5f85a/Untitled.png)
    
2. Click on the "Create a restore point" option from the search results.
3. The System Properties window will open. Click on the "Create" button under the "System Protection" tab.
4. Enter a name for the restore point and click on the "Create" button.
5. The restore point will be created and you will receive a confirmation message.

Creating a System Restore Point is a good idea before making any major changes to your system, as it allows you to revert to a previous state if anything goes wrong.

---

### Disabling unnecessary services on Windows can significantly enhance system performance and reduce resource usage, leading to a more efficient and stable operating environment.

**Here are the steps to disable unnecessary services on Windows:**

1. Open the "Services" application by pressing "Windows key + R" and typing "services.msc" in the Run dialog box. Click "OK" or press "Enter."
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5d2f9c23-733d-41bc-9441-a51fb84d0238/Untitled.png)
    
2. In the "Services" window, locate the service you want to disable. You can sort the list by "Startup Type" to find services that start automatically.
3. Right-click on the service and select "Properties."
4. In the "Properties" window, select the "General" tab.
5. Under "Startup type," select "Disabled" from the drop-down menu.
6. Click "Apply" and then "OK" to save the changes.

Be careful when disabling services as some services are critical for the proper functioning of the system. If you are unsure about a service, it's best to leave it running.

---

### Here are some Windows settings that you can disable to enhance system performance:

1. **Disable visual effects:**
    - Go to Settings > System > Display.
    - Under "Scale and layout", select "Advanced scaling settings".
    - Toggle off "Use text scaling".
    - Under "Scale and layout", select "Advanced display settings".
    - Set the "Resolution" to the recommended value.
    - Under "Advanced display settings", select "Display adapter properties".
    - Select the "Monitor" tab and set the screen refresh rate to the highest available value.
    - Select the "Adapter" tab and click on "List all modes".
    - Select the highest resolution and refresh rate available.
2. **Disable notifications:**
    - Go to Settings > System > Notifications & actions.
    - Toggle off "Get notifications from apps and other senders".
3. **Disable background apps:**
    - Go to Settings > Privacy > Background apps.
    - Toggle off the apps you don't want to run in the background.

Remember to exercise caution when making changes to your system and ensure you understand the implications of any changes before making them.

---

### Here are some commands you can use to check and clear your Windows system:

1. **Check disk for errors:**
    - Open Command Prompt as administrator and run the command:
    `chkdsk C: /f /r /x`
    This will check the C drive for errors and fix any issues it finds.
2. **Clear DNS cache:**
    - Open Command Prompt as administrator and run the command:
    `ipconfig /flushdns`
    This will clear the DNS cache and help resolve network issues.
3. **Clear Windows update cache:**
    - Open Command Prompt as administrator and run the command:
    `net stop wuauserv`
    This will stop the Windows Update service.
    - Go to the following folder:
    `C:\Windows\SoftwareDistribution\Download`
    - Delete all the files and folders inside the Download folder.
    - Go back to Command Prompt and run the command:
    `net start wuauserv`
    This will start the Windows Update service.
4. **Clear Windows Store cache:**
    - Open Command Prompt as administrator and run the command:
    `wsreset.exe`
    This will reset the Windows Store cache and clear any corrupted data that may be causing issues..
5. **Clear temporary files:**
    - Open Command Prompt as administrator and run the command:
    `Remove-Item -Path "$env:TEMP\*" -Recurse -Force`
    This will delete all files and subfolders within the system's temporary folder.

Remember to exercise caution when running these commands and ensure you understand what they do before executing them.

---

### Below are some PowerShell commands that you can use to optimize your Windows system:

1. **Disable Windows search indexing service:**
    - Open PowerShell as administrator and run the command:
    `Get-Service -Name WSearch | Set-Service -StartupType Disabled`
2. **Disable Windows tips and tricks:**
    - Open PowerShell as administrator and run the command:
    `Set-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager" -Name "SystemPaneSuggestionsEnabled" -Value 0`
3. **Disable automatic updates:**
    - Open PowerShell as administrator and run the command:
    `Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" -Name "NoAutoUpdate" -Value 1`
4. **Disable telemetry and data collection:**
    - Open PowerShell as administrator and run the command:
    `Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DataCollection" -Name "AllowTelemetry" -Value 0`
5. **Disable Superfetch service:**
    - Open Command Prompt as administrator and run the command:
    `sc config SysMain start= disabled`
    This will disable the Superfetch service and improve system performance.
6. **Disable hibernation:**
    - Open PowerShell as administrator and run the command:
    `powercfg -h off`
7. **Disable system activity monitoring:**
    - Open PowerShell as administrator and run the command:
    `Get-Service -Name 'DiagTrack' | Stop-Service`
    `Set-Service -Name 'DiagTrack' -StartupType Disabled`

Remember to use caution when running PowerShell commands and ensure you understand what they do before executing them.

---

### Here are some extra commands that you can use to optimize your Windows system:

1. **Check system files for errors:**
    - Open Command Prompt as administrator and run the command:
    `sfc /scannow`
    This will check your system files for errors and fix any issues it finds.
2. **Clean up Windows image:**
    - Open Command Prompt as administrator and run the command:
    `dism /online /cleanup-image /startcomponentcleanup`
    This will clean up your Windows image and free up disk space.

Remember to exercise caution when running these commands and ensure you understand what they do before executing them.

---

### Here is a PowerShell command that you can use to modify your Windows power plan:

**Use the following PowerShell command to switch your Windows power plan to Performance:**

- Open PowerShell as administrator and run the command:
`powercfg -setactive 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c`
This will configure the active power plan to Performance mode.
Remember to run PowerShell as an administrator to execute this command.
