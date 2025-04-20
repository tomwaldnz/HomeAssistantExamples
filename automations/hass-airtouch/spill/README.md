# HVAC State Outdoor Unit Monitoring
The automations that work with spill refer to `sensor.daikin_ducted_hvac_state`. This sensor is a custom sensor I have created that contains the state of the outdoor unit. I've found this very useful to prevent the automation triggering constantly, if you don't have anything like this you may need to tweak things a bit to work better.

## Current Based Monitoring
I have a [Shelly EM Pro](https://www.smarthome.com.au/product/shelly-em-pro-wi-fi-energy-meter/) device in my switchboard that monitors the current of a number of circuits, including my ducted heat pump. Based on this I have an automation that sets a sensor so other automations can use the outdoor unit state.

## AppDaemon Based Monitoring
Previous to installing the Shelly device I had an AppDaemon app I wrote which guessed at the outdoor unit state based on the heat pump mode and whether the temperature was changing. It was reasonable effective. I will put this onto GitHub at some point.
