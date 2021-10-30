---
title: Installing the TeamSpeak Plugin
description: Download the TeamSpeak plugin and integrations here!
published: true
date: 2021-10-30T23:08:30.308Z
tags: 
editor: markdown
dateCreated: 2021-10-05T05:02:14.308Z
---

## 1. Download the Plugin
All community members will need to download the 64 or 32 bit version of the Sonoran Radio TeamSpeak plugin.

- [SonoranRadio_win64.ts3_plugin *64-bit version of the plugin*](https://download.sonoransoftware.com/sonoranradio/archive/SonoranRadio_win64.ts3_plugin)
- [SonoranRadio_win32.ts3_plugin *32-bit version of the plugin*](https://download.sonoransoftware.com/sonoranradio/archive/SonoranRadio_win32.ts3_plugin)
{.links-list}

**Don't know which one to click?** Download both and try them out, you will see the error below if it's not the correct version:
![installer_error.png](https://i.imgur.com/Okf4oUS.png)

## 2. Install the Plugin

![installer.png](https://i.imgur.com/0x3QQ3X.png)

1. Download the plugin by clicking the links above
2. Make sure your TeamSpeak is completely closed
3. Open the installer by double-clicking the download, click `Install`, then click `Yes` in both popups
4. Open TeamSpeak back up and make sure you have the plugin installed and started
  a. This can be checked in `Tools -> Options -> Addons`
  
## Manual Install Instructions (Advanced)

1. Download the plugin using the the links above.
2. Rename the file from `SonoranRadio_winxx.ts3_plugin` to `SonoranRadio_winxx.zip`
3. Open the zip file with favorite archive opener (i.e. WinRAR or 7z)
4. Make sure TeamSpeak is completely closed
5. Drag all contents of the `plugins` folder in the archive to `%AppData%\TS3Client\plugins`
6. Open TeamSpeak back up and make sure you have the plugin installed and started
  a. This can be checked in `Tools -> Options -> Addons`
  
## Important Notes

### C++ Redistributable
Some users may be missing a required C++ redistributable on their PC.
> Plugin failed to load: failed to open plugin.: -834026130 (minimum 23, current: 25)

You can [download and install this package](https://aka.ms/vs/16/release/vc_redist.x64.exe) from Microsoft.

### Task Force Radio

The Sonoran Radio plugin is **not** compatible with the Task Force Arma 3 radio TeamSpeak plugin. It must be disabled or removed for Sonoran Radio to work properly.

### San Andreas Police Radio (SAPR)

TeamSpeak servers configured to use both Sonoran Radio and SAPR will cause compatibility issues. SAPR must be disabled or removed for Sonoran Radio to work properly on that server specifically.
