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

### Copy Sonoran CAD API Information

Dispatch AI requires a Sonoran CAD community ID, API key, and server ID.

The community ID and API key are located in the **Admin** panel > **Advanced** > **In-Game Integration** > **Web API**.

The server ID can be found in the **Admin** panel > **Customization** > **Servers**. The default server ID is `1`.

<div><figure><img src="../../.gitbook/assets/image (134).png" alt="" width="375"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (135).png" alt="" width="375"><figcaption></figcaption></figure></div>

### Link CAD In Radio

In the radio **Customization** panel > **Info** > Select a server (or create one) and click on the Sonoran CAD icon. This will open a popup modal to enter in your CAD's community ID, API key, and server ID.

<div><figure><img src="../../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure></div>

## Usage

### Selecting Your Wake Word

When pressing your push-to-talk key, a local AI listens to your microphone feed for the selected wake word. Once the wake word is heard, it sends all microphone traffic to the external AI for processing.

Customizing your wake word is available in the radio settings. Communities can even [create their own, custom wake words](dispatch-ai.md#creating-custom-wake-words).

<figure><img src="../../.gitbook/assets/image (133).png" alt="" width="284"><figcaption></figcaption></figure>

### Prompting the AI

All push-to-talk transmissions must start with the wake word in the first three seconds, or it will be considered a transmission to another unit.

**Example**

If your wake word is `Dispatch`, then your transmissions to the AI would be as follows:

\<wake word>, \<optional: my unit number>, \<action to do>\
&#xNAN;_**Dispatch**, A-10, mark me as available._\
&#xNAN;_**Dispatch**, A-10, run a lookup on the license plate ABC123_

## AI Commands & Features

### CAD Functionality

<details>

<summary>CAD Status</summary>

_**Dispatch**, A-10, mark me as available._\
&#xNAN;_**Dispatch**, A-10, show me 10-8._

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

## Creating Custom Wake Words

Your wake word is the phrase that tells the AI you’re addressing it, not another radio user, similar to “Hey Siri,” “Okay Google,” or “Alexa.”

Sonoran Radio includes several built-in wake word options, and you can also train a custom wake word tailored to your community. Training is straightforward, though processing can take up to an hour.

### 1. Build the Model

#### 1A. Wake Word Pronunciation

Open the [Google Colab training environment](https://colab.research.google.com/drive/1q1oe2zOyZp7UsB3jJiQ1IFn8z5YfjwEb?usp=sharing#scrollTo=-Q9wEuRdwY_E). In the first section, enter your custom **target\_word**, then click the **Play** button. The first run may take 30–60 seconds (or longer) to prepare the audio.

The webpage will play your custom wake word using its current pronunciation. Make sure the audio matches exactly how you intend to say the wake word. If it sounds incorrect, adjust the spelling to improve pronunciation.

**Example:**\
Sonoran → _suh\_nar\_rohn_

<figure><img src="../../.gitbook/assets/image (2).png" alt="" width="375"><figcaption></figcaption></figure>

#### 1B. Running the Model Training

Once you’re satisfied with the wake word’s pronunciation, select **Run All** at the top of the page or go to **Runtime → Run All**.

Training may take an **hour or longer to complete**. When finished, two files will automatically download to your computer.

<figure><img src="../../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure>

### 2. Upload the Model

Now that your model files are ready, it's time to upload them to Sonoran Radio.

{% hint style="warning" %}
This feature is coming soon!
{% endhint %}

### 3. Select the Model

Users in the community can now [select the custom wake word in their settings](dispatch-ai.md#selecting-your-wake-word). Additionally, you can [configure the default wake word for new users in your community](../usage/dispatch-panel/default-user-settings.md).
