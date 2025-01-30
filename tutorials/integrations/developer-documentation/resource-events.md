---
description: Learn more about custom integrations with the in-game resource!
---

# Resource API

## Push-to-talk

When a user presses or releases their PTT key, the following event can be used:

```lua
-- Event sent from Sonoran Radio
TriggerEvent('SonoranRadio::API:ToggleTalking', toggle, inVeh)

-- Event listener in a custom script
AddEventHandler('SonoranRadio::API:ToggleTalking', function(toggle, inVeh) 
  print(toggle) -- Boolean (Are the talking?)
  print(inVeh) -- Boolean (Are they in a vehicle)
end)
```

## Emergency (911) Calls

You can start, end, and toggle an emergency call with a client resource export:

```lua
-- In your custom script
-- true     = Start
-- false    = End
-- 'toggle' = Toggle
exports['sonoranradio']:setEmergencyCall('toggle')
exports['sonoranradio']:setEmergencyCall('toggle', 'My Custom Name')
```

The following client events reflect the emergency call status:

```lua
-- Event sent from Sonoran Radio
TriggerEvent('SonoranRadio::API:EmergencyCall', enabled)

-- Event listener in a custom script
AddEventHandler('SonoranRadio::API:EmergencyCall', function(enabled)
    print(enabled) -- Boolean (is the call starting (true) or ending (false))
end)
```

```lua
-- Event sent from Sonoran Radio
TriggerEvent('SonoranRadio::API:EmergencyCallDispatcher', available)

-- Event listener in a custom script
AddEventHandler('SonoranRadio::API:EmergencyCallDispatcher', function(available)
    print(available) -- Boolean (is a dispatcher attached to the call)
    -- NOTE: does not receive `false` if emergency call is ended
    -- (above event will receive that)
end)
```

## Signal Quality

You can get the current signal quality with an export

```lua
-- In your custom script
exports['sonoranradio']:getSignalQuality() -- number from 0.0 to 1.0
```

## Panic Button

You can listen to or active the panic button with an API event

```lua
-- Activate the panic button
TriggerEvent('SonoranRadio::API:PanicButton')

-- Listen to the panic button
AddEventHandler('SonoranRadio::API:PanicButton', function(status)
    print(status) -- Boolean (whether the panic button is active or not)
    -- your code here
end)
```
