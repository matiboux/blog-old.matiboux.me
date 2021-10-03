---
layout: post
title: Matiboux's Windows installation and configuration guide
date: 2021-10-03
last_updated: 2021-10-03
categories: [blog]
tags: [Windows]

excerpt: "A step-by-step installation and configuration guide for Windows."
---

This is a step-by-step installation and configuration guide for Windows.
This guide is based on my personal experience and preferences and may be incomplete, but it does -- at least in my
opinion -- give some good advices and good practices in how to configure Windows.

Table of contents:

- [Windows installation phase](#windows-installation-phase)
- [Windows setup phase](#windows-setup-phase)
- [Windows configuration phase](#windows-configuration-phase)
- [User configuration](#user-configuration)
  - [Settings](#settings)
  - [File explorer](#file-explorer)
  - [Personalize the taskbar](#personalize-the-taskbar)
  - [Uninstall default apps](#uninstall-default-apps)
- [Developer configuration](#developer-configuration)
  - [Settings](#settings-1)
  - [Enable Windows Subsystem for Linux](#enable-windows-subsystem-for-linux)
- [Upgrade to Windows 11](#upgrade-to-windows-11)
  - [Settings](#settings-2)
  - [Uninstall default apps](#uninstall-default-apps-1)
- [Apps installation](#apps-installation)
  - [Matiboux's apps list](#matibouxs-apps-list)
  - [Matiboux's taskbar pinned apps](#matibouxs-taskbar-pinned-apps)

## Windows installation phase

Before installing Windows, you'll a Windows installation support: either a CD or USB drive.

You can make a installation USB drive yourself using Microsoft's MediaCreationTool. For this, you'll need administrator
access to another Windows computer and a 8GB or more USB drive. Here are the settings I used:

- Language: English (United States)
- Windows: Windows 10
- Architecture: x64

Now it is time to boot your new computer on your the Windows installation support.

On the first page:

- Set "Language" to "English (United States)"
- Set "Time format" to "French (France)"
- Set "Keyboard input" to "French"

Continue.

- Click on "I don't have a license key" when you're prompted about activating Windows.
- Select your Windows version. Usually, you'd choose Windows 10 Home or Windows 10 Pro.
- Agree to terms and conditions.
- Select the "Custom" installation (for a fresh install).

On the page prompting where to install Windows:

- Choose the disk on which you want to install Windows.
- Delete all unwanted partition on this disk, including reserved and recovery partitions.
  For reinstalling on a disk that had a single partition for the system, you would delete all partitions.
- Select the Unallocated space on your disk
- Click on "New", leave the maximum size and confirm.
- Select the largest newly created partition on your disk.
- Click on "Next"

Now wait for the installation to complexe and for your computer to reboot.


## Windows setup phase

If everything goes well, your computer should boot directly your new Windows installation.
If not, reboot and force your BIOS to boot on your new Windows installation.

- Select your region: "France"
- Select your keyboard layout: "French" (AZERTY)
- Optionnally, you can add another keyboard layout. I added a QWERTY US layout.

For Windows 10 Pro installations, select your installation type. For me, I'll select "Set up for personal use".

Now you'll be prompted to create an administrator account:

- Select to create an "Offline account" (if applicable)
- Click on "Limited experience" to continue.
- Choose a username.
- Choose a password.
- Choose your security questions.

For all privacy settings, select "no". For the "diagnostic data", select "Required".


## Windows configuration phase

After the setup, you'll be logged into your administrator account.

If you're prompted about using Microsoft Edge, just say no.

Now it's time to configure Windows. There are some important settings to review using your administrator account:

In the <u>"System"</u> settings:
- In "Remote desktop": _it requires to be logged as an administrator to edit._
  - Disable "Remote Desktop" unless required for you.

In the <u>"Accounts"</u> settings:
- In "Family & other users":
  Create a standard user account for your daily use (recommended).
  - Click on "Add someone -else to this PC".
  - Select to create an "Offline account".
  - Choose a username.
  - Choose a password.
  - Choose your security questions.

In the <u>"Search"</u> settings:
- In "Searching Windows": _it requires to be logged as an administrator to edit._
  - Select the "Enhanced" indexing method (may not be recommended for a laptop).

In the <u>"Update & Security"</u> settings:
- In "Windows Update":
  - Click on "Check for updates"
- In "Windows Security":
  - Review problems and all settings.
  - In "App & browser control":
    - In "Reputation-based protection":
      - Enable "Potentially unwanted app blocking".
  - In "Device Security":
    - In "Core isolation":
      - Enable "Memory integrity"
    - In "Security processor details":  
      Verify that the Trusted Platform Module (TPM) is enabled.
- In "Activation":  
  You might want to activate Windows now, but you can do it later.
  However, activating Windows is required if you want to access all personalization settings.
- In "Find my device": _it requires to be logged as an administrator and into a Microsoft account to edit._
- In "Windows Insider Program": _it requires to be logged as an administrator to edit._  
  You can enable the Insider program here if you want.

Now, if you want to configure your administrator user account, you can check the full instructions for the user
configuration in the next section.

After this, if you created a standard user account, you can log into that account and configure it as well.


## User configuration

### Settings

Time to sign into your Microsoft account:

- Enter your email address
- Enter your password and 2FA code (if applicable)
- Enter your local Windows user password
- Let Windows sync your settings

If you have the "Get more out of Windows" message, open it:

- In "Use recommended browser settings":
  - Select "Don't update your browser settings"

If you want to configure "OneDrive", click on "Sign in" below it:

- Enter your Microsoft account email address.
- Select the OneDrive folder location.
- Deselect "Desktop", "Documents", "Pictures" for sync.
- Skip the tutorial.
- Click on "Later" when prompted about the mobile app.
- Click on "Open my OneDrive folder" to finish and verify its content.

In the <u>"System"</u> settings:

- Display : Rien à changer
- Sound : Rien à changer
- Notifications & actions :
  - Enable "Get notifications from apps and other senders"
  - Disable "Show notifications on the lock screen"
  - Enable "Show reminders and incoming VoIP calls on the lock screen"
  - Enable "Allow notifications to play sounds"
  - Enable "Show me the Windows welcome experience [...]"
  - Enable "Suggest ways I can finish setting up my device [...]"
  - Enable "Get tips, tricks, and suggestions [...]"
- Focus assist:
  - Select "Priority only"
  - Enable "When I'm suplicating my display"
  - Enable "When I'm playing a game"
  - Enable "When I'm using an app in full screen mode"
  - Enable "Show a summary of what I missed while focus assis was on"
- Power & sleep:
  - Set "When plugged in, turn off after" to "10 minutes"
  - Set "When plugged in, PC goes to sleep after" to "Never"
  - Set "Power mode" to "Best performance" (desktop PC only)
  - _Change Settings page to save changes and come back to "Power & sleep"._
  - In "Additional power settings":
    - Next to the selected power plan, usually "Balanced":
      - In "Change plan settings":
        - In "Change advanced power settings":
          - Set "Hard disk / Turn off hard disk after" to "Never"
          - Verify "Sleep / Sleep after" is set to "Never"
          - Set "Sleep / Hibernate after" to "Never"
          - Verify "Display / Turn off display after" is set to "10 minutes"
    - In "Choose what the power buttons do":
      - _Click on "Change settings that are currently unavailable"_
      - Set "Power button" to "Shutdown"
      - Set "Sleep button" to "Sleep"
      - Disable "Turn on fast startup"
      - Enable "Sleep"
      - Enable "Hibernate"
      - Enable "Lock"
- Storage
  - Enable "Storage Sense"
  - Open "Configure Storage Sense or run it now":
    - Set "Run Storage Sense" to "Every week"
    - Enable "Delete temporary files [...]"
    - Set "Delete files in my recycle bin [...]" to "30 days"
    - Set "Delete files in my Downloads folder [...]" to "Never"
    - Optionally, click on "Clean now"
  - In "Temporary files":
    - Select all temporary files and click on "Remove files"
  <!--- In "Change where new content is save":
    - Set "New apps will save to" to "System (C:)"
    - For all other options, you may choose to select another drive, used for your data.-->
  - In "Optimize Drives":
    - Select the System drive and optimize it
    - Optionally, analyse and optimize the other drives
    - Turn on "Scheduled optimization" and set its frequency to "Weekly"
- Tablet
  - Set "When I sign in" to "Use the appropriate mode for my hardware"
  - Set "When I use this device as a tablet" to "Ask me before switching modes"
- Multitasking
  - Set "Pressing Alt + Tab shows" to "Open windows only"
- Projecting to this PC: nothing in particular, unless supported by your device.
- Shared experiences: nothing in particular
- Clipboard:
  - Enable clipboard history
  - Disable "Sync across devices" (if applicable)
- Remote desktop:
  - _Requires to be logged as an administrator to edit._
  - Disable "Remote Desktop" unless required
- In "About":
  - Click on "Rename this PC" and give your PC a fancy name.
  - In "Advanced system settings":
    - _Requires to enter the admin password._
    - In "Remote":
      - Disable "Allow Remote Assistance connections to this computer"

In <u>"Devices"</u>:

- In "Bluetooth & other devices":
  - Turn off Bluetooth if you're not using it
- In "Printers & scanners": nothing in particular
- In "Mouse": nothing in particular
- In "Typing":
  - Enable all in "Spelling"
  - Enable all in "Typing"
  - _Not sure about enabling suggestions in "Hardware keyboard"_
  - Enable "Multilingual text suggestions"
- In "Pen & Windows Ink": nothing in particular
- In "Autoplay": nothing in particular
- In "USB": nothing in particular

In <u>"Phone"</u>: nothing in particular

In <u>"Network & Internet"</u>:

- In "Status":
  - In "Properties" for the current network's:
    - Set "Network profile" to "Private" if applicable
- In "Ethernet": nothing in particular
- In "Dial up": nothing in particular
- In "VPN": nothing in particular
- In "Airplane mode": nothing in particular
- In "Mobile Hotspot":
  - Change the network settings if this is supported by your device
- In "Proxy": nothing in particular

In <u>"Personalization"</u>:

- In "Background":
  - Customize your background
  - Your background may have been synced with your Microsoft account
- In "Colors":
  - Select "Custom" color mode
  - Select "Dark" as the "default Windows mode"
  - Select "Light" as the "default app mode"
  - Enable transparency effects
- In "Lock screen":
  - Customize your background
  - Customize your apps
- In "Themes": nothing in particular
- In "Fonts": nothing in particular
- In "Start":
  - Enable "Show more tiles on Start" (recommended on desktop PC)
  - Enable "Show app list in Start menu"
  - Enable "Show recently added apps"
  - Enable "Show used apps"
  - Disable "Show suggestions occasionnally in Start"
  - Disable "Show Start full screen"
  - Enable "Show recently opened items in Jump Lists or the taskba and in File Explorer Quick Access"
  - In "Choose which folders appear on Start":
    - Enable "File Explorer"
    - Enable "Settings"
    - Disable "Documents"
    - Disable "Downloads"
    - Disable "Music"
    - Disable "Pictures"
    - Disable "Videos"
    - Disable "Network"
    - Enable "Personal folder"
- In "Taskbar":
  - Enable "Lock the taskbar"
  - Enable "Automatically hide the taskbar in desktop mode"
  - Disable "Automatically hide the taskbar in tablet mode"
  - Disable "Use small taskbar buttons"
  - Disable "Use Peek to preview the desktop [...]"
  - Enable "Replace Command Prompt with Windows Powershell [...]"
  - Enable "Show badges on taskbar buttons"
  - Set "Taskbar location on screen" to "Bottom"
  - Set "Combine taskbar buttons" to "Always, hide labels"
  - Optionally, customize in "Select which icons appear on the taskbar"
  - In "Turn system icons on or off":
    - Enable "Touch keyboard"
    - Enable "Windows Ink Workspace"
    - Disable "Meet Now"
  - Disable "Show contacts on the taskbar"

In <u>"Apps"</u>:

- In "Apps & features":
  - In "Optional features":
    - In "More Windows features":
      - Enable "Windows Subsystem for Linux" (for developers)
      - Do not reboot right away
- In "Default apps":
  - You'll customize this after having installed some apps
  - Keep in mind the "Choose default apps by file type" menu
  - Keep in mind the "Choose default apps by protocol" menu
  - Keep in mind the "Set defaults by apps" menu
- In "Offline maps": nothing in particular
- In "Apps for websites": nothing in particular
- In "Video playback":
  - Enable "Automatically process video to enhance it"
- In "Startup":
  - Disable "Microsoft Edge"

In <u>"Accounts"</u>:

- In "Your info": nothing in particular
- In "Email & accounts": nothing in particular
- In "Sign-in options":
  - Add a Windows Hello sign-in option if you want
  - ~~Enable "Dynamic lock"~~ (causes problems unless you pair a device)
  - Disable "Restart apps"
  - Disable "Show account details [...] on the sign-in screen"
  - Enable "Use my sign-in info to automatically finish setting up my device after an update or restart"
- In "Acces work or school": nothing in particular
- In "Sync your setiings":
  - Enable "Sync settings"
  - Enable all settings

In <u>"Time & Language"</u>:

- In "Date & Time":
  - Set the time zone
  - Enable "Adjust for daylight saving time automatically"
- In "Region":
  - Set "Country or region" to "France"
  - Set "Regional format" to "English (Europe)"
  - Review "Regional format data"
- In "Language":
  - Add the language "French (France)":
    - Install all packages
  - In "French (France)":
    - Verify the installed keyboard layout: "French AZERTY"
  - In "English (United States)":
    - Verify the installed keyboard layout: "US QWERTY"
  - Set "Windows display language" to "English (United States)"
  - In "Keyboard":
    - Select "French (France)" as input method
- In "Speech":
  - Select "French (France)" as speech language
  - Enable "Recognize non-native accents for this langgages

In <u>"Gaming"</u>:

- In "Xbox Game Bar": nothing in particular
- In "Captures": nothing in particular
- In "Game Mode":
  - Enable "Game Mode"
- In "Xbox Management": nothing in particular

In <u>"Ease of Access"</u>:

- In "":
- In "Keyboard":
  - Disable "Allow the shortcut key to start Sticky Keys"
  - Disable "Allow the shortcut key to start Toggle Keys"
  - Disable "Allow the shortcut key to start Filter Keys"
- In "": nothing in particular
- In "": nothing in particular

In <u>"Search"</u>:

- In "Permission & History":
  - Set "SafeSearch" to "Off" (depending on the user)
- In "Searching Windows":
  - _Requires to be logged as an administrator to edit._
  - Select the "Enhanced" indexing method.

In <u>"Privacy"</u>:

- In "General":
  - Enable all settings
- In "Speech":
  - Enable "Online speech recognition"
  - Disable "contributing my voice clips"
- In "Inking & typing personalization":
  - Enable the setting
- In "Diagnostics & feeback":
  - Set to "Optional diagnostic data"
  - Disabled "Improve inking and typing"
  - Disabled "Tailored experiences"
  - Disabled "View diagnostic data"
  - Set "Feedback frequency" to "Automatically"
- In "Activity histoiry":
  - Enable "Store my activity history on this device"
  - Enable "Show activities from these accounts for your Microsoft account (if applicable)
- For all app permissions:
  - Enable the permission for your device
  - Enable "Allow apps to access your [...]"
  - Remove permission to unused apps (like 3D Viewer, Skype, ...)
    - "3D Viewer" has way too much permissions enabled by default
    - "Camera" can keep its access to camera and microphone
    - "Mail and Calendar" can keep its access to contacts, calendar and email
  - Enable "Allow desktop apps to access your [...]"
- In "Voice actiation" (special case):
  - Disable "Allow apps to use voice activation when this device is locked"
  - Disable "Allow apps to use voice activation"
  - Remove permission to unused apps (like 3D Viewer and Skype)
- In "Other devices":
  - Disable "Communicate with unpaired devices"
- In "Background apps": nothing in particular

In <u>"Update & Security"</u>:

- In "Windows Update":
  - Click on "Check for updates"
  - In "Advanced options":
    - Enable "Receive updates for other Microsoft products when you update Windows"
- In "Delivery Optimization":
  - Enable "Allow downloads from other PCs"
  - Select "PCs on my local network"
- In "Windows Security":
  - Review problems and all settings
  - In "App & browser control":
    - In "Reputation-based protection":
      - Enable "Potentially unwanted app blocking"
  - In "Device Security":
    - In "Core isolation":
      - Enable "Memory integrity"
    - In "Security processor details":
      - Verify that the TPM is enabled
- In "Backup": nothing in particular
- In "Troubleshoot": nothing in particular
- In "Recovery": nothing in particular
- In "Activation":
  - Activate Windows if it is not already
- In "Find my device":
  - _Requires to be logged as an administrator into a Microsoft account._

### File explorer

Open the file explorer.

In "This PC":
- Rename the "Local Disk" (C:) to "System"

In the "View" menu:
- Disable "Item check boxes"
- Enable "File name extensions"
- Enable "Hidden files"
- In "Options":
  - Review settings

### Personalize the taskbar

- Right click on the taskbar:
  - In "Search", select "Show search icon"
  - In "News and interests", select "Turn off"
  - Disable "Show Cortana button"
  - Enable "Show Task View button"
  - Enable "Show Windows Ink Workspace button"
  - Enable "Show touch keyboard button"
- Rick click on the "Meet" icon and select "Turn off" (if not disabled already)

### Uninstall default apps

Windows comes with pre-installed apps. You should uninstall the sponsored apps.

Open the start menu and look for apps you don't want to keep.

Apps you want to uninstall might be:
- Office
- Outlook (shortcut)
- Word (shortcut)
- Excel (shortcut)
- PowerPoint (shortcut)
- OneNote
- Skype
- Microsoft To Do
- Microsoft News
- Microsoft
- Spotify
- Roblox
- TikTok
- Hidden City: Hidden Object Aventure
- Photoshop Express
- Dolby Access


## Developer configuration

### Settings

In <u>"Update & Security"</u>:

- In "For developers":
  - _Requires to enter the admin password._
  - Apply File Explorer developer-friendly settings
  - Apply PowerShell developer-friendly "execution policy" setting
- In "Windows Insider Program":
  - You can join the Insider program here.

### Enable Windows Subsystem for Linux

Search and open "Turn Windows features on or off":

- Enable "Virtual Machine Platform".
- Enable "Windows Hypervisor Platform".
- Enable "Windows Subsystem for Linux".
- Reboot your system.

Open Windows Powershell:

- Execute `wsl --set-default-version 2`.

Open the Microsoft Store app:

- Install a Linux distribution (for example: Ubuntu).
- Open the app you installed.
- Configure your UNIX username and password.


## Upgrade to Windows 11

If you enabled Windows Insider in the Beta channel, you might be able to upgrade to Windows 11 via Windows Update.

Once Windows 11 installed, there are some settings you should check again.

### Settings

In <u>"Personalization"</u>:

- In "Taskbar":
  - Disable "Widgets" taskbar item
  - Disable "Chat" taskbar item
  - Set Taskbar alignment to "Left"
  - Enable "Automatically hide the taskbar"

### Uninstall default apps

More default apps will be installed, you might want to uninstall these:

- Microsoft Teams
- Skype
- Messenger
- Line
- Clipchamp
- Adobe Lightroom
- Logiciel de retouche de photos
- Wikipedia
- Whatsapp
- Picsart
- Office
- Tips (Windows 11)
- OneNote for Windows 10
- Snipping Tool


## Apps installation

### Matiboux's apps list

Now it's about time to install your apps.

First, you should install a web browser, unless you want to use Microsoft Edge of course.

Then, you'll be able to install any app you want.

Matiboux's list of apps:
- Web browser:
  - Google Chrome
- Games:
  - Steam
  - Uplay
  - Origin
  - Epic Games
  - Robert Space Industries
  - GeForce Experience
- Productivity:
  - Microsoft Office
  - LibreOffice
- Development:
  - WinSCP
  - PuTTY
  - Notepad++
  - Git
  - TortoiseGit
  - Visual Studio Code
  - Ubuntu 20.04 (WSL)
  - Jetbrains Toolbox (and apps)
  - Python 3
- Multimedia:
  - VLC
  - Stremio
  - qBittorrent
- Social:
  - Telegram
  - Discord PTB
- Image editing:
  - GIMP
- Video editing:
  - Kdenlive
- Tools:
  - CCleaner
  - Recuva
  - TreeSizeFree
  - CrystalDiskInfo
  - HWMonitor
  - Keybase
  - SyncBackFree
  - TeamViewer
  - Fences
  - TheBrain
- Streaming tools:
  - OBS Studio

_This list is incomplete and may be updated later._


### Matiboux's taskbar pinned apps

Pinned apps in my taskbar (in order):

- File explorer
- Notepad
- Google Chrome (or any web browser)
- Steam
- WinSCP
- Notepad++
- Stremio
- Telegram
- Discord
