---
description: In-game players can call 911 and talk to you through Sonoran Radio!
---

# Emergency Calls

<figure><img src="../../../.gitbook/assets/Customizable Tone Board Promo (1).png" alt=""><figcaption><p>Sonoran Radio - Emergency Calls</p></figcaption></figure>

## Emergency Calling In-Game

Players are able to make an emergency call in FiveM with `/radio 911`. This will place them in a call on the Dispatch Panel waiting for a dispatcher.

<div><figure><img src="../../../.gitbook/assets/image (81).png" alt=""><figcaption><p>Sonoran Radio FiveM - Emergency Call</p></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (82).png" alt=""><figcaption><p>Sonoran Radio - Dispatch Panel</p></figcaption></figure></div>

## Answering the Emergency Call

You can join and listen to an emergency call using the microphone and headphone buttons, just like any other channel in Sonoran Radio. The buttons will highlight green and red respectively when enabled

{% hint style="info" %}
Mic clicks are disabled in emergency channels
{% endhint %}

<div align="center" data-full-width="false"><figure><img src="../../../.gitbook/assets/image (83).png" alt=""><figcaption><p>Sonoran Radio - Speaking in 911 Call</p></figcaption></figure></div>

## Ending the Emergency Call

Dispatchers can end an emergency call with the red "End Call" button, and in-game players can end it by using `/radio 911` again.

<figure><img src="../../../.gitbook/assets/image (84).png" alt=""><figcaption><p>Sonoran Radio - End 911 Call</p></figcaption></figure>

## Redial the Caller

In some cases, the caller may hang up or dispatch needs to call them back for more information.

Once the call has ended, a `Re-dial {user}` option will appear. Click the green call button to re-dial.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## Customize The Emergency Number & Banner

By [editing the config file](../../getting-started/installing-the-in-game-resource.md#updates) you can customize the following options:

1. Customize `911` to any other number or word by editing the `emergencyCommand` property.
2. Hide the user's emergency call banner by setting `showEmergencyCallHelp` to `false`.

## Integrated Phone Scripts

Sonoran Radio also integrates with popular FiveM phone scripts like LB Phone!

{% content-ref url="../../integrations/fivem-phone-scripts.md" %}
[fivem-phone-scripts.md](../../integrations/fivem-phone-scripts.md)
{% endcontent-ref %}

## Developer Documentation

Third-party scripts, such as a phone system, can also programmatically start and end emergency calls.

{% content-ref url="../../../developer-documentation/developer-documentation/resource-events.md" %}
[resource-events.md](../../../developer-documentation/developer-documentation/resource-events.md)
{% endcontent-ref %}

