# Home Assistant Automations
These Airtouch 4 automations are based on the custom component [hass-airtouch4-platform](https://github.com/mihailescu2m/hass-airtouch4-platform). The component is rarely updated because it works very well as it is.

Conditions such as month selectors are set up for the New Zealand / southern hemisphere conditions. We usually heat from May to November, with June to August being the coldest months, cooling is often Jan to March.

Most of these automations are relatively simple, anyone familiar with Home Assistant could likely write them, possibly better than I have. Beginners to Home Assistant may appreciate these automations to help get them started.

## Device IDs
The Airtouch device ID is a hex string that looks something like `1111aa11aa111aaa111aaa111aaa1aaa`. The simplest way I know to find your device ID is to create an automation, add a condition (device condition), then type in a few characters of your device name - it'll either be something like Airtouch or the brand of the heat pump you have. Do whatever is required to save the automation, then "view as YAML". The device ID should be in there. Delete the temporary automation.

 - `ac_daikin`: My main ducted air conditioner


## Delays
I found the automations work more reliably if there's a small delay between commands being sent to the Airtouch. It might not be necessary, but it also doesn't hurt.

## Naming
I prefix my Airtouch actions with AT. Actions for other devices are similarly prefixed.

## Airtouch Damper Control
To use these automations you must have control over damper positions. I vaugely recall that I had to change a setting but I can't find it. To see if you have damper control go to the main console and tap the set temperature of any zone, between the - and +. Alternate in the app go to the zones page and tap the set temperature, between the - and +. If you have damper control enabled it should change to a percentage or "closed".

## Airtouch Control Sensor
To reduce overheating and spill you should also go to the main console -> System Settings -> Installer (enter password - default is polyair from memory) -> AC Setup -> Next -> Detail Setting. In there set "Control Sensor" to "Economy". Read the docs in there, but in short it tells AT4 to obey its sensors. From memory the default setting has the outdoor unit only turning off based on the temperature at the return vent.

## Spill Zone
In winter our spill zone is our lounge. In summer when we're cooling the spill zone is our small bedroom as it's on the warm side of the house. Some seasons we change the spill zone daily depending on whether we're heating or cooling.

## Email notifications
If you want email notifications, which some of my automations use, set this up in your configuration.yaml

The "name" field can be anything you like. If you call it email_service_name The action will use `notify.email_service_name` to send a notification.

```
notify:
  - name: email_service_name
    platform: smtp
    server: smtp.emailserver.com
    port: 587
    timeout: 15
    sender: your@email.com
    encryption: starttls
    username: your@email.com
    password: smtp-password-here
    recipient:
      - your@email.com
    sender_name: <Yourname> Home Assistant
```
