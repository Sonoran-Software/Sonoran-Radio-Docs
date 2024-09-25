---
description: >-
  Configure tunnels, underpasses, and other areas where radio signal will be
  degraded!
---

# Tunnels and Degrade Zones

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption><p>Sonoran Radio - Tunnel Detection System</p></figcaption></figure>

## What are Degrade Zones?

Degradation zones are areas like tunnels, underground areas, or mountain valleys that would experience signal loss in a realistic scenario. [Custom voice effects](../dispatch-panel/custom-voice-effects.md) will distort the audio more as signal loss increases.

## Creating and Modifying Zones

### Accessing the Menu

Open the menu with the in-game `/radiomenu` command and select `Degradation Zones`

<figure><img src="../../../.gitbook/assets/image (2).png" alt="" width="222"><figcaption><p>Sonoran Radio - </p></figcaption></figure>

### Zone Configuration Options

In the `Degradation Zones` menu, you can specify the strength and add points to create a 3D zone.

When creating a zone you can visualize via the drawn polygon and manipulate and move your last placed point using the on-screen controls

<div>

<figure><img src="../../../.gitbook/assets/image (3).png" alt="" width="221"><figcaption><p>Sonoran Radio - Degradation Zone Options</p></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/image (74).png" alt="" width="375"><figcaption><p>Sonoran Radio - Degradation Zone Poly</p></figcaption></figure>

</div>

<details>

<summary>Configuration Option</summary>

`Strength` \
\- The percent the signal strength will be cut by when inside the zone (0-1).\
\- Example: 0.5 = 50% [voice effect](../dispatch-panel/custom-voice-effects.md) degradation&#x20;

`Add Point to Zone`\
\- Adds another point to the 3D zone

`Undo Last Point`\
\- Removes the last place point in the 3D zone

`Min Z`\
\- The minimum Z value (floor height) of the 3D zone

`Max Z`\
\- The maximum Z value (ceiling height) of the 3D zone

`Finish Zone Creation`\
\- Finishes the 3D zone and saves to the `tunnels.json` file

`Cancel Zone Creation`\
\- Cancels the 3D zone editor and closes the menu

</details>
