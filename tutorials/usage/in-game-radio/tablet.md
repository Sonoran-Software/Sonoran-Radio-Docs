---
description: View the dispatcher panel via in-game tablet!
---

# Tablet

## Using the In-Game Tablet

The in-game tablet allows users to access the dispatch panel.

<figure><img src="../../../.gitbook/assets/image (149).png" alt="" width="375"><figcaption></figcaption></figure>

### Via Command

Users in-game can use the `/radio tablet` to open the tablet. The tablet will display the dispatch panel, also available on the web and desktop applications.

### Via Keybind

Users in-game can also specify a custom keybind to open and close the tablet.

<figure><img src="../../../.gitbook/assets/image (148).png" alt="" width="375"><figcaption></figcaption></figure>

## Commands and ACE Permissions

<details>

<summary>FiveM Tablet Config + ACE Permissions</summary>


Users can use `/radio tablet` or `/showdispatch` to toggle the tablet on/off.

An optional `acePermission` has been added to restrict this command to specific users.

In the [config.lua](../../getting-started/installing-the-in-game-resource.md#updates)'s `Config.acePermsForRadioTablet` allows you to enable the ace perm.

Example acePermission use: `add_ace group.dispatch sonoranradio.tablet allow`

</details>
