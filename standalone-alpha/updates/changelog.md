---
description: View the changelog for the Sonoran Radio application and in-game resource.
---

# Changelog

### 2.3.0 (Alpha) - Coming Soon!

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
