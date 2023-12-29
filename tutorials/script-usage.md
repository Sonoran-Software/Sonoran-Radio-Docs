---
title: FiveM Radio Script
description: How to use the in game radio script
published: true
date: 2023-12-29T23:32:06.286Z
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
![radio-keybinds.png](/tutorials/script-usage/nguxyo9.png)

# Radio Interface
![radio-interface.png](/tutorials/script-usage/4ardn0u.png)

## Turning on/off your Radio

You can click on the dial on the top right of the radio to toggle the radio on and off. You will also see this reflected in the teamspeak interface.

## Repositioning the Radio

To move the radio on your screen to a more suitable position, you can click the `Config` button with the radio open, then click `Reposition UI`.

![radio-reposition.png](https://i.imgur.com/3nMYJTV.png)

## Changing the Radio Frame 

To change your radio frame, you can click on the `Config` button with the radio open and then select radio frame options from the list shown. If your list shows as empty this is due to you not having permissions to access any addiontional frames. 

### Radio Frame Configuration 

Located in your `config.lua` you'll see a section titled `Config.frames`. You can first start with selecting your `permissionMode`, Viable options are "`ace`", "`qbcore`", "`esx"`. Additionally you can configure your `adminPermission`, this is an [ace permission](https://forum.cfx.re/t/basic-aces-principals-overview-guide/90917). The departments array is where you can configure your frames per department, below you can see the guide to this array. 

#### Radio Frame Configuration cont.

```lua
	departments = {
		['DEPT_ABBREVIATION'] = {
			label = 'DEPARTMENT NAME',
			permissions = {
				jobs = { -- Jobs that can use this department
					['police'] = {
						grades = { -- Job grades that can use this department
							1,
							2,
							3
						}
					}
				},
				ace = { -- ACE Permissions that can use this department | ONLY EFFECTIVE IN ACE PERMISSION MODE
					'sonoranradio.sahp'
				}
			},
			-- Radio frames that can be used by this department
			allowedFrames = {
				'default',
				'signalpro',
				'voxguard',
        'hi-vis'
			}
		}
	}
```
Available frames can be found by their folder names in the `/skins` folder. Default frames are:
 - `default`
 - `hi-vis`
 - `signalpro`
 - `voxguard`
 
 ### Radio Frame Commands
 - `adminskinchange` - Used to change the radio skin to any skin, regardless of config. Requies the `Config.frames.adminPermission` [ace permission](https://forum.cfx.re/t/basic-aces-principals-overview-guide/90917) to use. 
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

## 📡 Modifying In-Game Towers
Our custom in-game towers allow you to dynamically place repeaters around the map, customize the signal range, and more!

[Learn more about tower configuration](/tutorials/in-game-radio#modifying-in-game-towers)!

# In-game Towers

![tower.jpeg](/tutorials/script-usage/po2e6mz.jpeg)

## Locations

Tower locations are controlled by the server owner, and they may not always disclose the location of their towers. Look out for signal towers that look like the above and have the Sonoran Radio logo on the top dish!

## Destroying a Tower

If enabled, towers are able to be destroyed by anyone in server with weapons. By shooting the four dishes half-way up the tower, you are able to disable them one-by-one. As more dishes get destroyed, the more the tower's performance is impacted.

![shooting.jpeg](/tutorials/script-usage/5tp9vms.jpeg)

## Repairing a Tower

Once a tower is either partially or completely destroyed, anyone is able to locate and repair that tower. To repair, go near the ladder and cable at the bottom of the tower, and a popup will show telling you to press `G` to repair.

![repair.png](/tutorials/script-usage/rqn1ped.png)

# QB Core Radio Item

If you set the configuration option `Config.enforceRadioItem = true` the radio will only operate if the player has the "Radio" item in their QBCore inventory. When you enable this option, you will need to disable the `qb-radio` script as the two scripts will conflict. When the player has the radio item, they can use the `/radio` command or "Use" the item from the inventory by dragging it to the "Use" button or double clicking on it. When the radio item is in the hotbar of the inventory, you can also use the hotkey to open the radio.

# Sonoran Radio Top Down HUD (experimental)

You can bring up the Sonoran Radio HUD using the command `/radiohud [size]`. Currently supported sizes are `large` and `medium`. You can use the command `/radiohud off` to disable the radio HUD. More sizing and movement of the radio UI will be coming soon, however please feel free to try it out and report any problems that you encounter.
