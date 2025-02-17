---
layout: default
title: Headed/Headless Mode
permalink: /en-US/win10/HeadlessMode.htm
lang: en-US
---

##Headed and Headless mode

Windows IoT Core can be configured for either **headed** or **headless** mode. The difference between these two modes is the presence or absence of any form of UI.  
By default, Windows 10 IoT Core is in **headed** mode and displays system information like the computer name and IP address. 
Furthermore, in the headed mode, the standard UWP UI stack is available for fully interactive apps. 
Devices that don't need UI functionality can be set to **headless** mode. The UI stack is disabled and apps are no longer interactive. Headless mode apps can be thought of as services.

    NOTE: if you put your device into headless mode, use the WindowsIoTCoreWatcher application described below to find its IP address

##Changing the mode
You can modify the headed/headless state of your device from a PowerShell session.  To review the PowerShell details, look [here]({{site.baseurl}}/{{page.lang}}/win10/samples/PowerShell.htm).

* To display the current state of your device, use the `setbootoption` utility like this:

        [192.168.0.243]: PS C:\> setbootoption.exe

* To modify the state of your device to enable headless mode, use the `setbootoption` utility with the `headless` arg:

        [192.168.0.243]: PS C:\> setbootoption.exe headless
        [192.168.0.243]: PS C:\> shutdown /r /t 0

* To modify the state of your device to enable headed mode, use the `setbootoption` utility with the `headed` arg:

        [192.168.0.243]: PS C:\> setbootoption.exe headed
        [192.168.0.243]: PS C:\> shutdown /r /t 0


##Finding your headless device

A Windows IoT Core device that is in headless mode can be discovered using the **WindowsIoTCoreWatcher** application that is installed with the Windows 10 IoT Core tools.
When run, the application automatically finds all Windows IoT Core devices on the local network and displays device information such as the name, MAC, IP address, and more.

![Windows IoT Core Watcher]({{site.baseurl}}/images/HeadlessMode/IoTCoreWatcher.png)