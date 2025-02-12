---
description: >-
  Restrict user access to community approval, permissions, commands and features
  in-game with ACE permissions.
---

# Configuring ACE Permissions

## **Command ACE Permissions**

ACE permissions allow you to restrict what users have access to certain commands.

### **1. Create a Permission Group**

Here, we'll create an `admin` ACE group that has access to all of the `sonoranradio.example` categorized permissions.

```
# ACE group name 'admin' for 'sonoranradio.example' permission category
add_principal group.admin sonoranradio.example
```

### **2. Assign Permissions to the Group**

This adds all of the Sonoran Radio permissions (configuring repeaters, using the radio, and repairing repeaters) to the `sonoranradio.example` category that the `admin` ACE group has access to.

```
# Add permissions to the ace category "sonoranradio.example"

# Tower Configuration Menu
add_ace sonoranradio.example command.radiomenu allow

# Radio Access (Optional: If `acePermsForRadio` is `true` in config.lua)
# If using `acePermSync` in config.lua, this will also auto-approve the user in the community
add_ace sonoranradio.example sonoranradio.use allow

# ACE Permission Sync (Optional: If `acePermSync` is `true` in config.lua)
# If enabled, the general 
add_ace sonoranradio.

# Tower Repair (Optional: If `acePermsForTowerRepair` is `true` in config.lua)
add_ace sonoranradio.example sonoranradio.repair allow

# Connected Users List (Optional: If `acePermsForRadioUsers` is `true` in config.lua)
add_ace sonoranradio.example sonoranradio.radiousers allow

# Radio Scanner Menu (Optional: If `chatter` is `true` in config.lua)
add_ace sonoranradio.example sonoranradio.scanner allow

# Radio Scanner Channel Access (Optional: If `chatter` is `true` in config.lua)
# Number is based off of the channel ID
add_ace sonoranradio.example sonoranradio.channel.123
```

### **3. Add Users to the ACE Group**

This grants a user the `admin` ACE permission group, specific to their in-game license ID.

```
add_principal identifier.license:{GTA License} group.admin
```

***

## ACE Permission Sync

ACE permission sync allows you to automatically approve users in the radio community, grant access to private channels, and give user permissions like name changes, kick, etc.

[View other ways to manage user permissions.](../../getting-started/invite-and-manage-users.md)

<details>

<summary>Community Approval</summary>

Community members must be approved when first joining the radio. The approval behavior is dependent upon your [config.lua's `acePermsForRadio` value](../../getting-started/installing-the-in-game-resource.md#updates).

If `acePermsForRadio` is `true` users will need the `sonoranradio.autoapprove` permission to be automatically approved in the community.

If `acePermsForRadio` is `false` users will be automatically approved when turning on the radio.

</details>

<details>

<summary>Private Channels</summary>

Access to private channels can be granted via ACE permissions.

You will need the channel ID ([visible in the dispatch panel](../dispatch-panel/using-the-dispatch-panel.md#channel-ids) or [in-game radio](using-the-in-game-radio/fivem-keybinds-and-commands.md#copying-channel-and-scan-list-ids)) for each channel ACE permission.

`sonoranradio.channel.123`&#x20;

</details>

<details>

<summary>General Permissions</summary>

General radio community permissions can also be granted via ACE permissions.

Admin: `sonoranradio.admin`

Approve Members: `sonoranradio.communityapprove`

Change Display Name: `sonoranradio.setmynickname`&#x20;

Manage Display Name: `sonoranradio.setnickname`

Kick from Community: `sonoranradio.communitykick`&#x20;

Kick from Radio: `sonoranradio.radiokick`&#x20;

Move Radio Users: `sonoranradio.radiomove`

Play Dispatch Tones: `sonoranradio.radiotones`

Override Talkover Protection: `sonoranradio.radiotalkover`&#x20;



![](<../../../.gitbook/assets/image (109).png>)

</details>

## ACE Permission Tools

You can also use external services like [Sonoran CMS](https://info.sonorancms.com/integration-capabilities/qb-core-game-panel/using-the-game-panel/aces-and-principals) to easily manage ACE permissions via ranks and Discord roles.

<div><figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption><p>Sonoran CMS - QB Core Panel</p></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption><p>Sonoran CMS - vMenu Panel</p></figcaption></figure></div>
