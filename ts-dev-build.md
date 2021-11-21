---
title: Development Build
description: Learn how to install and use the development build of the TeamSpeak plugin
published: true
date: 2021-11-21T07:00:43.685Z
tags: 
editor: markdown
dateCreated: 2021-11-21T07:00:43.685Z
---

# Disclaimer

The Development Build is a version of the plugin that allows you to mess around with features that are usually locked behind paywalls in the production plugin. This may help you in developing integrations with the plugin you might otherwise not be able to make.

However, the Development Build of the plugin is not meant as a replacement for the production build. It may be unstable, and include features that could be dropped from production.

## Warning Dialog

When using the Development Build of the plugin in a patrol channel, every 10 or so transmissions will cause a dialog to popup and every connection you have to be muted. This is to prevent people from using the Development Build as a production replacement.

![example.png](https://i.imgur.com/I1OG9Bw.png)

# Install the Plugin

To install the plugin, you can download the installer from one of these links:

- [SonoranRadio_win64.ts3_plugin *64-bit Development Build*](https://download.sonoransoftware.com/sonoranradio/dev/archive/SonoranRadio_win64.ts3_plugin)
- [SonoranRadio_win32.ts3_plugin *32-bit Development Build*](https://download.sonoransoftware.com/sonoranradio/dev/archive/SonoranRadio_win32.ts3_plugin)
{.links-list}

> Please note that this installer will look identical to the production installer, other than the version that will look similar to `dev-1234abcd`
{.is-info}

## Auto-Updater

The Development Build will automatically prompt with new updates for development testing versions

# Portal

The Development Build of the plugin will use [https://radio.dev.sonoransoftware.com](https://radio.dev.sonoransoftware.com) as the portal. You are able to freely create and modify communities on this portal, which is completely separate from the production portal

> **WARNING**: Data may be purged randomly from this system with no prior notice.
{.is-warning}

## Accounts

Accounts on this portal are completely separate from production accounts. If you already have a development CAD or CMS account, you can use it here. Otherwise, you will need to create a new account

## Billing Portal

To test out premium features with the Development Build, follow these steps:
1. Navigate to the billing portal
2. Click `New Subscription`, the level you want, and the server you want
3. Enter the card number `4242 4242 4242 4242` with any expiration date and CVC
4. Click "Subscribe"