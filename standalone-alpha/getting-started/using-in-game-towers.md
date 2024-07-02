---
description: >-
  Configure and customize destructible radio towers in-game to impact radio
  performance.
---

# Using In-Game Towers

## Available Repeater Types

### Server Rack

Server rack style repeaters are found by default inside of police stations and hospitals. These repeaters offer the most interactive destruction experience.

Press `E` on the door to open it.

Each server inside can be individually destroyed and will fall separately out of the rack. These can be configured with 1-5 servers in each. As more of these servers are destroyed, the repeater signal will diminish.

<div>

<figure><img src="../../.gitbook/assets/server.png" alt=""><figcaption><p>Server Rack</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/server_opened (1).png" alt=""><figcaption><p>Server Rack - Opened</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/server_destroyed (1).png" alt=""><figcaption><p>Server Rack - Destroyed</p></figcaption></figure>

</div>

### Radio Tower

Tower style repeaters are found by default on hills, mountains, and large rooftops.

Players can climb the ladder to reach the top.

There are four dishes inside that each account for 25% of the health. As more of these dishes are destroyed, the repeater signal will diminish.

<div>

<figure><img src="../../.gitbook/assets/tower (1).png" alt=""><figcaption><p>Radio Tower</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/tower_broken.png" alt=""><figcaption><p>Radio Tower - Destroyed</p></figcaption></figure>

</div>

### Cellular Antenna

Cellular antenna style repeaters are found by default on the side of high-rises and other buildings.

Destroying this antenna will disable it's repeater range.

<div>

<figure><img src="../../.gitbook/assets/cell.png" alt=""><figcaption><p>Cellular Antenna</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/cell_destroyed.png" alt=""><figcaption><p>Cellular Antenna - Destroyed</p></figcaption></figure>

</div>

### Custom Repeaters

