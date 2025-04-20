# Home Assistant Automations
These Airtouch 4 automations are based on the custom component [hass-airtouch](https://github.com/TheNoctambulist/hass-airtouch). As of April 2025 this component is actively maintained, but it's mature and doesn't typically need regular updates.

Conditions such as month selectors are set up for the New Zealand / southern hemisphere conditions. We usually heat from May to November, with June to August being the coldest months, cooling is often Jan to March.

Most of these automations are relatively simple, anyone familiar with Home Assistant could likely write them, possibly better than I have. Beginners to Home Assistant may appreciate these automations to help get them started.


## Adding these automations to your HA
From the dashboard select automations -> new automation. Click the three dots at the top right of the screen and choose "Edit in YAML". Paste the automation in. You can then switch back to the visual editor. Once you get used to HA the YAML tends to be simpler to understand, but I often use the visual editor to set up the structure of an automation and find devices / entities.


## Naming
I prefix my Airtouch actions with AT or ATP. Actions for other devices are similarly prefixed. This isn't as necessary since categories have been added to Home Assistant but it does make searching for automations simpler when you have many devices controlled.

## Airtouch Damper Control
To use these automations you must have control over damper positions. On the Airtouch 4 this is done by going to the Airtouch tablet and navigating to System Settings -> Installer (enter password - default is polyair from memory or 8 spaces sometimes works) and uncheck "Groups lock to temp control"

## Airtouch Control Sensor
To reduce overheating and spill you you should put your Airtouch into "economy mode". On the Airtouch 4 this is found by going to the Airtouch tablet and navigating to System Settings -> Installer (enter password - default is polyair from memory or 8 spaces sometimes works) -> AC Setup -> Next -> Detail Setting. In there set "Control Sensor" to "Economy". Read the docs in there, but in short it tells AT4 to obey its sensors. From memory the default setting has the outdoor unit only turning off based on the temperature at the return vent.

## Spill Zone
In winter our spill zone is our lounge. In summer when we're cooling the spill zone is our small bedroom as it's on the warm side of the house. Some seasons we change the spill zone daily depending on whether we're heating or cooling. Having a bypass damper would eliminate this problem, but it would be very helpful if the spill zone could be changed from the Airtouch API.

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
