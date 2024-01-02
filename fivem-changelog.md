---
title: In-Game Radio Changelog
description: All version updates for the in-game FiveM radio resource.
published: true
date: 2024-01-02T23:09:56.387Z
tags: 
editor: markdown
dateCreated: 2021-10-07T05:11:41.006Z
---

## v1.7.2 (2024-01-02)
* Fix: QBCore metadata not saving from the /adminskinchange command
## v1.7.1 (2023-12-30)
* Feat: Add outdated config file check and error
## v1.7.0 (2023-12-29)
* Feat: Add support for additional radio frames
* Feat: Add support for real-time UI resizing 
* Fix: Multiple minor bugs & optimized code
## v1.6.2 (2023-02-01)
 * Feat: Support added for QUASAR Inventory for qb-core
   - The radio item has been renamed to `sonoran_radio`

## v1.6.1 (2023-01-05)
 * Feat: Optionally, radios can disable themselves when you die in-game

## v1.6.0 (2022-12-29)
 *  Feat: In-game radio components can be moved through a setting in the interface

## v1.5.2 (2022-12-02)
 * Fix: `previous preset` keybind acting like `next preset`

## v1.5.1 (2022-12-01)
 * Feat: New experimental resource API for other resources
   - [Learn More](/tutorials/in-game-radio#h-3rd-party-interaction-with-radio)

## v1.5.0 (2022-10-24)
 * Feat: [Mouse support for Mobile Radio UI (Vehicle UI)](/tutorials/script-usage#radio-interface).

## v1.4.1 (2022-09-22)
 * Feat: Add blip support for mobile repeaters.

## v1.4 (2022-09-14)
 * Feat: Add Tower API for external resources.

## v1.3.14 (2022-07-21)
 * Feat: Mobile Radio UI
 * Fix: Radio Console Log Bug.
 
> Important Reminder (Keybinds):
{.is-info}


To ensure that the mobile radio does not cause anyone to inadvertently crash while operating it, the buttons on the front of the mobile radio are currently unable to be pressed, therefore it is important that if you would like to change your radio settings while you are in your vehicle, you must use the keybinds. Please see the following document for more information about setting up keybinds to control the radio...
- [In-Game Script Usage](/tutorials/script-usage#radio-keybinds)
{.links-list}

**The in-car radio feature is currently experimental and may have unforseen problems. Please report problems that you encounter to our [support team](https://support.sonoransoftware.com).**

## v1.3.13 (2022-05-27)
 * Feat: Add Support for Sonoran Power Grid
 * Feat: Top Down Radio UI
 * Fix: Uncaught type error exception

## v1.3.12 (2022-05-19)
 * Feat: Tower Blips
 * Fix: Loop Problem

## v1.3.11 (2022-05-12)
 * Feat: QBCore Radio Item

## v1.3.10 (2022-04-21)
 * Fix: CAD Integration

## v1.3.9 (2022-04-16)
 * Various Build Changes.

## v1.3.7 (2022-03-18)
* **Fix: scan list not updating**
* **Fix: channels/presets not updating**
* **Tweak: NUI no longer allows in-game input at the same time**

## v1.3.5 (2022-03-02)
* **Feat: Ability to move while holding the radio**
* **Feat: Add Command `/radiotalk` to toggle radio talk animation**
* **Feat: Permission Based Tower Repair (Requires Config Update)**
* **Feat: Ace Permissions for using the In-Game Radio**
* **Fix: Tower Antennas Rotating to match Tower**
* **Fix: "Radio: Off" notifications now display when radio is turned off**
* **Fix: Radio Clock Digit Padding**
* **Tweak: Removed some nui spam that was in the console.**
* **Tweak: Added more items into the verbose debug messages**
* **Tweak: Slightly increased radio screen size by adjusting interface**

## v1.3.4 (2022-02-17)

* **Fix: Radio object staying in hand if opening soon after closing**
* **Fix: The ability to open the radio while aiming**
* **Fix: Animations being broken in vehicles** (especially motorcylces)

## v1.3.3 (2022-02-03)

* **Hotifx: state sync issue**

## v1.3.2 (2022-02-03)
- **Fix: tower components not respawning if they're deleted or removed**
- **Tweak: amount TS is updated with gamestate** (will decrease chance of antiflood engaging)

## v1.3.1 (2022-01-19)
- **Fix: AI density lowered when towers are enabled**

## v1.3.0 (2022-01-07)
 - **Feat: Tower Destruction / Repair**
 - **Feat: New Configuration Options**
 - **Fix: Auto-updater merge issue**

## v1.1.5 (2021-11-24)
*Note: Requires v1.2 of the sonrad plugin for SonoranCAD integration.*
 - **Feat: Unit Status**
 - **Feat: First Preset Button**
 - **Feat: Add Icons to Radio**
 - **Feat: Contacts list**
 - **Feat: Settings Page**
 - **Feat: Radio Status Color Indicators**
 - **Fix: Sonrad Panic**
 - **Fix: Radio Clock**
 - **Fix: Frequency Notification Issue**
 - **Fix: Channel name too long issue**
 - **Tweak: goToPreset Added**
 - **Tweak: Suppress Connection Messages**
 - **Tweak: Remove Logging**
 - **Tweak: Connection State Awareness**

## v1.1.4 (2021-11-09)
 - **Hot Fix: Send notifications only when radio is switched on.**

## v1.1.3 (2021-11-06)
- **FEAT: Radio reconnect command: `/radioreset`**
- **FEAT: Add channel switch in-game notifications**
- **FEAT: Add panic button in-game notification**
- **FEAT: Add radio on/off in-game notifications**
- **FEAT: Turn on/off scanning from the scan list (Pro)**
- **Fix: Add restrictions and notifications for free tier**
- **Fix: Radio stays in hand when restarting script**
- **Tweak: Gracefully handle known socket error messages**
- **Tweak: Suppress unknown/unexpected socket error messages**

## v1.1.2 (2021-10-26)
- **Fix: Corrected Frequency Bounds for Custom Frequency**
- **Fix: Corrected Handling of Config Changed Event**

## v1.1.1 (2021-10-26)
- **Fix: Fix Custom Frequencies**
- **Tweak: Remove More Debug Messages**

## v1.1.0 (2021-10-23)
- **FEAT: Preset Dial Keybinds**
- **FEAT: Radio Power Keybind**
- **FEAT; Panic Button Keybind**
- **Tweak: Remove More Debug Messages**

## v1.0.8 (2021-10-23)
- **FEAT: Radio Power Keybind**
- **FEAT: Panic Button Keybind**
- **Fix: Remove Some Logging**
- **Fix: Radio Power Button** 
- **Tweak: CI Pipeline**
- **Tweak: manifest.lua**

## v1.0.7 (2021-10-19)
- **FEAT: CAD Integration with Sonrad Plugin**
- **FEAT: Radio Power Button**
- **FEAT: Unit Status**
- **FEAT: Panic Button**
- **Tweak: Build Process**
- **Tweak: CI Pipeline**
- **Tweak: Game State Updates** 

## v1.0.6 (2021-10-11)
- **FEAT: Radio Branding**
- **FEAT: Open Animation**
- **Fix: Scrolling for Presets and Scan List**
- **Fix: Preset Header Overflow**

## v1.0.5 (2021-10-06)
- **Initial release of FiveM script for alpha testing**

## v1.0.4 (2021-10-05)
- **Fix: Minor bug fixes relating to build.**

## v1.0.3 (2021-10-05)
- **Feat: Add keybind for radio command**

## v1.0.2 (2021-09-30)
- **(Tweak) auto-updater script**

## v1.0.1 (2021-09-30)
- **(Feature) auto-updater script**