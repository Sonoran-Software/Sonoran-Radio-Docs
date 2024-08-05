---
description: >-
  Sonoran Radio is partnered with Big Daddy Scripts to offer a FREE copy of
  their radio animations script!
---

# Big Daddy Radio Animations

<figure><img src="../../.gitbook/assets/SONORAN X BIGPAPA2.png" alt=""><figcaption><p>Sonoran Radio x Big Daddy Scripts</p></figcaption></figure>

## What is this offer?

{% hint style="warning" %}
This script requires the pro version of Sonoran Radio standalone.
{% endhint %}

Big Daddy's radio animation script enhances your Sonoran Radio experience by adding five new in-game animations. As one of the most popular scripts of its kind, it offers versatile options based on where your radio is positioned—whether on your chest, shoulders, or handheld. This provides a more immersive and personalized interaction.

## Download and Installation

### 1. Download the Script and License Key

Create an account and [download the latest script resource](https://sonoran.link/bigdaddy) from Big Daddy Scripts.

In the account portal, select your recent order and copy the license key.

### 2. Install The Script

#### A. Extract

Extract the script to your server's `resources` folder.

#### B. License Key

In the `settings.ini` file, paste your license key.

#### C. Ensure the Resource

In your `server.cfg` file, add the following line **after** your Sonoran Radio resource lines:

<pre><code><strong># Start the sonoranradio resource
</strong>ensure sonoranradio

# Permissions for auto-updater (REQUIRED)
add_ace resource.sonoranradio command allow
add_ace resource.sonoranradio_updatehelper command allow

# ----------------NEW----------------
# Big Daddy Radio Animation Script
ensure BigDaddy-RadioAnmimation
</code></pre>

_Sonoran Radio will automatically detect the script named `BigDaddy-RadioAnmimation`, and disable the default Sonoran Radio animation (`disableAnimation` from the `config.lua`)_

### 3. Enjoy!

Once in-game, you can use the `/radioanim` command to open up the customization menu.

This script will automatically detect when you are talking on your Sonoran Radio.

[See the documentation for more information about configuration options and commands.](https://wiki.bigdaddyscripts.com/en/documentation/Radio-Animation)
