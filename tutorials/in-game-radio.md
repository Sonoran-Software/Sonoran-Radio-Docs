---
title: In-Game Radio Script
description: These are in the instructions for installing and using the in-game radio script.
published: true
date: 2021-11-11T03:52:39.633Z
tags: 
editor: markdown
dateCreated: 2021-10-07T04:57:05.274Z
---

# Radio Script Installation
## Installation Video
Our installation tutorial video is coming soon.
## Installation Guide
1. Download Release

	Download the [latest zip file](https://download.sonoransoftware.com/sonoranradio/archive/latest.zip) for the resource.
  
2. Extract the .zip file into your resources directory. Place the sonoranradio and sonoranradio_updatehelper into a folder labeled [sonoranradio]
  
3. Server Config

	Add the following to your `server.cfg`:

```
ensure sonoranradio

# permissions for auto-updater (REQUIRED)
add_ace resource.sonoranradio command allow
add_ace resource.sonoranradio_updatehelper command allow
``` 

>   It is very important that the `sonoranradio_updatehelper` resource is not started manually. Doing so may cause a server crash if updates are available due to a race condition.
>
> **DO NOT** start the whole [sonoranradio] folder as that will also start the sonoranradio_updatehelper which might cause crashing if started manually.
>
> Example of what NOT to do:
> `ensure [sonoranradio]`
{.is-danger}

## Updates
The Sonoran Radio in-game resource will automatically update with the latest features, fixes, and changes upon server restart!

## Commands
| Command | Description 								|
| ------- | --------------------------- |
| `/radio`  | Opens the radio Interface.	|

# Usage
When you have the script installed on your server, you can use the `/radio` command to display the radio interface. If you have the TeamSpeak plugin installed and are in an appropriate patrol channel, the radio will display a connected status.

Once the radio displays a connected status, you can now use the radio interface to change your preset channels, as well as add or remove scanned frequencies from your scan list.

## Changing Frequency
To change frequency using the radio, click on the box that has the name of the channel that you are connected to, as well as the frequencies associated with that preset. If those frequencies don't match a preset the radio will display `Custom Frequency`. When you click on that display, you will see a list of available presets that you can choose from. You can either select a preset from that list or you can click `Custom` to create your own pair of frequencies.

## Modifying Scan List
To add a frequency to your scan list, click on the Scan List button on the radio screen. This will display the frequencies that you are currently scanning.

If you want to add the current receieve frequency to the scan list, click on the `+` button on the top of the Scan List screen. To remove a scanned frequency from the screen, click on the `x` button next to the frequency to remove it from the Scan List.

## Sonoran CAD Integration
For use of the panic button, unit status, and call information section, check out our [Sonoran CAD integration](https://info.sonorancad.com/integration-plugins/integration-plugins/available-plugins/sonoran-radio-sonrad).
