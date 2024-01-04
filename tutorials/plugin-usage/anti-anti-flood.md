---
title: TeamSpeak Spam Protection
published: true
date: 2022-01-28T05:47:20.402Z
tags: null
editor: markdown
dateCreated: 2022-01-28T05:47:20.402Z
description: Fix TeamSpeak's dreaded anti-flood measures
---

# TeamSpeak Spam Protection

## What is Spam Protection

Spam protection (or Anti-flood) is a policy implemented by TeamSpeaks servers to prevent users from flooding the server with constant packets (essentially a DoS attack). However, this protection can get in the way of Sonoran Radio in some cases: if users are regularly switching frequencies, or keying up and down, then this can cause the server to falsely rate limit users.

![TeamSpeak - Spam Log](https://i.imgur.com/madtWJq.png)

When the server starts blocking commands of a user, sending more commands will only prolong the time that the user must wait until their cooldown has expired.

## How to Fix

This section demonstrates three methods of fixing this issue, two if you're a server owner, and one if you're just a user of the TeamSpeak plugin.

### 1. User Fix

**Prevention Measures** To prevent anti-flood from blocking you on TeamSpeak, keying up and down less frequently or changing frequencies less is an effective way to make sure you do not hit the rate limits.

**Rate Limited** If you've been rate limited, then slow down and take a breather. Further actions (like changing frequencies or keying up and down) will further increase the time you're rate limited. _Reconnecting or restarting TeamSpeak will not get rid of the rate limit_.

### 2. Developer/Owner Fix

If you are an owner or highly permissioned on the affected TeamSpeak server, you can increase the anti-flood limits by going into the Virtual Server settings and raising the values. We recommend 1.5x the values present, or 2x if issues persist.

![TeamSpeak - Edit Virtual Server](https://i.imgur.com/hQKP665.png) ![TeamSpeak - More Button](https://i.imgur.com/kNKVzQ0.png) ![Team speak - Anti-Flood Settings](https://i.imgur.com/5uD9wqm.png)
