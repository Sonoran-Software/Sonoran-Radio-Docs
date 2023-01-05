---
title: Registering Your Community
description: Before you begin using Sonoran Radio, you will need to register a community. Sonoran Radio uses your Sonoran Software account.
published: true
date: 2023-01-05T21:11:45.543Z
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

7. Note the Channel ID of your patrol channel by following the same method as Step 4, however ensure you select the patrol channel.

![snag_baf2f31d.png](https://i.imgur.com/n7nhAsx.png)

8. Click on the Plus button under the **Patrol Channels** section of the radio management portal. Insert that channels Unique ID and press `Add Patrol Channel`

![UMb4NXq.png](https://i.imgur.com/F5n2Vz7.png)
Note: Checking Allow Talkover disables preventing units from talking over one another.
Note: Customizable Talk-Around Ranges vary from Short Range (600m) to Extra Long Range (1400m) with a 400m difference between each range option. The Customizable Talk-Around Range only applies to talk-around frequencies, transmitted frequencies that don't get repeated over the radio tower network.

9. To create a new profile, click on the Plus button on the radio management portal under the **Profiles** section.

*Basic Profile Creation*
Basic Profile Creation is meant for a quick and easy way to create profiles without the hassle of organizing frequencies. Receiver Frequency & Transmit Frequency with automatically be generated on creation.
 ![sOlsmli.png](https://i.imgur.com/sOlsmli.png)
 * Set the display name of the profile. This will display in both TeamSpeak and the in-game radio.
 
 *Advanced Profile Creation*
 Advanced Profile Creation is meant for a more customizable and in-depth way to create profiles if you have the knowledge of how our Simplex & Duplex radio system works.
 ![SvlxfEp.png](https://i.imgur.com/SvlxfEp.png)
 * Set the Receive Frequency. In Simplex, this should be set to the same as the Transmit Frequency. In Duplex, this is the frequency of the transmissions from the repeater.
 * Set the Transmit Frequency. In Simplex, this should be set to the same as the Receive Frequency. In Duplex, this is the frequency that the repeater is listening for transmissions on.
 * Check the Repeats Transmit Frequency to enable the duplex repeater functionality.
- [Learn More About Simplex & Duplex Mode](/tutorials/core-concepts)
{.links-list}

10. To reorder the position of profiles, click on the `Reorder Profiles` button on the radio management portal.

![0PJHbo7.png](https://i.imgur.com/0PJHbo7.png)
* Drag and drop the rows in the order that you'd like them to be.
* Click the `Save Reordered Profiles` button above the profiles table to save.
* Click the `Cancel Reordered Profiles` button above the profiles table to cancel, it will reset any reordering changes you made.

11. The setup process is complete. You will need to disconnect and reconnect to your teamspeak server. If the setup process was successful, you should see the following:

 * `Server Authenticated` message in teamspeak when you join the server.
 ![snag_bb07b571.png](/snag_bb07b571.png)
 * Your Virtual Server should say `Authenticated`
 ![snag_bb07f2a9.png](/snag_bb07f2a9.png)
 * Your Patrol Channel should be marked as a Patrol Channel
 ![snag_bb08649d.png](/snag_bb08649d.png)