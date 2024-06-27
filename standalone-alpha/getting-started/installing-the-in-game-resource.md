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

### 3. Configure Sonoran Radio

Rename `config.CHANGEME.lua` to `config.lua`, and open it to edit your community ID

Set `Config.comId` to your community's ID. This can be found in your communitity's Administration page:

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Sonoran Radio - API Info with Community ID</p></figcaption></figure>

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

### Config Values <a href="#updates" id="updates"></a>

| Parameter                    | Default | Description                                                                                                                          |
| ---------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `comId`                      | EMPTY   | The Sonoran Radio Community ID                                                                                                       |
| `debug`                      | `false` | Display tower ranges on the map and other console prints.                                                                            |
| `allowUpdateWithPlayers`     | `true`  | Allow the auto-updater to run while players are still in the server.                                                                 |
| `enableCanary`               | `false` | Allow the auto-updater to pull development branches for early testing.                                                               |
| `allowAutoUpdate`            | `true`  | Allow the auto-updater to run.                                                                                                       |
| `noPhysicalTowers`           | `false` | Hide the in-game towers.                                                                                                             |
| `towerRepairTimer`           | `20`    | Time (in seconds) that it takes a player to repair a destructed tower.                                                               |
| `acePermsForRadio`           | `false` | <p>Restrict the usage of the radio (<code>/radio</code>) with ACE permissions.<br><br>ACE Command: <strong>TODO</strong></p>         |
| `acePermsForTowerRepair`     | `false` | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <strong>TODO</strong> </p> |
| `enforceRadioItem`           | `false` | Require the user to have a radio item in their inventory to be able to use the radio (QB & ESX frameworks).                          |
| `disableRadioOnDeath`        | `true`  | Prevent users from talking on the radio while dead.                                                                                  |
| `restoreRadioStateWhenAlive` | `true`  | Restore the radio's power state (on/off) when you are revived or respawn.                                                            |
| `deathDetectionMethod`       | `auto`  | <p>What method to use for death detection.<br><br><code>auto</code>, <code>manual</code>, or <code>qbcore</code></p>                 |

## Updates <a href="#updates" id="updates"></a>

The Sonoran Radio in-game resource will automatically update with the latest features, fixes, and changes upon server restart!

## Next Steps

Learn how to use the in-game radio:

{% content-ref url="using-the-in-game-radio.md" %}
[using-the-in-game-radio.md](using-the-in-game-radio.md)
{% endcontent-ref %}
