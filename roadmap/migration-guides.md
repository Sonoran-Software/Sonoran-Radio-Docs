---
description: >-
  In some cases, the auto-updater requires manual steps from one version to the
  next.
---

# Migration Guides

<details>

<summary>2.6.0 Release (In-Game Nearby Audio &#x26; Connected Users List)</summary>

Version 2.6.0 introduces new configuration values.

1. Open your existing `config.lua`
2. Ensure the following lines are set:
   1. `Config.chatter = true`
   2. `Config.acePermsForRadioUsers = false`

</details>

<details>

<summary>2.3.0-1 Release (In-Game Configuration Menu)</summary>

## Configuration File

Version 2.3.0 introduces a new configuration value.

1. Open your existing `config.lua`
2. Ensure the following lines are set:
   1. `Config.radioUrl = 'https://sonoranradio.com'`
   2. `Config.apiUrl = 'https://api.sonoranradio.com/'`

Your `config.lua` file should now look like the following:

<img src="../.gitbook/assets/image (22).png" alt="" data-size="original">

## ACE Permissions

Version 2.3.0 introduces a new in-game repeater configuration menu. This allows an easier way to add, edit, or remove in-game repeaters.

Communities will need to grant the new `command.radiomenu` permission.

Communities can remove the old spawn and remove command permissions:

* `command.spawnradiotower`
* `command.spawnradiorack`
* `command.spawnradiocellrepeater`
* `command.removeradiorepeater`

[See a complete example of our updated ACE permission structure.](../tutorials/usage/in-game-radio/configuring-ace-permissions.md)

</details>

<details>

<summary>2.2.0 Release (In-Game Towers)</summary>

## Towers File

Version 2.2.0 introduces multiple new in-game tower options. This includes a new `towers.DEFAULT.json` file that is required.

1. Delete the existing `towers.json` file in your `sonoranradio` resource.
2. Rename the new `towers.DEFAULT.json` file to `towers.json` in your `sonoranradio` resource and save.

## Configuration File

Version 2.2.0 adds a new API key configuration for upcoming features.

1. Add the following to line to your `config.lua` file, below the `Config.comId` line:

`Config.apiKey = 'YOUR API KEY'`

2. Replace `YOUR API KEY` with the [community API key](../tutorials/getting-started/installing-the-in-game-resource.md#id-3.-configure-community-information) from the `Administration` panel.

</details>

