---
description: This endpoint plays a tone (or multiple tones) in the radio.
---

# Play Tone

## Play Tone

<mark style="color:green;">`POST`</mark> `/api/play-tone`

This endpoint plays one or more tones for radio participants.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Request (Body)**

<pre class="language-typescript"><code class="lang-typescript">interface Tone {
  id: number;
  color: string;
  textColor: string;
  label: string;
  icon: string;
  src: string;
}

interface Request {
  /** The community ID */
  id: string<a data-footnote-ref href="#user-content-fn-1">;</a>
  /** The community API key */
  key: string;

  /** Which room (server id) to play tones for */
  roomId: number;
  /**
   * Tones to play.
   * You can provide either:
   * - a saved tone ID from the community tone list
   * - a full Tone object, including a custom src URL
   */
  tones: Array<number | Tone>;
  
  /** where to play the tones */
  playTo: {
    type: "channel" | "group" | "game";
    /**
      if type === 'channel', the channel ID
      if type === 'group', the group ID
      if type === 'game', the speaker ID (in speakers.json)
    */
    value: any;
  }[];
}

</code></pre>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "result": "ok",
  "code": 200
}
```
{% endtab %}
{% endtabs %}

You can use a full `Tone` object when you need to play a temporary or external audio file without first saving it to the community tone list. The object must include a valid `src` URL and the standard tone display fields.

Example:

```json
{
  "id": "community-id",
  "key": "community-api-key",
  "roomId": 1,
  "tones": [
    {
      "id": -1,
      "color": "#647492",
      "textColor": "text-white",
      "label": "Custom Tone",
      "icon": "fas fa-volume-high",
      "src": "https://example.com/custom-tone.mp3"
    }
  ],
  "playTo": [
    {
      "type": "channel",
      "value": 123
    }
  ]
}
```

[^1]:
