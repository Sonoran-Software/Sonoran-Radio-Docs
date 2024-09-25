---
description: >-
  Configure tunnels, underpasses, and other areas where radio signal will be
  degraded!
---

# Tunnels and Degrade Zones

This feature is coming soon!

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

## What are Degrade Zones?

Degradation zones are areas like tunnels, underground areas, or mountain valleys that would experience signal loss in a realistic scenario.

### Creating and Modifying Zones

#### Open the menu with the in-game `/radiomenu` command and navigate to the "Toneboard Speaker Menu"

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### Select "Create Degradation Zone" and begin your creation

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<details>

<summary>Button Explanations:</summary>

* Strength - The percent the signal strength will be cut by when inside the zone.
  * Example: 0.5 = 50% degradation&#x20;
* Add Point to Zone - Adds another point to the zone
* Undo Last Point - Removes the last place point in the zone
* Min Z - The minimum Z value at which you will be considered in the zone
  * Explanation: Z in a vector3 is the height value
* Max Z - The maximum Z value at which you will be considered in the zone
* Finish Zone Creation - Finishes the creation and saves to the `tunnels.json` file
* Cancel Zone Creation - Also works by closing the menu

</details>

#### When creating a zone you can visualize via the drawn polygon and manipulate and move your last placed point using the on-screen controls

<figure><img src="../../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>
