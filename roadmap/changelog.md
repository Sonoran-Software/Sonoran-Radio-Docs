---
description: View the changelog for the Sonoran Radio application and in-game resource.
---

# Changelog

### 2.13.0 - 01/21/2025

{% tabs %}
{% tab title="New" %}
In-Game Physical Scanners

* Added in-game physical scanner items for civilians to hear radio transmissions

Transmission Logs

* Added transmission logs in the dispatch panel with optional AI transcriptions

\#26361 Transmit to In-Game Speakers

* Added the ability to locally record microphone audio to play over the tone board to radios and in-game speakers

AI: Tone Text to Speech

* Added the ability to generate AI text to speech tones

\#26385 Stacked Tones

* Added the ability to "stack" and play multiple tones in a row

\#26534 In-Game/Mobile Radio Scan Lists

* Added configurable scan lists to quickly swap between multiple scanned channel groups

\#26414 Persist scanned channels

* Scanned channels now save locally to be restored when turning the radio back on

Free Vocoder

* Made the new vocoder available to the free version of Sonoran Radio

In-Game Text Radio SONORAN Branding

* Added small branding to the text based display in-game when large enough (vehicle display)

Vocoder PTT Timing

* Overhauled and improved vocoder PTT handling to ensure local UIs update much faster without a long delay before and after the transmissions
{% endtab %}

{% tab title="Fixed" %}
\#26458 Connect: Permission Denied Mic General Error

* Added improved notice and handling in the browser version if microphone permissions are not granted

Hotkey: Prevent Left Mouse

* Blacklisted the left mouse button from being used as a hotkey
{% endtab %}
{% endtabs %}

### 2.12.0 (Full Release) - 12/31/2024

{% tabs %}
{% tab title="New" %}
Radio Chatter: Vehicle Detection

* Added vehicle detection to lower and muffle nearby radio chatter if the user enters a vehicle. Chatter volume resumes if the window is down/broken or the door opens.

Emergency Call: Nearby Chatter

* When a user is making an emergency call on the phone, nearby users can now faintly hear the dispatcher talking on the other side of the phone.

Voice Effect: Clipping

* Added a new "clipping" voice effect to cut audio in and out when the radio signal is poor. This effect is designed to pair particularly well with the vocoder.

Transfer Community

* Added an option in the administration panel to transfer community ownership to another user.

Emergency Call: SFX

* Added a community customizable incoming emergency call sound effect for dispatchers.
{% endtab %}

{% tab title="Fixed" %}
Backend Error API Clearnup

* Cleaned up general backend errors from the API

In-Game Debug

* Removed leftover in-game debug prints
{% endtab %}
{% endtabs %}

### 2.11.0 (Beta) - 12/19/2024

{% tabs %}
{% tab title="New" %}
Text Style Display

* Added a new screen display style with a "text-based" UI for older radio styles

Settings UI: Tabs

* Overhauled the settings modal with tabs for each section

Hide Radio ESC User Config

* Added three radio display options for ESC behavior (stay on screen, hide, show only while transmitting)

Expired Community Removal

* Added automatic community deletion, if on the free version, after 30 days with a 21 day notice
{% endtab %}

{% tab title="Fixed" %}
Emergency Call: Fix Hear Radio Chatter Nearby

* Fixed an issue where users could not hear nearby radio chatter while on a 911 call

Hide/Close Radio when QB Item Gone

* Fixed an issue where removing the QB/ESX radio item would not turn off and remove the radio from the user's screen
{% endtab %}
{% endtabs %}

### 2.10.0 (Beta) - 12/03/2024

{% tabs %}
{% tab title="New" %}
\#25437 Radio In-Game Display

* The in-game radio will now persist on the user's screen, until they use `/radio hide`. Per-user customization will be released in a coming update.

\#25917 - EUP Chatter

* Added support for drawable items (in addition to the existing prop support) for EUP chatter exclusion.

Permission Reactivity

* When connected to the radio, user permissions will now update in real time.

Customize 911 Command

* Added a new config `emergencyCallCommand` property to customize the /radio 911 to other numbers or words based on locality.

