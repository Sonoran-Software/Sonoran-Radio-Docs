---
description: Learn more about the in-game radio resource.
---

# Using the In-Game Radio

{% embed url="https://www.youtube.com/watch?v=FSJOzPkS1uE" %}

## Initial Setup

### Displaying the In-Game Radio

By default, the radio display remains visible on-screen at all times. Users can toggle focus on the radio, enabling interaction when needed and un-focusing when done.

1. Use the [customizable keybind](./#setting-your-push-to-talk-ptt-keybind) (Default is `~` right above tab)
2. Use the `/radio` command

Access to the radio can be restricted with [ACE permissions](../configuring-ace-permissions.md).

### Hiding the In-Game Radio

#### A. Via Button

Use the purple button or icon on the radio frames:

<div><figure><img src="../../../../.gitbook/assets/image (85).png" alt="" width="375"><figcaption><p>Vehicle Radio: Hide Button</p></figcaption></figure> <figure><img src="../../../../.gitbook/assets/Screenshot 2024-12-05 124319.png" alt="" width="208"><figcaption><p>Handheld Radio: Hide Button</p></figcaption></figure></div>

#### B. Via Command

Use the `/radio hide` command in-game to hide the radio.

### Logging In

When you first use the in-game resource, you'll need to log in.\
A 4-digit code will appear for you to sign in from your browser.

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="345"><figcaption><p>Sonoran Radio - Login with Link Prompt</p></figcaption></figure>

Open [sonoranradio.com/link](https://sonoranradio.com/link) in a web browser, log in if needed, enter your code, and click "Activate" to log in to the game.

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption><p>Sonoran Radio - Activate Link</p></figcaption></figure>

### Logging Out

You can logout/un-link your in-game radio via the settings menu (gear icon).

<div><figure><img src="../../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>In-Game Radio - Settings</p></figcaption></figure> <figure><img src="../../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>In-Game Radio - Unlink</p></figcaption></figure></div>

***

## Using the In-Game Radio

### Setting your Push-To-Talk (PTT) Keybind

[You can customize your PTT button in your GTA Settings.](fivem-keybinds-and-commands.md)

### Connecting and Switching Channels

The radio will connect when you turn it on with the power button ([unless you need to login first](./#logging-in))

<div data-full-width="false"><figure><img src="../../../../.gitbook/assets/FiveM_b3095_GTAProcess_y5BTRN8idW.png" alt="" width="195"><figcaption><p>Sonoran Radio: Power Button</p></figcaption></figure> <figure><img src="../../../../.gitbook/assets/FiveM_b3095_GTAProcess_8EDvlAfgKq.png" alt="" width="176"><figcaption><p>Sonoran Radio: Channel List</p></figcaption></figure></div>

### Channel Scanning/Listening

<details>

<summary>Scanning Radio Channels</summary>

Scanning a radio channel allows users to hear all transmissions, even if they are not actively transmitting on that channel. However, transmissions on the primary channel (the one you are actively talking on) will take priority, muting transmissions from scanned channels whenever someone speaks on the primary channel.

#### Selecting Scanned Channels ([Modern or Text Display](../customizing-radio-frames.md#screen-styles))

1. Select the Channel Scan Icon
2. Select the channel group to view the contained channels
3. Click on a channel to toggle on/off scanning

[Learn how to toggle a channel scan via command or Stream Deck!](fivem-keybinds-and-commands.md#toggle-channel-scan)

![](<../../../../.gitbook/assets/image (3) (1).png>)![](<../../../../.gitbook/assets/image (5) (1).png>)



Users can also [create a scan list](./#scan-lists) to swap between multiple scanned channels at once.

</details>

### Custom Scan Lists

<details>

<summary>Scan Lists</summary>

Users can scan one or more channels to listen without transmitting. For monitoring multiple channels, "Scan Lists" let users group channels and easily switch between them.

#### Creating a Scan List ([Modern or Text Display](../customizing-radio-frames.md#screen-styles))

1. Toggle scanning on one or more channels.
2. Select the `+` icon next to `Scan Lists` to create a new scan list with the current selection.
3. Scan lists can be reordered via drag-and-drop.
4. Select the adjust button to rename or remove the scan list.
5. Click on the scan list to scan all of the channels inside of it.
6. Scan lists can be reordered via drag-and-drop

[Learn how to toggle a scan list via command or Stream Deck](fivem-keybinds-and-commands.md#toggle-scan-list)!

![](<../../../../.gitbook/assets/image (1) (1) (1).png>)![](<../../../../.gitbook/assets/image (2) (1) (1).png>)

</details>

### Adjust Volume

<details>

<summary>Radio Volume</summary>

#### System-Wide Volume

In the settings menu (gear icon) you can adjust the radio's total volume output.

[You can also use the in-game keybind to quickly adjust volume.](fivem-keybinds-and-commands.md#volume-up-down)

<img src="../../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="In-Game Radio - Settings" data-size="original"><img src="../../../../.gitbook/assets/image (8) (1) (1) (1).png" alt="In-Game Radio - System Volume" data-size="original">

#### Per-User Volume

You can also right-click on any user to adjust their volume specifically.

<img src="../../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1).png" alt="In-Game Radio - Per-User Volume" data-size="original">

</details>

### Adjust Volume With Sirens

<details>

<summary>Automatic Volume Increase w/Sirens</summary>

When in-game, turning on your sirens will increase your overall radio volume by the configured amount. Turning your sirens back off will lower the volume back down.

This feature is automatically integrated with [Luxart Vehicle Control](https://github.com/TrevorBarns/luxart-vehicle-control).\
If the resource is not named `LVC`, the [`config.luxartResourceName` value must be updated](../../../getting-started/installing-the-in-game-resource.md#updates).

For communities not using LVC, the functionality will fall back to a FiveM native that will trigger the functionality if either lights or sirens are activated.

![](<../../../../.gitbook/assets/image (1).png>)

</details>

### Move and Resize the Radio

{% hint style="info" %}
**If you move your radio too far off of your screen:**

Use `/radio reset` to reset the size and position.
{% endhint %}

<details>

<summary>Radio Move and Resize</summary>

On the radio screen, open the `Settings` modal by pressing the gear icon.

Select `Move/Resize`

* Click and drag the radio to change it's position on your screen.
* Hold `ctrl` and drag to resize the radio.
* Press `esc` to save the new size and position.

<img src="../../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="In-Game Radio - Settings" data-size="original"><img src="../../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1).png" alt="In-Game Radio - Move/Resize" data-size="original">

<img src="../../../../.gitbook/assets/image (17).png" alt="In-Game Radio - Adjustment" data-size="original">

</details>

### Escape Mode

<details>

<summary>ESC Radio Display Behavior</summary>

The Escape Mode selector changes the in-game radio display behavior after pressing `ESC`.

`Keep Radio Visible`

* The radio stays visible on `ESC`

`Hide Radio`

* The radio closes on `ESC`

`XMITT (PTT)`

* The radio closes on `ESC`, but is visible while transmitting

![](<../../../../.gitbook/assets/image (2).png>)

</details>

### Panic

<details>

<summary>In-Game Panic</summary>

Pressing the orange panic button on the in-game radio toggles your panic status.

This can also toggle your panic status in [Sonoran CAD](../../../integrations/sonoran-cad-integration.md#cad-panic).

Dispatchers will also be able to see your panic status.

![](<../../../../.gitbook/assets/image (3).png>)

</details>

### Radio Types

Sonoran Radio offers three radio platforms: handheld, top-down HUD, and vehicle.\
All three radio platforms can have [customizable frame styles](./#change-radio-frames).

<figure><img src="../../../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

When opening the radio via `/radio` the handheld radio will display on-screen.\
The vehicle UI will display when opening the radio inside of a vehicle.\
The top-down HUD style can be viewed with the `/radiohud` command.

### Change Radio Frames

The settings menu also allows you to customize your radio frame:

<figure><img src="../../../../.gitbook/assets/image (32).png" alt="" width="165"><figcaption><p>Sonoran Radio - Custom Frames</p></figcaption></figure>

Learn more about customizable radio frames:

{% content-ref url="../customizing-radio-frames.md" %}
[customizing-radio-frames.md](../customizing-radio-frames.md)
{% endcontent-ref %}

## Civilian Usage

### Placing an Emergency (911) Call

Civilians can place an emergency call to speak directly with dispatchers:

{% content-ref url="../../dispatch-panel/emergency-calls.md" %}
[emergency-calls.md](../../dispatch-panel/emergency-calls.md)
{% endcontent-ref %}

## Custom Animations

Unlock multiple more custom radio animations, FREE with Sonoran Radio pro!

<figure><img src="../../../../.gitbook/assets/SONORAN X BIGPAPA2.png" alt=""><figcaption><p>Sonoran Radio x Big Daddy Scripts</p></figcaption></figure>

{% content-ref url="../../../integrations/big-daddy-radio-animations.md" %}
[big-daddy-radio-animations.md](../../../integrations/big-daddy-radio-animations.md)
{% endcontent-ref %}
