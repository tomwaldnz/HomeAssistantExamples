# Home Assistant Examples
This repo provides examples of automations and related resources that I use for Home Assistant. Many of these will be for the Airtouch 4. I will eventually add some AppDaemon programs that do things such as provide a guess at the outdoor status of the ducted unit based on observed temperatures (which is useful to know for some automations) and a countdown timer to turn any entity off using a slider. I'll provide a dashboard or two at some point as well.

The automations work with home assistant `2025.04.1'. I have modified the automations very slightly to add them to this git repo, there may be minor errors from the copy / paste / edit process.

I use [hass-airtouch](https://github.com/TheNoctambulist/hass-airtouch), which as of April 2025 is actively maintained. Automations for this integration are in the "hass-airtouch" folder.

The "airtouch4-deprecated" folder contains automations based on older integration I used to use. That integration is not longer maintained and doesn't work with HA 2025.

## Room / Area Controls
A useful feature I developed is what I call "Room Controls". This lets me simply enable or disable automations for a room or resource using simple toggles. Each automation checks the toggle state as a condition.

## Important Recommendation
It's strongly recommended you read all the README files in each folder that you use resources from. If you don't do that you'll probably have significant problems.

## Bugs / Help
If anyone asks for help I'll help the best I can when I have time available. Patience is likely required, it may take me a few days or a week to reply. I will reply eventually even if it's just to say "I don't know".
