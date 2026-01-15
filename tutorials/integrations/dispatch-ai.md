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

## Usage

### Selecting Your Wake Word

When pressing your push-to-talk key, a local AI listens to your microphone feed for the customizable wake word. By default, this is **Dispatch**.

Communities can also [customize the default wake word for all users](../usage/dispatch-panel/default-user-settings.md).

<figure><img src="../../.gitbook/assets/image (140).png" alt="" width="287"><figcaption></figcaption></figure>

### Manual AI Toggle

FiveM users can also set a manual keybind in the settings. Pressing this keybind will enable the AI (same as the wake word) for your transmission.

<figure><img src="../../.gitbook/assets/image.png" alt="" width="375"><figcaption></figcaption></figure>

### Prompting the AI

In order to reduce false triggers and conserve local resources, the AI will only listen to the first five seconds of your transmission. This amount can be modified in the **Advanced** tab of the **Audio** settings.

**Example**

If your wake word is **Dispatch**, then your transmissions to the AI would be as follows:

\<wake word>, \<optional: my unit number>, \<action to do>\
&#xNAN;_**Dispatch**, A-10, mark me as available._\
&#xNAN;_**Dispatch**, A-10, run a lookup on the license plate ABC123_

## AI Commands & Features

### CAD Functionality

<details>

<summary>CAD Status</summary>

_**Dispatch**, A-10, mark my status as available._\
&#xNAN;_**Dispatch**, A-10, set my status to 10-8._

The AI agent will update your status in the CAD to the stated, customizable status code.

</details>

<details>

<summary>CAD Lookup</summary>

_**Dispatch**, A-10, run a lookup on the plate ABC123._\
&#xNAN;_**Dispatch**, A-10, do a record check on first name John last name Doe._

The AI agent will perform the lookup, send the results to your CAD, and notify you of brief details.

</details>

<details>

<summary>CAD Dispatch Calls</summary>

_**Dispatch**, A-10, attach me to the robbery in progress call._\
&#xNAN;_**Dispatch**, A-10, clear my call._\
&#xNAN;_**Dispatch**, A-10, close my call._\
&#xNAN;_**Dispatch**, A-10, add a note on the call that I am arriving on-scene now, it's a white vehicle._

The AI agent till attach, detach, clear, close, or add notes to the dispatch call.

</details>

<details>

<summary>CAD Panic</summary>

_**Dispatch**, A-10, toggle my panic status._

The AI agent will enable or disable your panic status.

</details>

### Radio Functionality

Coming soon!
