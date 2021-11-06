---
title: Plugin Changelog
description: All version updates for the TeamSpeak plugin
published: true
date: 2021-11-06T05:09:32.706Z
tags: changelog
editor: markdown
dateCreated: 2021-10-07T04:39:14.544Z
---

## 0.2.3 (2021-11-05)

* **Added** a list of preset-sorted users in channel description
  * ![example.png](https://i.imgur.com/Xlnjy04.png)
* **Changed** dispatch dialog channel users to alphabetical sort (and add preset/freq next to name)
  * ![example.png](https://i.imgur.com/KEG6akK.png)
* **Fixed** mic clicks playing when unintended (ex. if a person was blocked from transmitting)
* **Fixed** failure opening downloaded update package
* **Fixed** radio on/off not working in Free subscription
* **Fixed** simplex frequencies that overlap with duplex frequencies having unintended repeated transmissions
* **Fixed** rare crash when closing dispatch dialog
* **Fixed** fonts in all dialogs

## 0.2.2 (2021-10-30)

* **Fixed** invalid event data being sent (breaking FiveM)
* **Fixed** whispers being treated as transmissions

## 0.2.1 (2021-10-29)

* **Added** About menu button that displays info about plugin
* **Fix** FiveM script failing to connect in Free
* **Fix** links not working in some UI components
* **Fix** multiple instances of mic clicks playing when they shouldn't
* Other small bug fixes

## 0.2.0 (2021-10-23)

* **Added** authorization codes
* **Added** in-game connection for radio toggle
* **Fix** question mark button not doing anything in Dispatch UI
* **Fix** incompatibility between clients of different versions

## 0.1.2 (2021-10-08)

* **Added** auto-updater, which will prompt when a new update is available
* **Tweaked** some events when syncing state with game

## 0.1.1 (2021-10-07)

* **Fix** inversed logic for talkover protection
* **Fix** channels with IDs >65535 causing error when displaying sidebar information

## 0.1.0 (2021-10-06)

**Initial release of plugin for alpha testing**