Configure Default Keybinds

* Added new configuration values to customize the default radio keybinds for new in-game users.

In-Game Unlink via Pending Screen

* Added an account un-link for the in-game pending community approval screen.

Community Cards - Leave Community

* Added a leave community button in the portal.

In-Game Audio Subprocess Info

* Added a short URL guide in the in-game volume slider to help users who may be having a hard time hearing people.

Homepage - Emergency Call Promo

* Added a promotional tab on the front page for the in-game emergency call feature.
{% endtab %}

{% tab title="Fixed" %}
\#25858 Radio Frames

* Fixed an issue causing some communities to have no frame options available in settings based on their config values.

HUD Disconnect

* Fixed an issue causing the HUD view to show as disconnected.

\#25846 - Connected Users API

* Fixed an API 500 error when requesting the active users, but none are connected.

\#25741 - Radio Inventory

* Fixed an issue where using enforceRadioItem would throw an error that the radio item is not in your inventory.
{% endtab %}
{% endtabs %}

### 2.9.0 (Beta) - 11/07/2024

{% tabs %}
{% tab title="New" %}
In-Game Emergency Calls

* Added a way for players in-game to place an emergency (911) call to dispatchers

Developer Export - Radio Signal

* Added an export to get a user's radio signal quality

Developer Export - Panic

* Added an export to listen for a radio panic press

\#24896 Radio Item - Customize ID and Name

* Added customization options for the in-game radio item's ID and name

Auto-Join User on URL Load

* Users automatically join the community if they load a community's specific URL

Disable PTT SFX For Myself and/or Others

* Added a settings option to disable hearing mic-clicks for yourself and/or other users

Mute Scanned When Transmitting

* Added a settings option to mute scanned channels while transmitting

Debug Mode Toggle Command

* Added a toggle command for debug mode

Sonoran Account Avatar

* Added the user's Sonoran account avatar in the panel

Core Security Update

* Improved credential storage security

Browser Hotkey Notice - Not Global

* Added a notice in the settings page, if using the web version, that hotkeys are not "global" and the page must be in focus
{% endtab %}

{% tab title="Fixed" %}
Apple Silicon Hotkey Fix

* Fixed an issue causing global desktop hotkeys to be unavailable on Apple silicon based computers

In-Game Channel Selector - Private Channels

* Fixed an issue allowing users without permissions to access a private channel if they used the channel selector in-game

Toggle repeater mapping spamming chat

* Removed debug logs on repeater toggle

\#24958 QB Item Check Function

* Updated a depreciated QB item check method

HF: #25273 - PTT/Audio Flicker

* Fixed an issue causing vMenu Proxychat and Mumble Chat to flicker and stick with TalkSync enabled

HF: QB Metadata Tower Break

* Fixed an issue in QB Core mode causing tower signals to always be perfiect if the player had no metadata property.

HF: Member Tab

* Fixed an issue causing the members tab to not display if the user had a permission to kick, rename, or approve members but not the admin permission.

HF: Channel Permissions Owner Bypass

* Fixed an issue causing private channels to be hidden for the server owner.

HF: Move User 500

* Fixed an issue where moving your channel via context menu would throw a 500 error.

HF: Channel Add in Group via Dispatch

* Fixed an issue where adding a new channel via dispatch panel would put it in the first channel group, not the group that it was added from.

HF: TTS Replay On Reconnect

* Fixed an issue where connecting to a non-default channel, disconnecting by switching radio panel tabs, and re-connecting would start playing the TTS of the old channel name before correcting.

HF: AI TTS Generation on Create Channel

* Fixed an issue causing AI TTS generation to fail when creating a new channel.
{% endtab %}
{% endtabs %}

### 2.8.0 (Beta) - 10/10/2024

{% tabs %}
{% tab title="New" %}
CAD Integration

* Added `sonrad` integration to display Sonoran CAD call information on the in-game radio, along with panic functionality

Top-Down HUD Improvements

* Improved the top-down radio HUD to display the channel name, frequencies, and color changes when a user is transmitting

Talkover Override

