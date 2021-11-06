---
title: Using the Plugin
description: Explanations on how to use the plugin features in TeamSpeak
published: true
date: 2021-11-06T04:40:09.169Z
tags: teamspeak, ts, plugin, tutorial
editor: markdown
dateCreated: 2021-10-06T04:39:08.853Z
---

# Prerequisites

> Before continuing, it's expected that you've installed the plugin and understand the core concepts of Sonoran Radio.
{.is-warning}

- [Install TeamSpeak 3 Plugin *Each user needs to install this to use the radio*](/tutorials/install-plugin)
- [Core Concepts *Understand the theory of our radio*](/tutorials/core-concepts)
{.links-list}

# Unauthorized Servers

When connecting to a server that does not enable Sonoran Radio, the plugin will essentially stay dormant. It will display some basic information on the side panel when clicking the virtual server row (the top channel). If you expect the server to be authorized but it isn't, then contact the server owner for assistance.

## Example
![example.png](https://i.imgur.com/EvVvHSQ.png)

# Server Information

On authorized servers, the plugin will display much more information when compared to unauthorized servers. The information is displayed on the right sidebar of your TeamSpeak. The information displayed depends on what type of item you click (i.e. a user will display different info than the channel).

The virtual server (or topmost item) will display information about global authorization status and subscription tier that the TeamSpeak server has. A channel will display whether it is a [patrol channel](#patrol-channels). A client will display information about their frequencies and plugin version (if they also have the plugin installed).

## Examples

|Virtual Server|Channel|Client/User|
|-|-|-|
|![vs_example.png](https://i.imgur.com/yyzETdm.png)|![chan_example.png](https://i.imgur.com/olvbvSY.png)|![user_example.png](https://i.imgur.com/569GuCm.png)|

# Patrol Channels

All channels in a TeamSpeak server **except patrol channels** will have the same behavior as if the plugin weren't installed at all.

Once you have joined a patrol channel, special logic called "talk groups" will be automatically initialized. 

## Frequency Specific Audio

After joining a patrol channel, you may notice that you see people talking without actually hearing them. This is intentional and means that they are either in a different frequency or out of range from you.

Without being in-game, you are only able to hear units transmitting over statewide frequencies (aka repeated frequencies). If you are in-game, you will be able to hear statewide frequencies **AND** units transmitting to with the same `XMIT` frequency as your `RECV` frequency is set (only up to 500 meters).

The latter frequency type discussed above is called "talk around channels," and are only audible to those both in-game and in-range of your radio device. The further away you get from the transmitting radio device, the more interference in the transmission. This means that out-of-game users (like dispatchers) will be unable to hear you *unless* you switch to a statewide frequency.

## Talkover Protection

In patrol channels configured as such, units will be unable to talk over each other. This feature is called "talkover protection." When trying to talk over another unit, you will hear an audible tone that indicates that you must wait for the other unit to stop transmitting to start your transmission.

If you need to make an emergent transmission, you can override this behavior by double-clicking your push-to-talk button and then transmitting.

# Dispatch Panel

For authorized servers, you are able to open the Dispatch UI through `Plugins -> SonoranRadio -> Dispatch UI`
![open_ui.png](https://i.imgur.com/dX9BJXU.png)

> An error will be displayed in the chat box if your current server is not correct or not authorized.
{.is-danger}


## Self Radio Settings

The first page you will see after opening the UI is the tab to change your own radio settings. It will look similar to this:

![self_settings.png](https://i.imgur.com/zEovr1o.png)

You are able to modify your own frequency on this page. If the server has the correct subscription tier, you will also be able to edit your scanned frequencies through this panel.

When editing scanned frequencies, you are able to add a frequency by changing the frequency spinner and pressing `Add`. You can remove frequencies by right-clicking them in the list and pressing `Remove`. Please note that scanner settings only take effect after pressing `Set` on the bottom.

> Please note that when selecting a preset in the `Fill Preset` dropdown, it will not automatically change your frequency. It only fills the boxes for you in the UI, and you'll have to press `Change Frequency` yourself for it to take effect.
{.is-info}

## Channel Clients' Radio Settings

The second page you will see in the UI is the tab to change the radio settings of clients in your current channel. It will look similar to this:

![channel_settings.png](https://i.imgur.com/KEG6akK.png)

You can edit the XMIT/RECV frequencies of another unit by changing the spinners and pressing `Change Frequency`. `Fill Preset` has the same behavior as on the [Self Radio Settings](#self-radio-settings) tab. `Match Selected Client` being checked means that as you click different clients, the XMIT/RECV frequencies will be automatically filled in for that client.

> **Pro Tip** You are able to select multiple clients at the same time by control-clicking the clients or shift-clicking the clients. You are not able to edit the nickname of a client while selecting multiple clients.
{.is-success}