---
description: Learn how to download and install the in-game resource.
---

# Installing the In-Game Resource

## A. One-Click Installation (RocketNode)

We've partnered with Rocket Node to bring you one-click Sonoran Radio installation for FiveM — making it easier than ever to host your community and connect with Sonoran Radio.

* [Purchase your FiveM Game Server!](https://sonoran.link/p62G7ncv)
* Use code `SONORAN` to save big!

{% embed url="https://www.youtube.com/watch?v=1Vw4XwiLKgY" %}

## B. Pre-Configured Resource Installation

{% embed url="https://youtu.be/5cPJCugzP4g" %}

### 1. Download the ZIP

Download a pre-configured version of the in-game resource from the panel. This download will already have your community ID and API key in the `config.lua` file.

Navigate to `Customization` > `FiveM Integration` > `Download Resource`

### 2. Extract the ZIP File

Extract the .zip file into your resources directory. Place the `sonoranradio` and `sonoranradio_updatehelper` into a folder labeled `[sonoranradio]`

<figure><img src="../../.gitbook/assets/explorer_tVF7A0zXhJ (1).png" alt=""><figcaption><p>Sonoran Radio - Folder Structure</p></figcaption></figure>

### 3. Update Your Server Config

In your `server.cfg` file, add the following:

```
exec @sonoranradio/sonoranradio.cfg
```

{% hint style="danger" %}
It is very important that the `sonoranradio_updatehelper` resource is not started manually. Doing so may cause a server crash if updates are available due to a race condition.

**DO NOT** start the whole \[sonoranradio] folder as that will also start the sonoranradio\_updatehelper which might cause crashing if started manually.

Example of what NOT to do: `ensure [sonoranradio]`&#x20;
{% endhint %}

{% hint style="danger" %}
Start this resource **AFTER** your preferred framework and any additional framework core resources such as inventory resources
{% endhint %}

***

## C. Resource Installation (Manual)

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

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1).png" alt=""><figcaption><p>Sonoran Radio - Community ID &#x26; API Key</p></figcaption></figure>

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

***

## Configuration Values <a href="#updates" id="updates"></a>

<details>

<summary>Configuration Options</summary>

