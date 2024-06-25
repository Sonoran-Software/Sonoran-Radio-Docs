---
description: Learn more about custom integrations with the in-game resource!
---

# Resource Events

## Push-to-talk

When a user presses or releases their PTT key, the following event can be used:

```lua
-- Event sent from Sonoran Radio
TriggerEvent('SonoranRadio::API:ToggleTalking', toggle, inVeh)

-- Event listener in a custom script
RegisterNetEvent('SonoranRadio::API:ToggleTalking', function(toggle, inVeh) 
  print(toggle) -- Boolean (Are the talking?)
  print(inVeh) -- Boolean (Are they in a vehicle)
end)
```
