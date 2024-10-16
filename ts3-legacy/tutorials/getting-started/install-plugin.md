---
title: Installing the TeamSpeak Plugin
published: true
date: 2023-12-07T20:27:58.631Z
tags: null
editor: markdown
dateCreated: 2021-10-05T05:02:14.308Z
description: Download the TeamSpeak plugin and integrations here!
---

# Installing the TeamSpeak Plugin

## Installation

### 1. Download the Plugin

All community members will need to download the 64 or 32 bit version of the Sonoran Radio TeamSpeak plugin.

{% tabs %}
{% tab title="Windows (64-bit)" %}
[Download Windows 64-bit Plugin](https://download.sonoransoftware.com/sonoranradio/prod/archive/SonoranRadio\_win64.ts3\_plugin)
{% endtab %}

{% tab title="Windows (32-bit)" %}
[Download Windows 32-bit Plugin](https://download.sonoransoftware.com/sonoranradio/prod/archive/SonoranRadio\_win32.ts3\_plugin)
{% endtab %}

{% tab title="MacOS" %}
[Download MacOS Plugin](https://download.sonoransoftware.com/sonoranradio/prod/archive/SonoranRadio\_macos.ts3\_plugin)
{% endtab %}
{% endtabs %}

**Don't know which Windows version to click?** Download both and try them out, you will see the error below if it's not the correct version:&#x20;

<figure><img src="https://i.imgur.com/Okf4oUS.png" alt=""><figcaption><p>Sonoran Radio - Plugin Wrong Version</p></figcaption></figure>

{% hint style="danger" %}
Please note that TeamSpeak 5 is **not** compatible with plugins such as this. If you haven't already, make sure to download and install the [TeamSpeak 3 Client](https://teamspeak.com/en/downloads/#ts3client) first.
{% endhint %}

### 2. Install the Plugin

![Sonoran Radio - Plugin Installer](https://i.imgur.com/xktrfnX.png)

1. Download the plugin by clicking the links above
2. Make sure your TeamSpeak is completely closed
3. Open the installer by double-clicking the download, click `Install`, then click `Yes` in both popups
4. Open TeamSpeak back up and make sure you have the plugin installed and started a. This can be checked in `Tools` > `Options` > `Addons`

### Manual Install Instructions (Advanced)

1. Download the plugin using the the links above.
2. Rename the file from `SonoranRadio_winxx.ts3_plugin` to `SonoranRadio_winxx.zip`
3. Open the zip file with favorite archive opener (i.e. WinRAR or 7z)
4. Make sure TeamSpeak is completely closed
5. Drag all contents of the `plugins` folder in the archive to `%AppData%\TS3Client\plugins`
6. Open TeamSpeak back up and make sure you have the plugin installed and started a. This can be checked in `Tools` > `Options` > `Addons`

## Common Issues

### Plugin failed to load: API version is not compatible

Some users may see an error like this after installing the TeamSpeak plugin:

```
Plugin failed to load: API version is not compatible: 26 (minimum:23, current: 24)
```

This error means that their TeamSpeak client is out of date and needs to be updated to version 3.6 or higher.&#x20;

The TeamSpeak 3.6 update introduced major API changes that required us to rework the plugin, and because of this, plugins made for 3.6 are not backwards compatible with older versions of TeamSpeak.&#x20;

**We strongly recommend updating your TeamSpeak client to the latest version.**&#x20;

If for some reason updating is not possible, you can still download an [archived version](../../archive-downloads.md) that works on pre-3.6 versions of TeamSpeak. _Please be aware that the archive version is not updated or maintained._

## Important Notes

#### Auto-update

When a new update for Sonoran Radio is detected, the plugin will automatically prompt you saying that there is a new update. It is recommended that you install the update ASAP as it can include critical bug fixes.

#### Canary Builds

If you wish to receive early-access updates while helping make Sonoran Radio more stable, you can enable `Canary Builds` in the Settings menu. These builds are not guaranteed to be stable.

#### C++ Redistributable

Some users may be missing a required C++ redistributable on their PC.

{% hint style="danger" %}
Plugin failed to load: failed to open plugin.: -834026130 (minimum 23, current: 25)
{% endhint %}

You can [download and install this package](https://aka.ms/vs/16/release/vc\_redist.x64.exe) from Microsoft.

#### Task Force Radio

The Sonoran Radio plugin is **not** compatible with the Task Force Arma 3 radio TeamSpeak plugin. It must be disabled or removed for Sonoran Radio to work properly.

#### San Andreas Police Radio (SAPR)

TeamSpeak servers configured to use both Sonoran Radio and SAPR will cause compatibility issues. SAPR must be disabled or removed for Sonoran Radio to work properly on that server specifically.

#### Archived Versions

Looking for older versions of Sonoran Radio?

* [Sonoran Radio Archived Versions](../../archive-downloads.md)
