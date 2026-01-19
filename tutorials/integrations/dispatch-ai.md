---
description: >-
  Speak to our AI dispatcher over the radio to manage CAD status, dispatch
  calls, run record lookups, and more.
---

# Dispatch AI

{% hint style="danger" %}
This feature is available to select communities in our beta testing group and is **not yet available to the public**.
{% endhint %}

{% hint style="warning" %}
This feature requires **Sonoran One**, which includes the pro version of Sonoran Radio, CAD, and more.

[Learn more about our paid subscription plans.](../../pricing/pricing-faq/standalone-pricing.md)
{% endhint %}

## Setup

### 1. Copy Sonoran CAD API Information

<details>

<summary>Copy Sonoran CAD API Information</summary>

Dispatch AI requires a Sonoran CAD community ID, API key, and server ID.

The community ID and API key are located in the **Admin** panel > **Advanced** > **In-Game Integration** > **Web API**.

The server ID can be found in the **Admin** panel > **Customization** > **Servers**. The default server ID is `1`.

<div><figure><img src="../../.gitbook/assets/image (134).png" alt="" width="375"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (135).png" alt="" width="375"><figcaption></figcaption></figure></div>

</details>

### 2. Link CAD In Radio

<details>

<summary>Link CAD In Radio</summary>

In the radio **Customization** panel > **Info** > Select a server (or create one) and click on the Sonoran CAD icon. This will open a popup modal to enter in your CAD's community ID, API key, and server ID.

<div><figure><img src="../../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure></div>

</details>

### 3. Prompt Customization

<details>

<summary>AI Prompt Phrases</summary>

The AI has a set of tools it can use to take action in the CAD and on the radio—such as running lookups, creating calls, or updating statuses.

Radio traffic varies by community. One agency might say, “show me out on traffic with a blue sedan,” while another says, “create a traffic stop call with a blue sedan.”

Prompt phrase customization lets you train the AI to map your agency’s specific radio language to the correct system actions, so it responds appropriately to local lingo.

Keep your phrases short and direct. Adding too many phrases can eventually overload the AI's context window.

</details>

## Invoke the AI

<details>

<summary>Via Wake Work</summary>

When pressing your push-to-talk key, a local AI listens to your microphone feed for the customizable wake word. By default, this is **Dispatch**.

Users can customize their wake word by pressing the microphone button and speaking their custom wake word.

Communities can also [customize the default wake word for all users](../usage/dispatch-panel/default-user-settings.md).

<figure><img src="../../.gitbook/assets/image.png" alt="" width="260"><figcaption></figcaption></figure>

### Prompting the AI

In order to reduce false triggers and conserve local resources, the AI will only listen to the first five seconds of your transmission. This amount can be modified in the **Advanced** tab of the **Audio** settings.

Upon detection of the wake word, an audible beep indicates that the AI has been activated. Users may begin speaking before the beep is heard, as long as the tone occurs at some point during the same transmission.

**Example**

If your wake word is **Dispatch**, then your transmissions to the AI would be as follows:

\<wake word>, \<optional: my unit number>, \<action to do>\
&#xNAN;_**Dispatch**, A-10, mark me as available._\
&#xNAN;_**Dispatch**, A-10, run a lookup on the license plate ABC123_

</details>

<details>

<summary>Via Hotkey</summary>

FiveM users can also set a manual keybind in the settings. Pressing this keybind will enable the AI (same as the wake word) for your transmission.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt="" width="375"><figcaption></figcaption></figure>

</details>

## AI Commands & Features

### CAD Functionality

<details>

<summary>CAD Status</summary>

The AI agent can update your status in the CAD to the stated, customizable status code.

_**Dispatch**, A-10, mark my status as available._\
&#xNAN;_**Dispatch**, A-10, set my status to 10-8._

</details>

<details>

<summary>CAD Lookup</summary>

The AI agent can perform a name or plate lookup, send the results to your CAD, and notify you of brief details.

_**Dispatch**, A-10, run a lookup on the plate ABC123._\
&#xNAN;_**Dispatch**, A-10, do a record check on first name John last name Doe._

</details>

<details>

<summary>CAD Dispatch Calls</summary>

#### Create Call

The AI can create a call and assign your unit. If your unit has a location, it will be automatically applied to the call unless otherwise specified. If a license plate is provided, it will automatically run a plate lookup and send the results to your CAD.

_**Dispatch**, A-10, show me out on traffic with a blue four-door sedan. License plate ABC123._

***

#### Attach to Call

The AI can attach your unit to an existing call by mentioning the call ID, location, postal, title, etc.

_**Dispatch**, A-10, attach me to the robbery in progress call._

***

#### Call Notes

The AI can add a note to your active dispatch call for other units to see.

_**Dispatch**, A-10, add a note on the call that I am arriving on-scene now, it's a white vehicle._

***

#### Detach from Call

The AI can lookup your current dispatch call and remove you from it.

_**Dispatch**, A-10, clear my call._

***

#### Close Call

The AI can lookup and close your current dispatch call.\
&#xNAN;_**Dispatch**, A-10, close my call._

</details>

<details>

<summary>CAD Unit Groups</summary>

#### Group Units

The AI can add your unit (and others) to a new or existing group.

_**Dispatch**, A-10, add me to group 'Ladder 12'._\
&#xNAN;_**Dispatch**, A-10, add myself and B-11 to group 'Ladder 12'._

***

#### Clear Unit Group

The AI can remove your unit (and others) from a group.

_**Dispatch**, A-10, clear my unit group._\
&#xNAN;_**Dispatch**, A-10, remove B-11 and I's unit group._

</details>

<details>

<summary>CAD Panic</summary>

_**Dispatch**, A-10, toggle my panic status._

The AI agent will enable or disable your panic status.

</details>

<details>

<summary>FiveM: GPS Route to Postal</summary>

The AI can draw an in-game GPS route to a postal code on the map.

#### Raw Postal:

_**Dispatch**, A-10, route me to postal 123._\
&#xNAN;_**Dispatch**, A-10, directions to postal 123._

***

#### Postal on a Dispatch Call

The AI can find an active dispatch call based on the ID, location, title, etc.\
&#xNAN;_**Dispatch**, A-10, route me to call 123._\
&#xNAN;_**Dispatch**, A-10, route me to the traffic stop call._

</details>

<details>

<summary>FiveM: GPS Route to Unit</summary>

The AI will route you to the coordinates of another active unit by providing their unit name, number, etc.

_**Dispatch**, A-10, route me unit B-11._\
&#xNAN;_**Dispatch**, A-10, directions to unit J. Doe._

</details>

### Radio Functionality

Coming soon!

## Settings

<details>

<summary>AI Volume</summary>

The AI's reply volume can be changed in the settings menu.

<figure><img src="../../.gitbook/assets/image (141).png" alt="" width="259"><figcaption></figcaption></figure>

</details>

<details>

<summary>Hear AI Replies</summary>

By default, users hear AI replies directed to anyone in their primary or scanned channel. The radio setting allows you to switch from hearing AI replies for all users to hearing only replies addressed to you.

<figure><img src="../../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure>

</details>