Additional integrations like the [mobile command center](using-in-game-towers.md#mobile-command-center-repeater), [power grid hacking](using-in-game-towers.md#hacking-repeaters-power-grid-integration), and [custom vehicle repeaters](using-in-game-towers.md#mobile-vehicle-repeaters) offer further customization.

## Configuration

### Tower Placement

#### Default Positions

<figure><img src="../../.gitbook/assets/Default Placement.png" alt="" width="303"><figcaption><p>Sonoran Radio - Default Tower Positions</p></figcaption></figure>

#### Via Game Command

To <mark style="color:green;">**add**</mark> a new repeater, run one of the following commands:

* `/spawnRadioTower` - Create a new Tower type repeater
* `/spawnRadioRack <server count>` - Create a new server rack, with a specified number of servers (between `1` and `5`)
* `/spawnRadioCellRepeater` - Create a new cell antenna type repeater

To <mark style="color:red;">**remove**</mark> a radio repeater, run `removeRadioTower` to remove the closest repeater.

#### Manual Configuration

Alternatively, you can edit the individual `towers.json` file in the `sonoranradio` resource.

<details>

<summary>towers.json</summary>

```json
[
  // Radio Tower
  {
    // Unique Identifier
    "Id": "74d910e5-5705-4b58-baaf-88a8ca82734c",
    // Type of repeater (tower)
    "type": "radioTower",
    // XYZ Coordinates
    "PropPosition": {
      "x": -577.4769287109375,
      "y": -138.4747314453125,
      "z": 51.9765625
    },
    // Signal range in units
    "Range": 1500,
    // Allow destruction
    "Destruction": true
  },
  // Server Rack
  {
    // Unique Identifier
    "Id": "50a9c40a-e5bb-46b2-9a83-c5164599c64c",
    // Type of repeater (Server Rack)
    "type": "serverRack",
    // XYZ Coordinates
    "PropPosition": {
      "x": 443.3538513183594,
      "y": -983.1824340820312,
      "z": 30.6783447265625
    },
    // 360 degree compass heading for angles
    "heading": 90,
    // Signal range in units
    "Range": 1500,
    // Status of each server in rack: "alive" or "dead"
    "serverStatus": [
      "alive",
      "alive",
      "alive",
      "alive",
      "alive"
    ],
    // Is the repeater on or not
    "Powered": true,
    // Make the repeater invisible by setting to true
    "NotPhysical": false,
    // Temporary repeater
    "DontSaveMe": false,
    // Allow destruction
    "Destruction": true
  },
  // Cell Repeater
  {
    // Unique Identifier
    "Id": "1f68f034-500b-4b29-9356-8c8bf63fda04",
    // Type of repeater (cell repeater)
    "type": "cellRepeater",
    // XYZ Coordinates
    "PropPosition": {
      "x": 152.5,
      "y": -775.9000244140625,
      "z": 264.29998779296877
    },
    // 360 degree compass heading for angles
    "heading": 340.0,
    // Signal range in units
    "Range": 1500.0,
    // Is the repeater on or not
    "Powered": true,
    // Make the repeater invisible by setting to true
    "NotPhysical": false,
    // Temporary repeater
    "DontSaveMe": false,
    // Status of the antenna: "alive" or "dead"
    "AntennaStatus": "alive",
    // Allow destruction
    "Destruction": true
  }
]

```

</details>

#### **Command ACE Permissions**

ACE permissions allow you to restrict what users have access to certain commands.

1. Create a Permission Group

Here, we'll create an `admin` ACE group that has access to all of the `sonoranradio.towers` categorized permissions.

```
add_principal group.admin sonoranradio.towers
```

2. Assign Permissions to the Group

This adds all of the Sonoran Radio permissions (spawning and saving each repeater type) to the `sonoranradio.towers` category that the `admin` ACE group has access to.

```
# Add permissions to the ace category "sonoranradio.towers"

# Towers
add_ace sonoranradio.towers command.spawnRadioTower allow

# Server Racks
add_ace sonoranradio.towers command.spawnRadioRack allow

# Cell Repeaters
add_ace sonoranradio.towers command.spawnRadioCellRepeater allow

# Tower Removal
add_ace sonoranradio.towers command.removeRadioTower allow

# Tower Repair (Optional: If `acePermsForTowerRepair` is `true` in config.lua)
add_ace sonoranradio.towers sonoranradio.repair allow

# Radio Access (Optional: If `acePermsForRadio` is `true` in config.lua)
add_ace sonoranradio.towers sonoranradio.use allow
```

3. Add Users to the ACE Group

This grants a user the `admin` ACE permission group, specific to their in-game license ID.

```
add_principal identifier.license:{GTA License} group.admin
```

## Using the In-Game Towers

### Destroying a Tower

When tower destruction is enabled, users can use any form of weapon to damage the repeaters.

Once damaged and destroyed, the tower no longer provides radio coverage within that range.

### Repairing a Tower

Players can walk up to a destroyed repeater and press `G` to being the repair process.

The repair time can be configured in the `config.lua`'s `towerRepairTimer`.

You can also restrict permissions to repairing a tower with ACE permissions by setting `acePermsForTowerRepair` to `true` in the `config.lua`.

### Viewing Tower Coverage

#### Via In-Game Map

Enabling`Config.debug` in the `config.lua` file will display a radius around each tower, where the edge represents 50% radio quality.

#### Via Sonoran CAD Live Map

View Sonoran Radio repeater signal strength and health on the integrated CAD live map.\
Or, view dispatch call information on the in-game radio!

{% content-ref url="../integrations/sonoran-cad-integration.md" %}
[sonoran-cad-integration.md](../integrations/sonoran-cad-integration.md)
{% endcontent-ref %}

### Viewing Signal Strength

Coming Soon!

## Additional Integrations

### Mobile Command Center Repeater

The [Sonoran Mobile Command Center](https://www.sonoran.store/package/5287071) also offers a built-in radio repeater to improve reception on a scene.

Raise the radio antenna by running the `/mccradio` command.

<div>

<figure><img src="../../.gitbook/assets/mcc.png" alt=""><figcaption><p>Sonoran Mobile Command Center</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/mcc_radio.png" alt=""><figcaption><p>Sonoran Mobile Command Center</p></figcaption></figure>

</div>

### Hacking Repeaters - Power Grid Integration

Communities can add additional [Sonoran Power Grid](https://www.sonoran.store/package/5120025) integration support, enabling users to hack a radio repeater's power source instead of destroying it.

<figure><img src="../../.gitbook/assets/power_grid_promo.png" alt="" width="563"><figcaption><p>Sonoran Power Grid</p></figcaption></figure>

### Mobile (Vehicle) Repeaters

To extend coverage range, communities can also customize what vehicles contain a radio repeater.

In the `config.lua`, you can configure vehucle types and the range of a given vehicle's repeater.

**Example Config Structure:**

```lua
-- Enable mobile repeaters
Config.enableVehicleRepeaters = true
-- Mobile repeater spawncodes
Config.repeaterVehicleSpawncodes = {
    {model = "police", label = "Police Vehicle", range = 200},
    {model = "police2", label = "Police Vehicle", range = 200},
}
```

In-game, you can press `G` to toggle the mobile repeater on a configured vehicle.

If a vehicle is destroyed, it will no longer function as a radio repeater.
