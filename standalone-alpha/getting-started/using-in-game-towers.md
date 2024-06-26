---
description: >-
  Configure and customize destructible radio towers in-game to impact radio
  performance.
---

# Using In-Game Towers

{% hint style="danger" %}
This feature is not yet accessible in the early-access Alpha.

Stay tuned to our [Discord ](https://discord.sonoransoftware.com)for news and announcements!
{% endhint %}

## Available Repeater Types

### Server Rack

Server rack style repeaters are found by default inside of police stations and hospitals. These repeaters offer the most interactive destruction experience.

Press `E` on the door to open it.

Each server inside can be individually destroyed and will fall separately out of the rack. There are five servers inside that each account for 20% of the health. As more of these servers are destroyed, the repeater signal will diminish.

### Tower

Tower style repeaters are found by default on hills, mountains, and large rooftops.

Players can climb the ladder to reach the top.

Each dish on the top accounts for a percentage of the tower's health. As more of these dishes are destroyed, the repeater signal will diminish.

### Cellular Antenna

Cellular antenna style repeaters are found by default on the side of high-rises and other buildings.

Destroying this antenna will disable it's repeater range.

## Configuration

### Modifying Tower Placement

Coming Soon!

### Modifying Tower Range

Coming Soon!

### Viewing Tower Coverage

#### Via In-Game Map

Coming Soon!

#### Via Sonoran CAD Live Map

Coming Soon!

## Visualize Signal Strength

Coming Soon!



## Mobile (Vehicle) Repeaters

To extend coverage range, specific emergency vehicles can be configured to have a built-in radio repeater, similar to the [Mobile Command Center](https://www.sonoran.store/package/5287071).

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