| Parameter                    | Default                                                                                                                                                                                                                           | Description                                                                                                                                                                                                                                            |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `comId`                      | EMPTY                                                                                                                                                                                                                             | The Sonoran Radio Community ID                                                                                                                                                                                                                         |
| `apiKey`                     | EMPTY                                                                                                                                                                                                                             | The Sonoran Radio Community API Key                                                                                                                                                                                                                    |
| `debug`                      | `false`                                                                                                                                                                                                                           | <p>Display tower ranges on the map and other console prints.<br>This can be toggled live with the <a href="../usage/in-game-radio/using-the-in-game-radio/fivem-keybinds-and-commands.md#debug-mode">debug mode command</a>.</p>                       |
| `allowUpdateWithPlayers`     | `true`                                                                                                                                                                                                                            | Allow the auto-updater to run while players are still in the server.                                                                                                                                                                                   |
| `enableCanary`               | `false`                                                                                                                                                                                                                           | Allow the auto-updater to pull development branches for early testing.                                                                                                                                                                                 |
| `allowAutoUpdate`            | `true`                                                                                                                                                                                                                            | Allow the auto-updater to run.                                                                                                                                                                                                                         |
| `chatter`                    | `true`                                                                                                                                                                                                                            | Allow civilians to hear radio chatter when one is nearby                                                                                                                                                                                               |
| `talkSync`                   | `true`                                                                                                                                                                                                                            | <p>Talk in-game whenever you talk on the radio<br><br>If using <a href="../integrations/big-daddy-radio-animations.md">BD Animations</a>, you will also need to disable their <code>TalkSync</code> feature in the <code>settings.ini</code> file.</p> |
| `emergencyCallCommand`       | `911`                                                                                                                                                                                                                             | Command suffix to start or stop an emergency call (i.e. '911' == /radio 911)                                                                                                                                                                           |
| `luxartResourceName`         | `lvc`                                                                                                                                                                                                                             | Resource name for Luxart Vehicle Control, [used for the siren volume integration](../usage/in-game-radio/using-the-in-game-radio/#automatic-volume-increase-w-sirens).                                                                                 |
| `keybinds`                   | <pre class="language-lua"><code class="lang-lua">Config.keybinds = {
	['toggle'] = '',
	['ptt'] = 'BACKSLASH',
	['power'] = '',
	['panic'] = '',
	['nextChannel'] = '',
	['prevChannel'] = '',
	['talkAnim'] = ''
}
</code></pre> | <p>Default radio keybinds (these can be changed in GTA settings).<br><br>Use the <code>Input Parameter</code> from the <a href="https://app.gitbook.com/s/gJnyZgUQPWpA5p9njAAR/">CFX Documentation</a>. </p>                                           |
| `towerRepairTimer`           | `20`                                                                                                                                                                                                                              | Time (in seconds) that it takes a player to repair a destructed tower.                                                                                                                                                                                 |
| `rackRepairTimer`            | `15`                                                                                                                                                                                                                              | Time (in seconds) that it takes a player to repair a destructed server rack.                                                                                                                                                                           |
| `antennaRepairTimer`         | `15`                                                                                                                                                                                                                              | Time (in seconds) that it takes a player to repair a destructed cellular antenna.                                                                                                                                                                      |
| `acePermSync`                | `false`                                                                                                                                                                                                                           | [Sync ACE permissions to auto-approve and grant radio permissions from in-game](../usage/in-game-radio/configuring-ace-permissions.md#ace-permission-sync).                                                                                            |
| `acePermsForServerRepair`    | `false`                                                                                                                                                                                                                           | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <code>sonoranradio.repair</code></p>                                                                                                         |
| `acePermsForTowerRepair`     | `false`                                                                                                                                                                                                                           | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <code>sonoranradio.repair</code></p>                                                                                                         |
| `acePermsForAntennaRepair`   | `false`                                                                                                                                                                                                                           | <p>Restrict the ability to repair damaged radio repeaters with ACE permissions.</p><p></p><p>ACE Command: <code>sonoranradio.repair</code></p>                                                                                                         |
| `acePermsForRadio`           | `false`                                                                                                                                                                                                                           | <p>Restrict the usage of the radio (<code>/radio</code>) with ACE permissions.<br><br>ACE Command: <code>sonoranradio.use</code></p>                                                                                                                   |
| `enforceRadioItem`           | `false`                                                                                                                                                                                                                           | <p>Require the user to have a item in their inventory to be able to use the radio or radio scanner.<br><a href="../integrations/fivem-inventories.md">View supported frameworks and inventories.</a></p>                                               |
| `acePermsForRadioUsers`      | `false`                                                                                                                                                                                                                           | <p>Restrict the usage of the radio (<code>/radiousers</code>) with ACE permissions.<br><br>ACE Command: <code>sonoranradio.radiousers</code></p>                                                                                                       |
| `disableRadioOnDeath`        | `true`                                                                                                                                                                                                                            | Disables radio when dead.                                                                                                                                                                                                                              |
| `restoreRadioStateWhenAlive` | `true`                                                                                                                                                                                                                            | Restore the radio's power state (on/off) when you are revived or respawn.                                                                                                                                                                              |
| `deathDetectionMethod`       | `auto`                                                                                                                                                                                                                            | <p>What method to use for death detection.<br><br><code>auto</code>, <code>manual</code>, or <code>qbcore</code></p>                                                                                                                                   |
| `disableAnimation`           | `false`                                                                                                                                                                                                                           | Disable the radio talking animation for custom animation scripts.                                                                                                                                                                                      |
| `noPhysicalCellRepeaters`    | `false`                                                                                                                                                                                                                           | Hide the in-game cellular antenna repeaters                                                                                                                                                                                                            |
| `noPhysicalRacks`            | `false`                                                                                                                                                                                                                           | Hide the in-game server rack repeaters                                                                                                                                                                                                                 |
| `noPhysicalTowers`           | `false`                                                                                                                                                                                                                           | Hide the in-game tower repeaters                                                                                                                                                                                                                       |
| `autoCallouts`               | <pre><code>{
	enabled = true, -- Whether or not this feature is enabled
	speedUnit = 'mph', -- mph | kmh | none -- The unit of speed provided with the callout
}
</code></pre>                                                    | When enabled, user radios will [automatically transmit their heading, road, and speeds](broken-reference) during a pursuit.                                                                                                                            |
| `autoPttOnPanic`             | <p></p><pre><code>{
	enabled = true, -- Enable automatic PTT when panic button is pressed
	duration = 15 -- Duration in seconds to hold PTT when panic button is pressed
}
</code></pre>                                          | When a [radio user panics](../usage/in-game-radio/using-the-in-game-radio/#panic), this feature will automatically press their push-to-talk key for the configured amount of time.                                                                     |



</details>

***

## ACE Permissions (Command Restrictions) <a href="#updates" id="updates"></a>

ACE permissions allow communities to restrict access to actions like using the radio, adding and removing towers, repairing towers, and more.

{% content-ref url="../usage/in-game-radio/configuring-ace-permissions.md" %}
[configuring-ace-permissions.md](../usage/in-game-radio/configuring-ace-permissions.md)
{% endcontent-ref %}

***

## Updates <a href="#updates" id="updates"></a>

The Sonoran Radio in-game resource will automatically update with the latest features, fixes, and changes upon server restart!

***

## Next Steps

Learn how to customize and use the dispatch and in-game portals:

{% content-ref url="../usage/" %}
[usage](../usage/)
{% endcontent-ref %}
