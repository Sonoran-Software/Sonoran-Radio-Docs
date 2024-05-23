---
description: Learn how to download and install the in-game resource.
---

# Installing the In-Game Resource

## Installation Video

TODO

## Resource Installation

### 1. Download the ZIP

Download the latest Sonoran Radio standalone resource from the panel. This download will already have your community ID pre-configured.

IMAGE TODO

### 2. Extract the ZIP File

Extract the .zip file into your resources directory. Place the `sonoranradio` and `sonoranradio_updatehelper` into a folder labeled `[sonoranradio]`

IMAGE TODO

### 3. Update Your Server Config

In your `server.cfg` file, add the following:

```
ensure sonoranradio

# permissions for auto-updater (REQUIRED)
add_ace resource.sonoranradio command allow
add_ace resource.sonoranradio_updatehelper command allow

# permissions for sonrad tower commands
add_principal group.admin sonoranradio.towers
add_ace sonoranradio.towers command.spawntower allow
add_ace sonoranradio.towers command.savetowers allow
```

{% hint style="danger" %}
It is very important that the `sonoranradio_updatehelper` resource is not started manually. Doing so may cause a server crash if updates are available due to a race condition.

**DO NOT** start the whole \[sonoranradio] folder as that will also start the sonoranradio\_updatehelper which might cause crashing if started manually.

Example of what NOT to do: `ensure [sonoranradio]`
{% endhint %}

## Updates <a href="#updates" id="updates"></a>

The Sonoran Radio in-game resource will automatically update with the latest features, fixes, and changes upon server restart!

## Next Steps

Learn how to use the in-game radio:

{% content-ref url="using-the-in-game-radio.md" %}
[using-the-in-game-radio.md](using-the-in-game-radio.md)
{% endcontent-ref %}
