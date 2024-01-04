---
description: Change the look of your in-game radio with custom frames!
---

# Customizing Radio Frames

{% hint style="info" %}
Please be aware that this guide is a work in progress and is actively being written. As such, it may not cover all aspects of customizing radio frames.
{% endhint %}

## Frame Permissions

You can restrict radio frames so that you can specify which frames any given department, job, or job grade can use, as well as configure ace permissions for admin commands. This can integrade with ESX or QBCore, or can be used standalone.

Here's an example configuration, specifying that a member of the `sahp` department, with the `police` job and a grade of `1`, `2` or `3` is allowed to use the frames `default`, `signalpro`, or `voxguard` only:

<pre class="language-lua"><code class="lang-lua"><strong>Config.frames = {
</strong>	permissionMode = 'ace', -- ace, qbcore, esx or none
	adminPermission = 'sonoranradio.admin', -- ACE permission required to use admin commands
	departments = {
		['sahp'] = {
			label = 'San Andreas Highway Patrol',
			permissions = {
				jobs = { -- Jobs that can use this department
					['police'] = {
						grades = { -- Job grades that can use this department
							1,
							2,
							3
						}
					}
				},
				ace = { -- ACE Permissions that can use this department | ONLY EFFECTIVE IN ACE PERMISSION MODE
					'sonoranradio.sahp'
				}
			},
			-- Radio frames that can be used by this department
			allowedFrames = {
				'default',
				'signalpro',
				'voxguard'
			}
		}
	}
}
</code></pre>

## Customizing Radio Frames

To begin customizing your radio frames, you will first want to navigate to the skins folder at `sonoranradio\skins`. In here are subfolders for every different frame that's been added to the radio.

In each skin folder, there are generally going to be two or three images as well as a `skin.json` file. The images will show the different frames used with that one skin. Generally, there will be a handheld (portable) radio image, a mobile (vehicle) radio image, and sometimes a top-down (HUD) radio image.&#x20;

In skins.json, you can specify the images for each type of radio, as well as where the button positions correlate to on the radio image.

It is recommended that you cope-paste a `skin.json` file from an existing skin, and change the values as needed to ensure formatting stays the same.

At the top of your `skin.json` file, you can specify the name of the radio next to `name`. Below that, you can set up the fames. For each frame, you must specify `type` and configure the `body` settings.

### Frame Types

The following are valid as values for `type`:

* `portable` - Used for handheld radios
* `vehicle` - Used for mobile radios installed in a vehicle
* `hud` - Top-down view of a portable radio

### Body Settings

In `body` you can specify the `image`, or the file name for the image assocated with the specified `type`. For example, the image for your `portable` radio might be `radio-portable.png`, which is what you'd enter as the image type.

You can also input a value for `width`, or the width of the image as it displays in-game.

### Controls

For every frame, you can assign different actions button to different positions on the image. For example, if your radio frame has a panic button, you can add a panic button hitbox that roughly matches up with the size and position of the panic button on your radio image. Thus, when the users clicks on that part of the image in-game, it will trigger panic as if the user had actually pressed a button.

{% hint style="info" %}
**PROTIP:** Enable debug mode in the main config (change Config.debug to `true`) to show where the buttons are on screen. This makes it significantly easier to configure the position and size.
{% endhint %}

The available action types are as follows:

* `power`
* `next_preset`
* `prev_preset`
* `panic`
* `home`
* `hide`

### Screen and Mini-Screen

You can also specify the position and width of the screen on your radio frame, so that Sonoran Radio can display its own information as if its a part of that radio. To do this, you must modify the values under `screen` (or `miniScreen` for `hud`-type radio frames).

With `hud`-type radio frames, `controls` can also be left blank.

## Example File

Below is an example of a `skin.json` file:

```json
{
  "name": "Moto AX",
  "frames": [
    {
      "type": "portable",
      "body": { "image": "radio-portable.png", "width": 17 },
      "controls": [
        {
          "action": "power",
          "bottom": 29.6,
          "right": 0.8,
          "width": 2.7,
          "height": 2.7
        },
        {
          "action": "next_preset",
          "bottom": 30,
          "right": 7.25,
          "width": 1.25,
          "height": 4.25
        },
        {
          "action": "prev_preset",
          "bottom": 30,
          "left": 7.125,
          "width": 1.25,
          "height": 4.25
        },
        {
          "action": "panic",
          "bottom": 29.75,
          "left": 4,
          "width": 2,
          "height": 1.25
        },
        {
          "action": "home",
          "bottom": 3.25,
          "left": 6.75,
          "right": 6.75,
          "height": 1.5
        }
      ],
      "screen": {
        "bottom": 5.875,
        "height": 18.125,
        "left": 3.2185,
        "right": 3.2,
        "zIndex": 5
      }
    },
    {
      "type": "vehicle",
      "body": { "image": "radio-mobile.png", "width": 45.125 },
      "controls": [
        {
          "action": "power",
          "top": 2.25,
          "left": 6.15,
          "width": 2,
          "height": 2
        },
        {
          "action": "prev_preset",
          "top": 2.25,
          "right": 17.25,
          "width": 1.5,
          "height": 2
        },
        {
          "action": "next_preset",
          "top": 5,
          "right": 17.25,
          "width": 1.5,
          "height": 2
        },
        {
          "action": "hide",
          "top": 8.25,
          "right": 17.25,
          "width": 1.5,
          "height": 1.5
        },
        {
          "action": "home",
          "top": 11.25,
          "right": 17.25,
          "width": 1.5,
          "height": 1.5
        },
        {
          "action": "panic",
          "top": 2.25,
          "right": 3.75,
          "width": 2,
          "height": 2
        }
      ],
      "screen": {
        "top": 2.65,
        "height": 10.2,
        "left": 11,
        "width": 13.45,
        "zIndex": 5
      }
    },
    {
      "type": "hud",
      "body": { "image": "radio-portable-top.png", "width": 22.25 },
      "controls": [],
      "miniScreen": {
        "bottom": 7.2,
        "height": 3.75,
        "left": 7.75,
        "right": 7.5
      }
    }
  ]
}
```
