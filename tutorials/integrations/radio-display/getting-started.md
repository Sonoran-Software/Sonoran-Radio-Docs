---
description: >-
  This page will walk you through getting and installing the Radio Display
  script.
---

# Getting Started

## Acquire the Script <a href="#acquire-the-script" id="acquire-the-script"></a>

After "purchasing" (free) the script through the Sonoran store you may [download the script through the keymaster account](https://docs.sonoran.store/general/tebex-assets) that purchased the script. Upon downloading extract the file to a safe place.

## Install Prerequisite

{% hint style="warning" %}
You must have [SonoranRadio](../../getting-started/installing-the-in-game-resource.md) in order to use
{% endhint %}

## Install the script

1. Inside the script package you just extracted will be two folders. Copy both to a folder in your server's resources folder called `[sonoranradio]` note the `[]` in the name, without them it will not work.

<figure><img src="../../../.gitbook/assets/image (98).png" alt=""><figcaption><p>SonoranRadio - Radio Display - Folders</p></figcaption></figure>

2. In the `sonoran-radiodisplay`folder there will be a file called `config.CHANGEME.lua` you should rename that to be `config.lua` and configure the settings inside as you would like them to be configured based on the configuration documentation below. In that same folder will also be a file called `radios.CHANGEME.json` which you should rename to `radios.json` and use to manually place in-car radios based on the existing template, note you can also use the menu placement system in game.
3. Finally, in your `server.cfg` add the following:

```
ensure sonoran-radiodisplay

add_ace resource.sonoran-radiodisplay command allow
add_ace resource.sonoran-radiodisplay_helper command allow

```

## Configuring the Script

<details>

<summary>Default <code>config.lua</code></summary>

```lua
Config = {}

Config.debug_mode = false -- Enable debug mode
Config.configuration_version = 1.0
Config.auto_update = true -- Enable auto updates

Config.lang = {
    addNewRadioHelp = 'Open the menu to begin spawning a new in-car model model',
    vehNotCompatible = 'This vehicle is not compatible with the in-car model placement system!',
    vehAlrRadio = 'This vehicle already has a valid in-car radio!',
    radioMenuHeader = 'Sonoran In-Car Radio',
    creditsPanel = 'Made by',
    spawningSubMenu = 'In-Car Radio Spawning',
    attachingSubMenu = 'Attaching',
    deletionSubMenu = 'Are you sure?',
    radioAttachMenuButton = 'Attach In-Car Radio',
    deleteMenuButton = 'Delete Current In-Car Radio',
    spawnMenuButton = 'Spawn In-Car Radio',
    deletionConfirmationButton = 'Yes, remove from all of these vehicles',
    deletionCancelButton = 'Cancel',
    deletionCancelled = 'In-Car Radio deletion cancelled',
    noRadioFound = 'No In-Car Radio is in this vehicle!',
    modelComboBox = 'Model:',
    vehAlrRadioNoti = '~r~This vehicle already has an In-Car Radio of this type',
    notInVeh = '~r~You must be in a vehicle!',
    vehicleBone = 'Radio - Vehicle Bone',
    object = "Object:",
    vehicleBoneComboBox = 'Vehicle Bone',
    objectName = 'Sonoran In-Car Radio',
    attachButton = 'Attach',
    detachButton = 'Detach',
    confirmPlacementButton = 'Apply to all of this vehicle model',
    cannotGoFaster = '~r~You cannot go any faster!',
    cannotGoSlower = '~r~You cannot go any slower!',
}

Config.commands = {
    carRadioMenu = 'carradiomenu',
    restricted = false -- should the detector menu be restricted?
}

Config.permissionMode = "ace" -- Available Options: ace, framework, custom

-- Ace Permissions Section --
Config.acePerms = {
    aceObjectUseMenu = "sonoran.incarradio", -- Select the ace for placing new ATM's and using admin repair
}

-- Framework Related Settings --
Config.framework = {
    frameworkType = "qb-core", -- This setting controls which framework is in use options are esx or qb-core
    inventoryType = "normal", -- Which inventory you would like to use normal, quasar, ox_inventory (OX Will only work for ESX Legacy as of now)
    civilianJobNames = {"unemployed"}, -- An array of job names that should be allowed to use the radio menu
    useCivilianJobListAsBlacklist = false, -- This will treat the civilian job list as a blacklist rather than a whitelist
}

-- Configuration For Custom Permissions Handling --
Config.custom = {
    checkPermsServerSide = true, -- If true the permission event will be sent out to the server side resource, this is recommended
    permissionCheck = function(_, type) -- This function will always be called server side.
        if type == 0 then -- Check permission to use the menu
            return true or false -- Return true if they have admin, return false if they don't
        end
    end
}

Config.general = {
    notificationType = "native", -- Available options: native, pNotify, okokNotify
    useAllowlistAsBlacklist = false, -- If true, the Config.allowlistedCars will be treated as an blacklist
}

Config.allowlistedCars = {
        "FIRETRUK",
        "LGUARD",
        "PBUS",
        "POLMAV",
        "POLICET",
        "PRANGER",
        "PREDATOR",
        "RIOT",
        "RIOT2",
        "AMBULAN",
        "POLICE",
        "POLICE2",
        "POLICE3"
}

```

</details>

## Radio Location Config

You have two options for placing new radars:

1. You can use the command `/radiodisplay` while in a LEO vehicle to initiate spawning a new radio and generate the relevant config data
   * After running this command you will be prompted by a menu that will take you through the spawning process.
   * You may need to modify some of the rotation values manually to get that perfect placement you are looking for.
2. You can manually copy and paste an existing config and then modify the values to meet your needs for the new radio

### `radios.json` Property Explanation <a href="#radars.json-property-explanation" id="radars.json-property-explanation"></a>

| Property Name | Example  | Notes                                                               |
| ------------- | -------- | ------------------------------------------------------------------- |
| `ID`          | `2`      | `ID` must be unique. No other radar can share this ID               |
| `Position`    |          | This is a table that contains the x, y, and z coords of the radar   |
| `Rotation`    |          | This is a table that contains the x, y, and z rotation of the radar |
| `Vehicle`     | `POLICE` | This is the vehicles spawn code                                     |
| `Bone`        | `-1`     | This is the index of the bone you would like to attach the radar to |

## Commands

| Command Name    | Command Description                                                 | Required Permissions |
| --------------- | ------------------------------------------------------------------- | -------------------- |
| `/radiodisplay` | This command will initiate the radar spawning and attaching process | As configured        |

## Default Vehicles

| Vehicle Spawncode | Adds Radio by Default |
| ----------------- | --------------------- |
| `FBI`             | `yes`                 |
| `FBI2`            | `yes`                 |
| `POLICE`          | `yes`                 |
| `POLICE2`         | `yes`                 |
| `POLICE3`         | `yes`                 |
| `POLICE4`         | `yes`                 |
| `POLICEOLD1`      | `no`                  |
| `POLICEOLD2`      | `no`                  |
| `SHERIFF`         | `yes`                 |
| `SHERIFF2`        | `yes`                 |