* Added a new permission granting users the ability to double-press their PTT button to override the talkover protection and silence the other transmitter

CMS Sync - Talkover Override Permission

* Added the ability to manage talkover override permission via Sonoran CMS

Talkover Override Success Tone

* Added a new, community-customizable talkover override success sound effect

Homepage Revamp

* Completely revamped the homepage for feature highlights

UI Cleanup/Component Optimization

* General internal cleanup and optimizations, making way for new future UI possibilities

Community Kick - Disconnect from Radio

* When a player is kicked from the community (via Radio members tab or CMS) they will now be automatically disconnected from the radio, preventing them from transmitting any further

Home Button - Auto-Reconnect

* Pressing the home button on the in-game radio (to hard refresh) will now automatically re-connect the user

Optimized Signal Quality Reports

* Optimized in-game tower signal reporting to spam fewer updates across the websockets, only reporting when there is a significant enough change
{% endtab %}

{% tab title="Fixed" %}
Permission Checks

* Fixed multiple backend permission checks preventing users without the `Admin` permission from accessing functionality

Key Input on Power Toggle

* Fixed an issue causing the in-game "press any key" popup to display every time you turned off/on the radio, instead of just once at the initial game join

\#25095 - TTS Fast

* AI channel name TTS will now stop playing if you quickly switch to another channel before the audio has finished

Radio Frame - Persist Selection

* Fixed an issue where selecting a different radio frame in the settings would not save/persist after closing the radio

Mobile repeaters won't toggle on

* Fixed an issue causing the `G` button in vehicles configured to act as a mobile repeater to not work

Admin Panels - No Perm Redirect

* Added local permission checks to prevent users from loading UI panels by changing the browser URL, even though the backend properly prevented data manipulation

Unable to Leave Pending Community

* Fixed an unauthorized error from happening when trying to leave a community you were pending in.

New User - Unknown Display Name

* Fixed an issue where a user newly joining the community and connecting to the radio would display as "Unknown User" to people already connected

QB Reference Error

* Fixed an error causing the in-game resource to fail under certain QB Core modes
{% endtab %}
{% endtabs %}

### 2.7.2 (Beta) - 09/27/2024

{% tabs %}
{% tab title="Fixed" %}
Voice Degradation

* Fixed an issue causing some users to experience gradual voice degradation that was only fixed after refreshing/power toggling the radio

Digital Voice Effect

* Smoothed and reduced the initial digital voice filter effect
{% endtab %}
{% endtabs %}

### 2.7.0 (Beta) - 09/25/2024

{% tabs %}
{% tab title="New" %}
Voice Effect Customization

* Added the ability to create multiple custom voice effect filters and apply them per-channel.

Tone Board - Play to In-Game Speakers

* Added the ability configure in-game speakers and play radio tones to them.

Tunnel Signal Degrade

* Added the ability to configure in-game tunnels and other 3D areas that reduce radio signal quality.

AI Channel Text-To-Speech

* Added automatic AI generated channel name TTS that will play when connecting and switching channels.

Context Menu Name Change

* Added the ability to right-click on a connected user to quickly modify their display name.

Private Channel Permissions

* Added the ability to toggle channel visibility to private, requiring a user permission to connect.

CMS x Radio - Private Channel Permissions

* Added the ability to automatically manage private radio channel permissions via Sonoran CMS.

CMS x Radio - Name Sync

* Added the ability to automatically manage radio display names via Sonoran CMS.

Nearby Radio Chatter - Earpiece

* Added the ability to configure in-game earpiece EUP that will prevent people nearby from hearing your radio.

Game Resource Optimization

* Added multiple new in-game optimizations to improve resource performance.

Connected Users List - Save Position

* Added size and position persistence to the in-game connected users list.

Proxy URL - Retry

* Added retry logic and UI errors in the event that the in-game resource can not get the proxy URL.
{% endtab %}

{% tab title="Fixed" %}
\#24819 - Talkover on Scan

* Fixed an issue causing talkover protection to prevent someone listening to a channel with someone transmitting from transmitting in their own, clear channel.

Tone Configuration Fixes

