---
description: >-
  Pulled over in a traffic stop? You'll hear the real radio chatter when an
  officer has an active radio nearby!
---

# Hear Nearby Radio Chatter

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption><p>Sonoran Radio - Hear Nearby Chatter</p></figcaption></figure>

Pulled over in a traffic stop? You'll hear the real radio chatter when an officer has an active radio nearby!

{% hint style="warning" %}
Due to bandwidth usage, this feature is automatically enabled with the Pro version only!

[Learn more about our paid subscription plans.](../../../pricing/faq/standalone-pricing.md)
{% endhint %}

## Video Example

{% embed url="https://youtu.be/R9-xBm0sGBA" %}

## Usage

### Audio Permissions

Due to browser restrictions, audio playback on a user's device requires user interaction. When users join the server, they will be prompted to press any key to activate Sonoran Radio.

Afterwards, they will be able to hear nearby radio chatter.

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption><p>Sonoran Radio - Nearby Chatter Permission Interaction</p></figcaption></figure>

### Adjust Volume

Players can adjust the nearby radio volume in-game using the `/radiovolume` command.

Ex: `/radiovolume 75` sets the nearby radio to 75% volume.

### Technical Information

When a player is within 15 game units of an active radio, they will hear the live chatter from the nearest radio. If multiple radios within range are tuned to different channels, the player will hear all those channels blended, but the sound will primarily emit from the closest radio source.

_This feature is experimental and subject to both change and improvements._

## In-Game Earpiece

Some communities may offer custom EUP (clothing and accessories) that players can use to personalize their characters. For radio users, an option to wear an earpiece (headphones) could be useful, allowing them to listen to radio chatter privately without others nearby overhearing.

The `config.lua` file's `Config.chatterExclusions` list defines earpiece items (custom EUP prop IDs) that block radio chatter from being heard nearby.

{% hint style="info" %}
This feature only works only with "prop" variations
{% endhint %}

<div>

<figure><img src="../../../.gitbook/assets/image (46).png" alt="" width="147"><figcaption><p>Sonoran Radio - In-Game Radio Earpiece</p></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/image (45).png" alt=""><figcaption><p>Sonoran Radio - Earpiece Configuration</p></figcaption></figure>

</div>
