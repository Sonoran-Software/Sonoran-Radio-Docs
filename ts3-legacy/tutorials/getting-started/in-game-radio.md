---
title: In-Game Radio Script
published: true
date: 2023-12-07T18:46:03.696Z
tags: null
editor: markdown
dateCreated: 2021-10-07T04:57:05.274Z
description: >-
  These are in the instructions for installing and using the in-game radio
  script.
---

# Installing the FiveM Radio Script

## Radio Script Installation

### Installation Video

{% embed url="https://youtu.be/N1k8SseN6ug?t=235" %}

### Installation Guide

1.  Download Release

    Download the [latest zip file](https://download.sonoransoftware.com/sonoranradio/archive/latest.zip) for the resource.
2. Extract the .zip file into your resources directory. Place the sonoranradio and sonoranradio\_updatehelper into a folder labeled \[sonoranradio]
3.  Server Config

    Add the following to your `server.cfg`:

```
ensure sonoranradio

# permissions for auto-updater (REQUIRED)
add_ace resource.sonoranradio command allow
add_ace resource.sonoranradio_updatehelper command allow

# permissions for sonrad tower commands
add_principal group.admin sonoranradio.towers
add_ace sonoranradio.towers command.spawntower allow
add_ace sonoranradio.towers command.savetowers allow
```

{% hint style="danger" %}
It is very important that the `sonoranradio_updatehelper` resource is not started manually. Doing so may cause a server crash if updates are available due to a race condition.

**DO NOT** start the whole \[sonoranradio] folder as that will also start the sonoranradio\_updatehelper which might cause crashing if started manually.

Example of what NOT to do: `ensure [sonoranradio]`
{% endhint %}

### Updates

The Sonoran Radio in-game resource will automatically update with the latest features, fixes, and changes upon server restart!

### Commands

| Command            | Description                                                                     |
| ------------------ | ------------------------------------------------------------------------------- |
| `/radio`           | Opens the radio Interface.                                                      |
| `/radiotalk`       | Toggles the radio talk animation                                                |
| `/radioreset`      | Resets the radio connection.                                                    |
| `/radiohud [size]` | Changes the size of the Radio interface. Options are `small`, `medium`, `large` |
| `/spawntower`      | Spawns a radio tower at your location.                                          |
| `/savetowers`      | Saves the currently spawned towers.                                             |
| `/sradio`          | Utility command for sonoran radio administration                                |

### Ace Permissions

| Ace Permission        | Description                                    |
| --------------------- | ---------------------------------------------- |
| `command.spawntower`  | Gives access to the `/spawntower` command.     |
| `command.savetowers`  | Gives access to the `/savetowers` command.     |
| `command.sradio`      | Gives access to the `/sradio` commmand.        |
| `sonoranradio.use`    | Radio Usage Permission (If Enabled in Config)  |
| `sonoranradio.repair` | Tower Repair Permission (If Enabled in Config) |

See below for more detailed ace permission setup.

## Usage

When you have the script installed on your server, you can use the `/radio` command to display the radio interface. If you have the TeamSpeak plugin installed and are in an appropriate patrol channel, the radio will display a connected status.

Once the radio displays a connected status, you can now use the radio interface to change your preset channels, as well as add or remove scanned frequencies from your scan list.

### Changing Frequency

To change frequency using the radio, click on the box that has the name of the channel that you are connected to, as well as the frequencies associated with that preset. If those frequencies don't match a preset the radio will display `Custom Frequency`. When you click on that display, you will see a list of available presets that you can choose from. You can either select a preset from that list or you can click `Custom` to create your own pair of frequencies.

### Modifying Scan List

To add a frequency to your scan list, click on the Scan List button on the radio screen. This will display the frequencies that you are currently scanning.

If you want to add the current receive frequency to the scan list, click on the `+` button on the top of the Scan List screen. To remove a scanned frequency from the screen, click on the `x` button next to the frequency to remove it from the Scan List.

Please note that a **Pro-level subscription** is required to utilize the scanning feature.

### Modifying In-Game Towers

<figure><img src="../../../.gitbook/assets/tower_in_game.jpeg" alt="" width="124"><figcaption><p>In-Game Radio Tower</p></figcaption></figure>

To modify the list of towers, you can either add-on to the existing list by using `/spawntower` and then `/savetowers` while in-game

**Command ACE Permissions**

```json
add_principal group.admin sonoranradio.towers
add_ace sonoranradio.towers command.spawntower allow
add_ace sonoranradio.towers command.savetowers allow
```

**YOU WILL NEED TO SET A USER AS `group.admin` STILL TO GIVE PERMISSION TO COMMANDS** You can do this by setting a user's identifier as group.admin with the following line...

```lua
add_principal identifier.license:{GTA License} group.admin
```

Alternatively, you can edit the file `towers.json` in the `sonoranradio` resource.

The config example below shows two radio tower placements.

**Example Config Structure:**

```json
[
	{
    "Id": "74d910e5-5705-4b58-baaf-88a8ca82734c",
		"Swankiness":0.0,
		"PropPosition":{"x":0.0,"y":0.0,"z":0.0},
		"Destruction":false,
		"Range":1500.0
	},
	{
    "Id": "7a4cb19d-e158-4afa-9e56-6de0c5446626",
		"Swankiness":0.0,
		"PropPosition":{"x":100.0,"y":0.0,"z":0.0},
		"Destruction":false,
		"Range":1500.0
	},
]
```

**Config Object Properties:** `Swankiness` - Not yet implemented `PropPosition` - X, Y, Z coordinate positioning object `Destruction` - Toggles whether this specific tower can be destroyed `Range` - Tower's range with in-game radios

{% hint style="info" %}
**Pro Tip:** Enabling`Config.debug` in the `config.lua` file will display a radius around each tower, where the edge represents 50% radio quality
{% endhint %}

### Customizing Mobile Repeaters <a href="#mobile-repeaters" id="mobile-repeaters"></a>

Vehicles can be configured to act as radio repeaters. In the config, you can set what vehicles are allowed to act as mobile repeaters, and the range of a given vehicle's repeater.

**Example Config Structure:**

```lua
-- Enable mobile repeaters
Config.enableVehicleRepeaters = true
-- Mobile repeater spawncodes
Config.repeaterVehicleSpawncodes = {
    {model = "police", label = "Police Vehicle", range = 200},
    {model = "police2", label = "Police Vehicle", range = 200},
}
```

In-game, you can press `G` to toggle the mobile repeater on a configured vehicle.

### Sonoran CAD Integration

For use of the panic button, unit status, and call information section, check out our [Sonoran CAD integration](https://info.sonorancad.com/integration-plugins/integration-plugins/available-plugins/sonoran-radio-sonrad).

### 3rd-Party Interaction with Radio

The following are client events that can be triggered to activate specific actions of the radio. More events are coming soon.

| Client Event                    | Description                                                                                             |
| ------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `SonoranRadio::API:NextPreset`  | Programmatically switch the client's radio to the next preset.                                          |
| `SonoranRadio::API:PrevPreset`  | Programmatically switch the client's radio to the previous preset.                                      |
| `SonoranRadio::API:PowerToggle` | Programmatically toggle the client's radio power.                                                       |
| `SonoranRadio::API:PanicButton` | Programmatically activate the panic button the client's radio.                                          |
| `SonoranRadio::API:SetPreset`   | Set the preset of the client's radio to the specified preset number. (Only Parameter is Preset as Int.) |
