---
description: Integrate Sonoran Radio with OpenAI.
---

# AI Keys

## Sonoran Radio AI

Sonoran Radio integrates with OpenAI to add additional features and functionality. Each feature can be easily enabled or disabled and have separate AI keys for optimal billing transparency.

## Generating an Open AI Key

### 1. Login to the Open AI Platform

Navigate to [platform.openai.com](https://platform.openai.com/) and create an account.

At the top left, select `Create Project` for a new category of Sonoran Radio API keys.

<div><figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>OpenAI: Create Project</p></figcaption></figure> <figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>OpenAI: Name Project</p></figcaption></figure></div>

### 2. Add Billing Information

OpenAI charges based on usage for each model. You will need to add payment information for AI usage.

Navigate to `Settings` > `Billing` > `Add payment details` to add a credit or debit card on file. Once added, you can manually add credits and set billing limits.

<div><figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption><p>OpenAI: Payment Details</p></figcaption></figure> <figure><img src="../../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption><p>OpenAI: Payment Limits</p></figcaption></figure></div>

### 3. Generate an API Key

With the new project selected, navigate to `API Keys` > `Create new secret key`&#x20;

Give the new API key a name (we recommend a separate key for [each AI feature](ai.md#ai-options) for optimal billing transparency) and select your Sonoran Radio project.

You can also restrict each key's model access based on the [specific feature's requirements](ai.md#ai-options).

<div><figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption><p>OpenAI: Generate Key</p></figcaption></figure> <figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="251"><figcaption><p>OpenAI: Generate Key</p></figcaption></figure></div>

### 4. Add your API Key to Sonoran Radio

In Sonoran Radio, navigate to `Customize` > `AI` > toggle on and paste in your new OpenAI API key for the specific feature.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Sonoran Radio: OpenAI API Keys</p></figcaption></figure>

## AI Options



### [Dispatch AI](dispatch-ai.md)

Dispatch AI offers in-depth integration to manage Sonoran CAD unit statuses, lookups, call creation, emergency calls, and more.

#### Model Requirements (OpenAI)

* `gpt-realtime-mini`
* `gpt-5-nano`
* `gpt-4o-mini-transcribe`
* `gpt-4o-mini-tts`

### [Transmission Log STT](../usage/dispatch-panel/transmission-logs.md) (Speech-To-Text)

Transmission logs enable dispatchers to review and replay previous transmissions. With AI integration, these logs are enhanced with text transcripts, making it easier to search, reference, and analyze past communications efficiently.

#### Model Requirements  (OpenAI):

`whisper-1`

### [Tone Board TTS](../usage/dispatch-panel/custom-tone-board.md#ai-text-to-speech) (Text-To-Speech)

Tone board text-to-speech allows the generation of spoken text tones.

#### Model Requirements  (OpenAI):

`tts-1-hd`