* Fixed multiple issues with tone files and tone cosmetic customizations not being persisted or removed.

CAD Livemap Repeater Types

* Fixed an issue causing only the radio tower type repeaters to show on the CAD livemap.
{% endtab %}
{% endtabs %}

### 2.6.2 (Beta) - 09/13/2024 (In-Game Only)

{% tabs %}
{% tab title="Fixed" %}
In-Game Connected Users

* Fixed an issue with the connected users list causing some names to not change to green while the user was talking
{% endtab %}
{% endtabs %}

### 2.6.1 (Beta) - 09/11/2024 (In-Game Only)

{% tabs %}
{% tab title="New" %}
In-Game Connected Users

* When talking, user names will display as green
* Added proper CSS ellipsis to display names
* Added tooltip to user display names
* Alphabetically sorted display names
{% endtab %}

{% tab title="Fixed" %}
Radio and Connected User Hide

* Fixed an issue causing the radio and connected user menu to not hide when pressing ESC if no hotkey was set
{% endtab %}
{% endtabs %}

### 2.6.0 (Beta) - 09/11/2024

{% tabs %}
{% tab title="New" %}
Hear Chatter In-Game

* Civilians can now hear live radio chatter when there is a nearby radio. This requires the pro version.

Top-Down HUD

* Added the top-down radio HUD UI in-game

Multi-Frame

* Added four radio frame options in-game to choose from, customizable by the community

In-Game Connected List

* Added an in-game connected users list

Cache Busting

* Added improved cache busting to ensure in-game radio updates are recieved faster by users

Mic Clicks - For Local Only

* Per-user custom mic clicks are now only heard by that user, instead of everyone on the radio

In-Game Talk Sync

* Talk in-game at the same time you talk in the radio
{% endtab %}

{% tab title="Fixed" %}
Vehicle Radio Blue Screen

* Fixed an issue causing switching from the handheld to vehicle radio causing a blue radio screen for some users until turned off and back on

In-Game Talkover

* Fixed an issue allowing some users to talkover others while talkover protection was enabled
{% endtab %}
{% endtabs %}

### 2.5.0 (Beta) - 08/16/2024

{% tabs %}
{% tab title="New" %}
Sonoran CMS Integration

* Added the ability to manage your radio user's joining, permissions, and kicking via Sonoran CMS ranks and Discord roles.

Input/Output Device Selection

* Added the ability to customize and test the input and output sources via the settings menu.

Tone Board

* Added a customizable toneboard allowing dispatchers to play or repeat tones on specific channels and groups.

Server Customization UI

* Consolidated the server customization menu into organized tabs and improved the in-game install with a step-by-step tutorial.

Animation Download

* Added a tutorial step in the server customization menu to install the custom radio animations.
{% endtab %}

{% tab title="Fixed" %}
New Join 403

* Hotfix: Fixed an issue causing newly joined members to get an error on the web and desktop versions.
{% endtab %}
{% endtabs %}

### 2.4.0 (Alpha) - 08/05/2024

{% tabs %}
{% tab title="New" %}
Channel Groups & Organization

* Added the ability to create channel groups and easily organize via drag-and-drop

Custom Talkover Tone

* Added the ability to customize a community-wide talkover error SFX

Signal Bars

* Added visual signal bars in-game to view your tower connectivity

SFX Volume

* Added the ability to customize the sound effect volume in the settings menu

Auto-Join on Link

* Users now automatically join the Sonoran Radio community after linking in-game

In-Game Enhanced Error Handling

* Improved errors and ensured the resource fails to start without a proper community ID and API key

Mobile UI improvements

* Added multiple improvements for mobile users, including a dedicated UI for the radio panel

Mobile PTT Button

* Added a push to talk button to the mobile version (web, apps coming soon) to utilize the rado on mobile devices
{% endtab %}

{% tab title="Fixed" %}
Fix: Desktop Updater

* Fixed an issue causing the desktop application auto-updater from working

PTT In-Game & Radio

* Fixed an issue preventing scripts from making the player talk in-game at the same time as they're talking on the radio

\#23608 - Server Members

* Fixed an issue limiting the number of users visible in the server members tab

