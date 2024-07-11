---
description: Restrict user access to commands and features in-game with ACE permissions.
---

# Configuring ACE Permissions

## **Command ACE Permissions**

ACE permissions allow you to restrict what users have access to certain commands.

### **1. Create a Permission Group**

Here, we'll create an `admin` ACE group that has access to all of the `sonoranradio.towers` categorized permissions.

```
# ACE group name 'admin' for 'sonoranradio.towers' permission category
add_principal group.admin sonoranradio.towers
```

### **2. Assign Permissions to the Group**

This adds all of the Sonoran Radio permissions (configuring repeaters, using the radio, and repairing repeaters) to the `sonoranradio.towers` category that the `admin` ACE group has access to.

```
# Add permissions to the ace category "sonoranradio.towers"

# Tower Configuration Menu
add_ace sonoranradio.towers command.radiomenu allow

# Radio Access (Optional: If `acePermsForRadio` is `true` in config.lua)
add_ace sonoranradio.towers sonoranradio.use allow

# Tower Repair (Optional: If `acePermsForTowerRepair` is `true` in config.lua)
add_ace sonoranradio.towers sonoranradio.repair allow
```

### **3. Add Users to the ACE Group**

This grants a user the `admin` ACE permission group, specific to their in-game license ID.

```
add_principal identifier.license:{GTA License} group.admin
```

## ACE Permission Tools

You can also use external services like [Sonoran CMS](https://info.sonorancms.com/integration-capabilities/qb-core-game-panel/using-the-game-panel/aces-and-principals) to easily manage ACE permissions via ranks and Discord roles.

<div>

<figure><img src="../../.gitbook/assets/image.png" alt="" width="375"><figcaption><p>Sonoran CMS - QB Core Panel</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/image (2).png" alt="" width="375"><figcaption><p>Sonoran CMS - vMenu Panel</p></figcaption></figure>

</div>
