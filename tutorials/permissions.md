---
title: Permissions
description: Permissions are a way to restrict actions to specific groups, to help combat trolling and abuse
published: true
date: 2022-03-12T00:19:41.165Z
tags: 
editor: markdown
dateCreated: 2022-03-12T00:18:16.464Z
---

# Permissions

Permissions are able to be added or removed from Sonoran Radio in the [web panel](https://sonoranradio.com/). As of now, permissions are server group only, meaning that they reach everywhere in the TeamSpeak equally (you cannot have permissions effect certain channels or clients, only server gruops).

## Server Group IDs

To find server group IDs, enable the `Client Group Info Data` option for the Sonoran Radio plugin:

![plugin_menu.png](https://i.imgur.com/b43tLvp.png)

![settings.png](https://i.imgur.com/zv8Bz1i.png)

After enabling the option, you're able to click on a client and see their server groups, along with their server group IDs in parentheses.

![groups.png](https://i.imgur.com/T3LkEEa.png)

## Setup on Webpanel

Adding a permission in the webpanel is as easy as clicking `Add Permission`, inputting the server group, and selecting the permission. For each entry, only input one server group per permission.

If you wish to have multiple server groups per permission, then you must create multiple entries with different server groups, but the same permission.

> Unless atleast one entry for a permission is created in the webpanel, then the permission will be granted to every server group. If you wish for nobody to obtain a permission, then create an entry for a nonexistant group (like group ID `0`).
{.is-info}


![perms.png](https://i.imgur.com/8rRxSmw.png)

![add_perm.png](https://i.imgur.com/UIyfJM5.png)

> Add descriptive nicknames to help identify what the permission does for the future. It can be hard to decipher otherwise.
{.is-success}

## Current Permissions

**Free** servers do not have any permission customization.

|Name|Subscription Requirement|Grants|Introduced|
|-|-|-|-|
|Open Dispatch UI|Plus|The ability to open the Dispatch UI|0.4.0|
|Modify Channel User|Plus|The ability to modify other units from the Dispatch UI|0.4.0|
|Talkover Protection Override|Plus|The ability to double-click PTT to talk over another client|0.4.0|
|Radio Lock|Pro|The [Radio Lock](/tutorials/plugin-usage#unit-quick-actions) feature|0.4.0|
|Radio Attention|Pro|The [Radio Attention](/tutorials/plugin-usage#unit-quick-actions) feature|0.4.0|