\#23542 - Tower Components

* Fixed an issue causing pieces of a radio tower to be left after removal

\#23758 Discord and Apple Login Window

* Fixed an issue on the desktop app opening the radio in a second window after login via Discord or Apple
{% endtab %}
{% endtabs %}



### 2.3.0 (Alpha) - 7/11/2024

{% tabs %}
{% tab title="New" %}
Repeaters - UI Menu

* Added an in-game repeater menu to add, edit, and remove repeaters.

In-Game Volume

* Added the ability to adjust the system-wide volume in-game via the settings menu.

In-Game Per-User Volume

* Added the ability to right click on a user in-game to adjust their volume.

Panel - Customized Download

* Added a new download link in the radio panel that includes a pre-configured community ID and API key.

In-game Radio - Logout

* Added an option to logout and unlink your radio in-game via the settings menu.

Startup - Link IP

* Added an automatic API call to link your server's IP address to your community ID. This will be used for an upcoming integration.

API Key - Rotate

* Added the ability to rotate and refresh your API key if leaked.

Menu CMS Discovery

* Added the CMS community discovery spotlight to the portal's community selection menu.
{% endtab %}

{% tab title="Fixed" %}
Talkover Protection In-Game

* Fixed an issue causing talkover protection in-game to fail.

Distortion Inconsistencies

* Fixed an issue causing in-game distortion due to tower signal to not work consistently.

In-Game Permission Re-Request

* Fixed an issue causing the user to be asked for microphone permissions on every join.
{% endtab %}
{% endtabs %}

### 2.2.1 (Alpha) - 07/03/2024 (In-Game Only)

{% tabs %}
{% tab title="Fixed" %}
Tower Distance

* Fixed an issue causing tower distortion levels to "freeze" in certain cases.
{% endtab %}
{% endtabs %}

### 2.2.0 (Alpha) - 07/02/2024

{% tabs %}
{% tab title="New" %}
In-Game Tower Signal

* Added variable audio distortion based on how close a user in-game is to a radio repeater model.

User Display Names

* Added the ability to customize user display names and two new permissions to set who can change their, and others', display name.

Link UI Refresh

* Improved the /link portal UI with automatic focusing, forward/back navigation, and submission.

In-Game Towers

* Added three radio repeater models for in-game signal strength.

In-Game Resize and Move

* Added the ability to resize and move the radio UI.

Custom Animation Support

* Added the ability to disable in-game animations while talking, for custom animation scripts.

Developer Exports - PTT

* Added developer exports when a user activates and deactivates their PTT hotkey.
{% endtab %}

{% tab title="Fixed" %}
\#23262 - Desktop Hotkey

* Fixed an issue with updating your keybind not setting until an application restart
*
{% endtab %}
{% endtabs %}



### 2.1.1 (Alpha) - 06/21/2024

{% tabs %}
{% tab title="New" %}
Desktop Application - Hotkey Setting

* Improved handling for detecting a wider array of hotkeys in the desktop application, including standard mouse buttons.
{% endtab %}
{% endtabs %}

### 2.1.0 (Alpha) - 06/18/2024

{% tabs %}
{% tab title="New" %}
Login Link

* New login for in-game resource/mobile

Community ID

* Use community IDs in URL instead of numeric IDs

Volume Control

* Added per-user volume controls

Talkover Protection

* Added toggleable talkover protection

Channel Change: Drag-and-drop

* Move users by dragging and dropping
{% endtab %}

{% tab title="Fixes" %}
* Fixed connecting on another window redirecting to home (which would break the in-game resource)
{% endtab %}
{% endtabs %}

### 2.0.1 (Alpha) - 06/18/2024

{% tabs %}
{% tab title="Fixes" %}
Community ID

* Accept community ID in place of standalone ID

\#22925 - ESC Error

* Fixed ESC with the radio open causing an error, preventing you from leaving the radio
{% endtab %}
{% endtabs %}

### 2.0.0 (Alpha) - 06/06/2024

{% tabs %}
{% tab title="New" %}
Initial Release
{% endtab %}
{% endtabs %}
