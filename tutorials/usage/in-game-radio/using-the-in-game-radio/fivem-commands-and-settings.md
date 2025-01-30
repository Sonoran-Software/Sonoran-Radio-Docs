---
description: Radio settings panel for FiveM.
---

# FiveM Commands & Settings

The FiveM radio's settings panel offers additional configuration options.

## FiveM Settings



<figure><img src="../../../../.gitbook/assets/image (99).png" alt="" width="270"><figcaption></figcaption></figure>

### Volume Change w/Sirens

When in-game, turning on your sirens will increase your overall radio volume by the configured amount. Turning your sirens back off will lower the volume back down.

This feature is automatically integrated with [Luxart Vehicle Control](https://github.com/TrevorBarns/luxart-vehicle-control).\
If the resource is not named `LVC`, the [`config.luxartResourceName` value must be updated](../../../getting-started/installing-the-in-game-resource.md#updates).

For communities not using LVC, the functionality will fall back to a FiveM native that will trigger the functionality if either lights or sirens are activated.

### Escape Mode

The Escape Mode selector changes the in-game radio display behavior after pressing `ESC`.

`Keep Radio Visible`

* The radio stays visible on `ESC`

`Hide Radio`

* The radio closes on `ESC`

`XMITT (PTT)`

* The radio closes on `ESC`, but is visible while transmitting

## FiveM Client Commands

### Copying Channel and Scan List IDs

FiveM commands require channel and scan list IDs. These IDs can be made visible by toggling the `#` icon in the channel or scan list menus.

<div><figure><img src="../../../../.gitbook/assets/image (103).png" alt="" width="180"><figcaption><p>Modern UI: Channel and Scan IDs</p></figcaption></figure> <figure><img src="../../../../.gitbook/assets/image (104).png" alt="" width="198"><figcaption><p>Modern UI: Channel IDs</p></figcaption></figure></div>

### Stream Deck Integration

Stream Deck plugins like [FXCommands](https://marketplace.elgato.com/product/fxcommands-fivem-a6cdf538-76ac-4fc7-b8b8-130ea2b8bcbb) can be used to trigger any of the commands below.

### Toggle Channel Transmit

To toggle transmitting on a specific channel use the command

`/radio channel ID`

### Toggle Scan List

To toggle on/off a specific scan list use the command

`/radio scanlist ID`

### Toggle Channel Scan

To toggle on/off scanning a specific channel use the command

`/radio scan ID`

## FiveM Server Commands

Commands for the server console.

### Debug Mode

Toggle the [`config.debug` mode](../../../getting-started/installing-the-in-game-resource.md#updates) with the command

`/sonoranradio debugmode`

Note: This mode does not persist through server restarts.

### Update

Run the automatic update with the command

`/sonoranradio update`













