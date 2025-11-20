---
description: This endpoint plays a tone (or multiple tones) in the radio.
---

# Play Tone

## Get Community Channels

<mark style="color:green;">`POST`</mark> `/api/play-tone`

This endpoint plays a tone (or multiple tones) for participants of the radio

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Request (Body)**

<pre class="language-typescript"><code class="lang-typescript">interface Request {
  /** The community ID */
  id: string<a data-footnote-ref href="#user-content-fn-1">;</a>
  /** The community API key */
  key: string;

  /** Which room (server id) to play tones for */
  roomId: number;
  /** the IDs of tones to play */
  tones: number[];
  
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
    "groups": [
        {
            "id": 0,
            "name": "Default",
            "orderIndex": 0
        },
        {
            "id": 1,
            "name": "test",
            "orderIndex": 1
        }
    ],
    "channels": [
        {
            "id": 123,
            "groupId": 0,
            "displayName": "Patrol Ops",
            "recvFreqMajor": 40,
            "recvFreqMinor": 120,
            "xmitFreqMajor": 36,
            "xmitFreqMinor": 275,
            "repeatsXmit": true,
            "status": true,
            "orderIndex": 0,
            "talkoverProtection": false
        }
    ]
}
```
{% endtab %}
{% endtabs %}

[^1]: 
