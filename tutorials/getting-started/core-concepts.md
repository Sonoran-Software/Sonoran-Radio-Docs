---
description: How radios work can be intimidating. Look here for what means what.
---

# Core Concepts

## Core Concepts <a href="#core-concepts" id="core-concepts"></a>

Radios are complicated. For emergency systems, it has always been a design need to hide many of these complicated features away from the people using the radios to streamline them. However, it's not possible to hide everything, or else it would take the functionality of the radio with it.

This page helps explain many of these visible features in a way that anyone could understand.

## XMIT & RECV Frequencies <a href="#xmit-recv-frequencies" id="xmit-recv-frequencies"></a>

**Your XMIT Frequency** is the frequency that you are transmitting to.\
**Your RECV Frequency** is the opposite, the one you're receiving transmissions from.

Why the need for two separate frequencies? This wouldn't be the case if radios had unlimited range, however, they don't, their range is actually fairly small. As a solution to this, telecommunications companies set up towers that will take transmissions from one frequency, then repeat those exact transmissions to another frequency but with much higher power. Radios can then receive transmissions from much further on that new frequency. This system is also known as Simulcast.

For Sonoran Radio, a server owner can change the properties of a set of frequencies to simulate this behavior, essentially making the XMIT/RECV frequency pair audible from anywhere. If this weren't the case, you could only hear units within a certain range.

#### Example Diagram <a href="#example-diagram" id="example-diagram"></a>

![Example Diagram](../../.gitbook/assets/Radio\_Diagram.png)

### Simplex and Duplex <a href="#simplex-and-duplex" id="simplex-and-duplex"></a>

In the world of radio communications the terms `Simplex` and `Duplex` are used in two different ways. One to describe the type of "channel" you are using and another to describe the capabilities of the radio hardware.

#### Channels <a href="#channels" id="channels"></a>

As mentioned above channels are composed of a `XMIT` frequency and a `RECV` frequency.

In **Simplex** channels the `XMIT` and `RECV` are the same frequency.

In **Duplex** channels the `XMIT` and `RECV` are different frequencies and typically require a repeater as a middle man to have the signal reach further.

Duplex channels are sometimes described as **Half-Duplex** and **Full-Duplex**. The term half-duplex refers to systems where use of a push-to-talk switch is required to communicate. Full-duplex refers to systems like mobile telephones with a capability to simultaneously receive and transmit. Repeaters are by nature full-duplex, most mobiles and almost all handhelds are half-duplex.

![Simplex and Duplex](../../.gitbook/assets/Radio\_simplex-duplex.jpg)

#### Hardware <a href="#hardware" id="hardware"></a>

**Simplex** hardware is really only used by radio broadcast stations because they do not need to communicate to anyone in two directions, they send out a message to listeners and listeners cannot communicate back.

**Half-Duplex** hardware is most 2-Way Radio hardware, when transmitting the radio cannot receive others transmitting a message. Depending on the system, there might be **Talkover Protection** to keep messages clear from transmitting over each other, or when two radios transmit the receivers in range may get a garbagled sound.

**Full-Duplex** hardware is typically only repeaters in business and emergency services implementations. Full-duplex hardware can transmit and receive at the same time, by nature, this is exactly what a repeater needs to do in order to give real-time communication between radios.

### Scanned Frequencies <a href="#scanned-frequencies" id="scanned-frequencies"></a>

Scanning a frequency means to hear the transmissions over that frequency, even while your main **RECV** frequency is not set to that frequency.

This, however, doesn't mean that the transmissions with each frequency you're listening to will overlap. If you're listening to a transmission on a scanned frequency, then someone starts transmitting in your **RECV** frequency, then the scanned frequency's transmission will be cut off (i.e. priority is given to your MAIN frequency).

Scanning a set of frequencies can help dispatchers and units know what's going on in other channels/frequencies without having to constantly switch.

### ↕️ LOW/HIGH Frequency Bands <a href="#lowhigh-frequency-bands" id="lowhigh-frequency-bands"></a>

**LOW BAND:** 30.000MHz - 50.999MHz\
**HIGH BAND:** 150.000MHz - 174.999MHz

In the United States, the Federal Communications Commission (FCC) designates certain frequency bands to certain uses. There are two separate designations for public service radio: the VHF Low Band and the VHF High Band.

Realistically, the transmissions sent over the VHF High Band can penetrate walls and building much better but have a shorter range, and vice versa for the VHF Low Band. However, this functionality is not simulated in Sonoran Radio.

![Frequency Spectrum](../../.gitbook/assets/Radio\_Spectrum-View.png)
