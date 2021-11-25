---
title: FiveM Radio Script
description: How to use the in game radio script
published: true
date: 2021-11-25T05:06:50.099Z
tags: 
editor: markdown
dateCreated: 2021-10-23T14:23:15.408Z
---

# Prerequisites

> Before continuing, it's expected that you've installed the plugin and understand the core concepts of Sonoran Radio.
{.is-warning}

- [Install TeamSpeak 3 Plugin *Each user needs to install this to use the radio*](/tutorials/install-plugin)
- [Install FiveM Radio Script*Allows users to change radio settings in game*](/tutorials/in-game-radio)
- [Core Concepts *Understand the theory of our radio*](/tutorials/core-concepts)
{.links-list}

# Opening the Radio and Keybinds

When you install the script, your users can use and configure the keybinds or commands to open your radio interface and interact with the physical buttons on the outside of the radio.

## Radio Keybinds
![example.png](https://i.imgur.com/NGuXyo9.png)

# Radio Interface

![example.png](https://cdn.discordapp.com/attachments/851253011791609867/913250908622696498/SNAGHTML786d1a.png)

## Turning on/off your Radio

You can click on the dial on the top right of the radio to toggle the radio on and off. You will also see this reflected in the teamspeak interface.

## Radio Status Indicator
The color of the bar next to your current frequency indicates the state of your radio.

- Status Color: Gray 
If you are disconnected from TeamSpeak the indicator will be gray.

- Status Color: Blue 
If you are connected to TeamSpeak, the indicator will be blue.

- Status Color: Green 
If you have configured the [sonrad](https://info.sonorancad.com/integration-plugins/integration-plugins/available-plugins/sonoran-radio-sonrad) correctly and you are logged into the CAD system, the radio status indicator will be green.
When your status indicator is green, your radio panic button will activate your panic through CAD, and you will be able to view basic call information by clicking on the Call Details button.

## Change Frequency

To change your current frequency, either use the dial on the top of the radio, use the keybinds that you set in the Keybinds Menu, or click on the change frequency icon. In the change frequency menu, you can either set a custom frequency or you can select a preset. You can click on either side of the knob on the top of the radio to go to the previous or next preset.

### Using Preset Knob
You can click on either side of the preset selection knob to cycle through preset frequencies. Cycling through next and previous frequencies can also be done via keybind. To set the keybinds, navigate to your game keybinds and set prev and next.

### Using First Preset Button
The button that resembles a house is a new button that you can click to automatically change to the first preset frequency. In future releases this button may be configured on an individual or server-wide basis. For now, the home button will change you to the first preset on your list.

## Add/Remove Scan Frequency

To add frequency to scan list, set your radio to that the frequency you would like to add, click on scan list, and press the plus button. Press the x button next to a frequency to remove from the scan list.

## Integrating With Sonoran CAD

Usage of the Sonoran CAD integrations requires the sonrad plugin for the Sonoran CAD. You can download and install that plugin [here](https://github.com/Sonoran-Software/sonoran_sonrad).

Or, learn more about the Sonoran CAD radio plugin [here](https://info.sonorancad.com/integration-plugins/integration-plugins/available-plugins/sonoran-radio-sonrad).

### Sonoran CAD Panic Button
To activate your panic from your radio, you can use the button on the top of your radio. This button can also be pressed by a keybind that you can set in your FiveM Keybinds.

### Sonoran CAD Call Details
If you have configured your Sonoran CAD [sonrad](https://info.sonorancad.com/integration-plugins/integration-plugins/available-plugins/sonoran-radio-sonrad) plugin correctly, and you are attached to a call, you can click on the "Call Details" button to review the details of the call that you are attached to.
