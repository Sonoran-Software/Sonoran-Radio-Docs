---
title: Registering Your Community
description: Before you begin using Sonoran Radio, you will need to register a community. Sonoran Radio uses your Sonoran Software account.
published: true
date: 2021-12-04T20:45:20.988Z
tags: 
editor: markdown
dateCreated: 2021-10-07T06:06:34.627Z
---

# Registering Your Community
Registering your community and setting up Sonoran Radio is fast, easy, and free!

*Note: If you have not already, you will need to create a user account with Sonoran Software, and have the TeamSpeak Plugin Installed*

1. Navigate to SonoranRadio.com and click on the Login Button and enter your Sonoran Software credentials.
![snag_baee8718.png](/snag_baee8718.png)

2. Click on the `Register a Teamspeak Server for Sonoran Radio` button to begin linking your TeamSpeak server.

3. (Optional) Enter a nickname for your server

4. Retrieve the Unique ID of your TeamSpeak server using the Sonoran Radio Plugin.
	* Click on the TeamSpeak Virtual Server
  	* Copy the Unique ID field.
    ![snag_baed5a6f.png](/snag_baed5a6f.png)
> You must have the [TS3 Plugin installed](/tutorials/install-plugin) on your TeamSpeak client before this information will appear
{.is-warning}

    
5. Paste the Server UID into the new server form and press `Register Server`

![unknown.png](https://i.imgur.com/eOTfAkY.png)

6. Copy the Authorization Code given, re-connect to your TeamSpeak Server and paste the code in the popup

> If you are receving an error, it can be one of three common issues: 1. You do have the required permissions (You must be able to modify the server password); 2. You do not have version 0.2.0 or greater of the plugin; 3. You did not set your Server UID properly in the panel.
{.is-warning}

![webpanel.png](https://i.imgur.com/sylq41i.png)
![plugin.png](https://i.imgur.com/yy0PxZy.png)

7. Retrieve the Unique ID of your patrol channel by following the same method as Step 4, however ensure you select the patrol channel.

![snag_baf2f31d.png](/snag_baf2f31d.png)

8. Click on the `Add Patrol Channel` button under the **Patrol Channels** section of the radio management portal. Insert that channels Unique ID and press `Add Patrol Channel`

![snag_baf56630.png](/snag_baf56630.png)
Note: Checking Allow Talkover disables preventing units from talking over one another.

9. To create a new profile, click on the `Add Profile` button on the radio management portal.

 ![snag_bb00cfc2.png](/snag_bb00cfc2.png)
 * Set the display name of the profile. This will display in both TeamSpeak and the in-game radio.
 * Set the Receive Frequency. In Simplex, this should be set to the same as the Transmit Frequency. In Duplex, this is the frequency of the transmissions from the repeater.
 * Set the Transmit Frequency. In Simplex, this should be set to the same as the Receive Frequency. In Duplex, this is the frequency that the repeater is listening for transmissions on.
 * Check the Repeats Transmit Frequency to enable the duplex repeater functionality.
- [Learn More About Simplex & Duplex Mode](/tutorials/core-concepts)
{.links-list}

10. The setup process is complete. You will need to disconnect and reconnect to your teamspeak server. If the setup process was successful, you should see the following:

 * `Server Authenticated` message in teamspeak when you join the server.
 ![snag_bb07b571.png](/snag_bb07b571.png)
 * Your Virtual Server should say `Authenticated`
 ![snag_bb07f2a9.png](/snag_bb07f2a9.png)
 * Your Patrol Channel should be marked as a Patrol Channel
 ![snag_bb08649d.png](/snag_bb08649d.png)