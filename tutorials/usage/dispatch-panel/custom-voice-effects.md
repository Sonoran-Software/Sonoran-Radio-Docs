---
description: Customize digital and analog style voice effects for your community!
---

# Custom Voice Effects

<figure><img src="../../../.gitbook/assets/Radio FX (1).png" alt=""><figcaption><p>Sonoran Radio: Voice Effect Customization</p></figcaption></figure>

{% hint style="warning" %}
Unless on the Pro version, communities are limited to one voice effect style.

[Learn more about our paid plans](../../../pricing/faq/).
{% endhint %}

## Available Voice Effects

Sonoran Radio lets you create custom voice effect profiles for user audio. These effects can be independently assigned to specific radio channels and emergency calls.

Expand the `Vocoder`, `Clipping`, `Digital`, `Analog` and `Equalizer` boxes for specific customizations.

By clicking the microphone icon and using the signal strength slider, you can hear how the effect will sound when users are talking.

### Vocoder

{% hint style="danger" %}
This feature is currently in early-access, available only on the **pro** subscription.
{% endhint %}

{% hint style="info" %}
The **vocoder** effect remains consistent and does not fluctuate based on [in-game signal strength](../in-game-radio/in-game-repeaters.md)
{% endhint %}

The Vocoder voice effect simulates a modern P25-style radio compression using an AMBE-like encoding approach, commonly heard in proprietary digital radio systems. It’s ideal for communities seeking realistic conditions and authentic downsides.

When enabled, audio is routed through a vocoder for encoding and decoding before broadcast, causing a slight transmission delay.

**It is recommended to use the** [**clipping voice effect**](custom-voice-effects.md#clipping) **in addition to the vocoder to have in-game signal strength impact the transmission quality.**

### Clipping

The clipping voice effect mutes or "clips" audio intermittently based on in-game signal strength. As the signal weakens, more audio is cut, making transmissions increasingly difficult to understand.

### Digital

The digital voice effect applies bitrate compression to the audio, causing it to sound increasingly robotic and harder to understand as signal quality decreases.

### Analog

The analog voice effect adds static and scratchiness to the audio, making it sound progressively fuzzier and less clear as signal quality deteriorates.

### Equalizer (EQ)

{% hint style="info" %}
This **EQ** effect remains consistent and does not fluctuate based on [in-game signal strength](../in-game-radio/in-game-repeaters.md)
{% endhint %}

The equalizer effect allows you to boost or reduce frequencies in the high, mid, and low ranges.

_**Tip:** For a "tin can" effect, increase the mid frequencies while reducing the low and high ranges._

## Applying the Voice Effect

## To Radio Channels

In the [channel editor, you can select the desired voice effect](configure-channels.md#setting-the-voice-effect). This voice effect will apply to anyone talking in that channel.

<figure><img src="../../../.gitbook/assets/image (93).png" alt="" width="282"><figcaption><p>Sonoran Radio: Channel Voice Effect</p></figcaption></figure>

### To Emergency Calls

To apply a custom voice effect for [emergency phone calls](emergency-calls.md), toggle the phone icon in the voice effect tab.

**Note:** If no custom voice effect is selected for emergency calls, a default "tin can" EQ effect will be applied.

<figure><img src="../../../.gitbook/assets/image (92).png" alt="" width="375"><figcaption><p>Sonoran Radio: Emergency Call Voice Effect Selection</p></figcaption></figure>
