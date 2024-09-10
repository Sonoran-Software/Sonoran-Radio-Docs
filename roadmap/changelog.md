---
description: View the changelog for the Sonoran Radio application and in-game resource.
---

# Changelog

### 2.6.0 (Beta) - Coming Soon

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

### 2.2.1 (Alpha) - 07/03/2024

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
