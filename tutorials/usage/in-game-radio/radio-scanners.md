---
description: Discretely listen to your community's radio
---

# Radio Scanners

<figure><img src="../../../.gitbook/assets/scanner.png" alt=""><figcaption><p>Sonoran Radio - In-Game Scanner</p></figcaption></figure>

{% hint style="warning" %}
Due to bandwidth usage, this feature is automatically enabled with the Pro version only!

[Learn more about our paid subscription plans.](../../../pricing/faq/standalone-pricing.md)
{% endhint %}

## Video Example

## Using the Radio Scanner

### Enabling the Scanner

1. Enable the `config.chatter`  option in your [config.lua](../../getting-started/installing-the-in-game-resource.md#updates).
2. Add the `sonoranradio.scanner` [ace permission](configuring-ace-permissions.md).

### Opening in Standalone

You can use `/radio scanner` command to open a personal scanner. This requires the `sonoranradio.scanner` [ace permission](configuring-ace-permissions.md).

### Opening in QBCore

With the[ radio scanner item in their inventory](radio-scanners.md#giving-the-scanner-item-qbcore), users can double click to open the [scanner menu](radio-scanners.md#using-the-radio-scanner-1).

<figure><img src="../../../.gitbook/assets/image (96).png" alt=""><figcaption><p>Sonoran Radio Scanner Item in Inventory</p></figcaption></figure>

#### Item Drop

If the scanner item is dropped on the floor, you can open its scanner menu by being near it and pressing `E`.

If the scanner is powered, transmissions will be heard by nearby users.

<figure><img src="../../../.gitbook/assets/image (97).png" alt=""><figcaption><p>Sonoran Radio Scanner Item Drop Use Hint</p></figcaption></figure>

### Radio Scanner Menu

`Power On` the radio and then select `Next Channel` or `Previous Channel` until you have selected the correct channel.

By default, only public radio channels will be available. For [private channels](../dispatch-panel/configure-channels.md#restrict-channel-visibility), you can [configure ACE permissions to access them](radio-scanners.md#ace-permissions).

<figure><img src="../../../.gitbook/assets/image (95).png" alt="" width="345"><figcaption><p>Sonoran Radio FiveM Radio Scanner Controls</p></figcaption></figure>

## Developers

### Ace Permissions

If you have enabled `Config.acePermsForScanners`, you must add permissions in your `server.cfg`for the scanner to work. Example:

```bash
# Give the group access to /radio scanner
add_ace group.admin sonoranradio.scanner allow

# Only public (non-private) channels are accessible
# Grant access to "Tac 1" and "Fire Dept" private channels
# Channel names are CASE SENSITIVE and must be EXACT
add_ace group.admin "sonoranradio.channel.Tac 1" allow
add_ace group.admin "sonoranradio.channel.Fire Dept" allow
```

### Giving the Scanner Item (QBCore)

Sonoran Radio does not provide a way to get the scanner item independently. You can give the item with any method, but here's an example chat command:

```
/giveitem <playerId> sonoran_radio_scanner 1
```

Please note that if you changed `Config.ScannerItem.name`, it will not work with `sonoran_radio_scanner`
