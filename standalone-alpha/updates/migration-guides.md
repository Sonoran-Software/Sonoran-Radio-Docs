---
description: >-
  In some cases, the auto-updater requires manual steps from one version to the
  next.
---

# Migration Guides

<details>

<summary>2.3.0 Release (In-Game Configuration Menu)</summary>

## Configuration File

Version 2.3.0 introduces a new configuration value.

1. Open your existing `config.lua`
2. Add a new line `Config.apiUrl = 'https://sonoranradio.com'`

Your `config.lua` file should look like the following:

<img src="../../.gitbook/assets/image (22).png" alt="" data-size="original">

## ACE Permissions

Version 2.3.0 introduces a new in-game repeater configuration menu. This allows an easier way to add, edit, or remove in-game repeaters.

Communities will need to grant the new `command.radiomenu` permission.

Communities can remove the old spawn and remove command permissions:

* `command.spawnradiotower`
* `command.spawnradiorack`
* `command.spawnradiocellrepeater`
* `command.removeradiorepeater`

[See a complete example of our updated ACE permission structure.](../getting-started/configuring-ace-permissions.md)

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

2. Replace `YOUR API KEY` with the [community API key](../getting-started/installing-the-in-game-resource.md#id-3.-configure-community-information) from the `Administration` panel.

</details>

