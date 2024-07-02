---
description: Learn more about the in-game radio resource.
---

# Using the In-Game Radio

## Initial Setup

### Accessing the In-Game Radio

#### Keybind

* The default keybind to open Sonoran Radio is `~` (right above Tab)
  * You can also [customize this keybind](using-the-in-game-radio.md#setting-your-push-to-talk-ptt-keybind)

#### Command

* Use the `/radio` command

<details>

<summary>Restrict Radio Access (Permissions)</summary>

If the `acePermsForRadio` option is set to `true` in the [configuration file](installing-the-in-game-resource.md#updates), users will need access to the `sonoranradio.use` ACE permission.

1. Create a Permission Group

Here, we'll create a `police` ACE group that has access to all of the `sonoranradio.general` categorized permissions.

<pre><code><strong># ACE Group = "police"
</strong><strong># Category of permissions = "sonoranradio.general"
</strong><strong>add_principal group.police sonoranradio.general
</strong></code></pre>

2. Assign Permissions to the Group

This adds all of the Sonoran Radio permissions (spawning and saving each repeater type) to the `sonoranradio.towers` category that the `admin` ACE group has access to.

```
# Radio Access (Optional: If `acePermsForRadio` is `true` in config.lua)
# Add the radio usage permission to the "sonoranradio.general" category
add_ace sonoranradio.general sonoranradio.use allow
```

3. Add Users to the ACE Group

This grants a user the `admin` ACE permission group, specific to their in-game license ID.

```
# Add the "police" group
# which contains all of the "sonoranradio.general" category permissions
# to a specific user (via GTA license #)
add_principal identifier.license:{GTA License} group.police
```

</details>

### Logging In

When you first use the in-game resource, you'll need to log in.\
A 4-digit code will appear for you to sign in from your browser.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Sonoran Radio - Login with Link Prompt</p></figcaption></figure>

Open [sonoranradio.com/link](https://sonoranradio.com/link) in a web browser, log in if needed, enter your code, and click "Activate" to log in to the game.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Sonoran Radio - Activate Link</p></figcaption></figure>

## Using the In-Game Radio

### Setting your Push-To-Talk (PTT) Keybind

By default, there is no PTT keybind set. You can set one in your GTA `Settings` -> `Key Bindings` -> `FiveM` -> `Radio PTT`

<figure><img src="../../.gitbook/assets/FiveM_b3095_GTAProcess_WGNNv8eoKV.png" alt=""><figcaption></figcaption></figure>

### Connecting and Switching Channels

The radio will connect when you turn it on with the power button ([unless you need to login first](using-the-in-game-radio.md#logging-in))

<div data-full-width="false">

<figure><img src="../../.gitbook/assets/FiveM_b3095_GTAProcess_y5BTRN8idW.png" alt=""><figcaption></figcaption></figure>

</div>

You can scroll through the radio channels with the channel select dial on top, or choose a channel using the UI

<figure><img src="../../.gitbook/assets/FiveM_b3095_GTAProcess_8EDvlAfgKq.png" alt=""><figcaption></figcaption></figure>
