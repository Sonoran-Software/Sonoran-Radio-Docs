---
description: Learn how to download and install the in-game resource.
---

# Installing the In-Game Resource

## Resource Installation

### 1. Download the ZIP

Download the [latest release](https://download.sonoransoftware.com/sonoranradio/fivem/latest.zip) of the FiveM resource

### 2. Extract the ZIP File

Extract the .zip file into your resources directory. Place the `sonoranradio` and `sonoranradio_updatehelper` into a folder labeled `[sonoranradio]`

<figure><img src="../../.gitbook/assets/explorer_tVF7A0zXhJ (1).png" alt=""><figcaption><p>Sonoran Radio Folder Structure</p></figcaption></figure>

### 3. Configure Community Information

1. Rename the `config.CHANGEME.lua` file to `config.lua`
2. In the `config.lua` file set `comId` to your community's ID
3. in the `config.lua` file set `apiKey` to your community's API key

The community ID and API key can be found in the `Administration` tab.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Sonoran Radio - Community ID &#x26; API Key</p></figcaption></figure>

### 4. Update Your Server Config

In your `server.cfg` file, add the following:

```
# Start the sonoranradio resource
ensure sonoranradio

# Permissions for auto-updater (REQUIRED)
add_ace resource.sonoranradio command allow
add_ace resource.sonoranradio_updatehelper command allow
```

{% hint style="danger" %}
It is very important that the `sonoranradio_updatehelper` resource is not started manually. Doing so may cause a server crash if updates are available due to a race condition.

**DO NOT** start the whole \[sonoranradio] folder as that will also start the sonoranradio\_updatehelper which might cause crashing if started manually.

Example of what NOT to do: `ensure [sonoranradio]`
{% endhint %}

### Config.lua Values <a href="#updates" id="updates"></a>

| Parameter                    | Default | Description                                                                                                                                    |
| ---------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `comId`                      | EMPTY   | The Sonoran Radio Community ID                                                                                                                 |
| `apiKey`                     | EMPTY   | The Sonoran Radio Community API Key                                                                                                            |
| `debug`                      | `false` | Display tower ranges on the map and other console prints.                                                                                      |
| `allowUpdateWithPlayers`     | `true`  | Allow the auto-updater to run while players are still in the server.                                                                           |
| `enableCanary`               | `false` | Allow the auto-updater to pull development branches for early testing.                                                                         |
| `allowAutoUpdate`            | `true`  | Allow the auto-updater to run.                                                                                                                 |
| `towerRepairTimer`           | `20`    | Time (in seconds) that it takes a player to repair a destructed tower.                                                                         |
| `rackRepairTimer`            | `15`    | Time (in seconds) that it takes a player to repair a destructed server rack.                                                                   |
| `antennaRepairTimer`         | `15`    | Time (in seconds) that it takes a player to repair a destructed cellular antenna.                                                              |
| `acePermsForServerRepair`    | `false` | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <code>sonoranradio.repair</code></p> |
| `acePermsForTowerRepair`     | `false` | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <code>sonoranradio.repair</code></p> |
| `acePermsForAntennaRepair`   | \`false | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <code>sonoranradio.repair</code></p> |
| `acePermsForRadio`           | `false` | <p>Restrict the usage of the radio (<code>/radio</code>) with ACE permissions.<br><br>ACE Command: <code>sonoranradio.use</code></p>           |
| `enforceRadioItem`           | `false` | Require the user to have a radio item in their inventory to be able to use the radio (QB & ESX frameworks).                                    |
| `disableRadioOnDeath`        | `true`  | Prevent users from talking on the radio while dead.                                                                                            |
| `restoreRadioStateWhenAlive` | `true`  | Restore the radio's power state (on/off) when you are revived or respawn.                                                                      |
| `deathDetectionMethod`       | `auto`  | <p>What method to use for death detection.<br><br><code>auto</code>, <code>manual</code>, or <code>qbcore</code></p>                           |
| `disableAnimation`           | `false` | Disable the radio talking animation for custom animation scripts.                                                                              |
| `noPhysicalCellRepeaters`    | `false` | Hide the in-game cellular antenna repeaters                                                                                                    |
| `noPhysicalRacks`            | `false` | Hide the in-game server rack repeaters                                                                                                         |
| `noPhysicalTowers`           | `false` | Hide the in-game tower repeaters                                                                                                               |

## ACE Permissions (Command Restrictions) <a href="#updates" id="updates"></a>

ACE permissions allow communities to restrict access to actions like using the radio, adding and removing towers, repairing towers, and more.

### Towers (Add, Remove & Repair)

Learn more about [restricting tower additions, removal, and repair](using-in-game-towers.md#command-ace-permissions) access.

### Radio

Learn more about [restricting access to the radio in-game](using-the-in-game-radio.md#restrict-radio-access-permissions).

## Updates <a href="#updates" id="updates"></a>

The Sonoran Radio in-game resource will automatically update with the latest features, fixes, and changes upon server restart!

## Next Steps

Learn how to use the in-game radio:

{% content-ref url="using-the-in-game-radio.md" %}
[using-the-in-game-radio.md](using-the-in-game-radio.md)
{% endcontent-ref %}
