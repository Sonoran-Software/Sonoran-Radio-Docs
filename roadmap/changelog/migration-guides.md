---
description: >-
  In some cases, the auto-updater requires manual steps from one version to the
  next.
---

# Migration Guides

<details>

<summary>2.18.0 (LB Phone, Background Noise)</summary>

Version 2.18.0 adds a new integration for LB phone and feature to inject background noise into your transmissions.

1. Open your existing `config.lua`
2. Add the new `Config.showEmergencyCallHelp = true` option. [Setting this to false hides the emergency call banner.](../../tutorials/usage/dispatch-panel/emergency-calls.md#customize-the-emergency-number-and-banner)
3. Add the new `Config.phoneResource = 'none'` option. [Setting this to `'lb-phone'` enables the LB phone integration.](../../tutorials/integrations/fivem-phone-scripts.md#lb-phone)
4. Add the new `Config.enableBackgroundAudio = true` option. [Setting this to false disables the background audio injection feature.](../../tutorials/usage/in-game-radio/background-audio-injection.md)

<figure><img src="../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

</details>

<details>

<summary>2.15.0 (ACE Perm Sync)</summary>

Version 2.15.0 adds a new feature to manage radio community approval and permissions via ACE perms.

1. Open your existing `config.lua`
2. Add the new `Config.acePermSync = false` property. You can enable and configure this feature if desired.

![](<../../.gitbook/assets/image (3) (1) (1).png>)

</details>

<details>

<summary>2.14.0 Release (LVC Resource Name)</summary>

Version 2.14.0 adds a new feature to increase radio volume when in-game sirens are on.

1. Open your existing `config.lua`
2. Add the new `Config.luxartResourceName = 'lvc'` property.

![](<../../.gitbook/assets/image (105).png>)

</details>

<details>

<summary>2.11.0 Release (Earpieces JSON)</summary>

Version 2.11.0 Migrates the earpiece configuration from the `config.lua`to `earpieces.json`. Therefore, this property is no longer needed in your `config.lua` file.

1. Open the new `earpieces.json` file to confirm your configuration has been migrated (after resource start).
2. Open your existing `config.lua`
3. Remove the `Config.chatterExclusions` property.

![](<../../.gitbook/assets/image (87).png>)

</details>

<details>

<summary>2.10.0 Release (Config Values)</summary>

Version 2.10.0 introduces new configuration values to customize the default user keybinds and the emergency call prefix.

Note: _This new default key mapping will only apply to new users who have not joined the server and had their keybind set yet._

1. Open your existing `config.lua`
2. Paste in the two, new default config options:

```lua
Config.emergencyCallCommand = '999' -- Command suffix to start or stop an emergency call (i.e. '911' == /radio 911)
```

```lua
-- Default radio keybinds (these can be changed in GTA settings) --
Config.keybinds = {
	['toggle'] = '',
	['ptt'] = '\\',
	['power'] = '',
	['panic'] = '',
	['nextChannel'] = '',
	['prevChannel'] = '',
	['talkAnim'] = ''
}
```

This is is also available from the auto-updater's `config.CHANGEME.lua`

</details>

<details>

<summary>2.8.1 Release (Mobile Repeater Default Key)</summary>

Version 2.8.1 introduces a new configuration value to customize the default user keybind to toggle mobile repeaters.

Note: _This new default key mapping will only apply to new users who have not joined the server and had their keybind set yet._

1. Open your existing `config.lua`
2. Paste in the new default config option (`Config.mobileRepeaterKeybind`)\
   This is also available from the auto-updater's `config.CHANGEME.lua`

```
-- Mobile repeater keybinds
Config.mobileRepeaterKeybind = {
	mapperType = 'keyboard', -- See: https://docs.fivem.net/docs/game-references/input-mapper-parameter-ids/
	map = 'g', -- See: https://docs.fivem.net/docs/game-references/input-mapper-parameter-ids/
	label = 'Toggle Radio Repeater'
}
```

Your `config.lua` show now look like the following:

<img src="../../.gitbook/assets/image (80).png" alt="" data-size="original">

</details>

<details>

<summary>2.7.0 (Speakers, Tunnels, Voice Effects, and Earpiece EUP)</summary>

Version 2.7.0 introduces a new configuration value for EUP earpiece detection (to prevent people from hearing nearby chatter).

1. Open your existing `config.lua`
2. Paste in the new default config option:\
   This is also available from the auto-updater's `config.CHANGEME.lua`

```lua
-- Radio Chatter Exclusion Settings --
Config.chatterExclusions = {
	{
		componentId = 2, -- Ears
		drawableId = 1, -- Number in vMenu MP Ped Component list
		texture = 0 -- Texture ID in vMenu MP Ped Component list
	},
	{
		componentId = 2, -- Ears
		drawableId = 2, -- Number in vMenu MP Ped Component list
		texture = 0 -- Texture ID in vMenu MP Ped Component list
	},
	{
		componentId = 2, -- Ears
		drawableId = 2, -- Number in vMenu MP Ped Component list
		texture = 0 -- Texture ID in vMenu MP Ped Component list
	},
	{
		componentId = 2, -- Ears
		drawableId = 42, -- Number in vMenu MP Ped Component list
		texture = 0 -- Texture ID in vMenu MP Ped Component list
	},
}
```

3.  Your `config.lua` should now appear like the following after adding in the `Config.chatterExclusions` property:

    <figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

</details>

<details>

<summary>2.6.0 Release (In-Game Nearby Audio &#x26; Connected Users List)</summary>

Version 2.6.0 introduces new configuration values.

1. Open your existing `config.lua`
2. Ensure the following lines are set:
   1. `Config.chatter = true`
   2. `Config.acePermsForRadioUsers = false`
   3. `Config.talkSync = true`

Your `config.lua` should now look like the following:

![](<../../.gitbook/assets/image (41).png>)

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

<img src="../../.gitbook/assets/image (22).png" alt="" data-size="original">

## ACE Permissions

Version 2.3.0 introduces a new in-game repeater configuration menu. This allows an easier way to add, edit, or remove in-game repeaters.

Communities will need to grant the new `command.radiomenu` permission.

Communities can remove the old spawn and remove command permissions:

* `command.spawnradiotower`
* `command.spawnradiorack`
* `command.spawnradiocellrepeater`
* `command.removeradiorepeater`

[See a complete example of our updated ACE permission structure.](../../tutorials/usage/in-game-radio/configuring-ace-permissions.md)

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

2. Replace `YOUR API KEY` with the [community API key](../../tutorials/getting-started/installing-the-in-game-resource.md#id-3.-configure-community-information) from the `Administration` panel.

</details>
