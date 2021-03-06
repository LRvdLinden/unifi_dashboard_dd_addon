<h1 align="center">Unifi Dashboard - Dwains Dashboard Add-on (more_page)</h1> 


<p align="center">
  <a href="https://dwainscheeren.github.io/dwains-lovelace-dashboard/">
    <img src="https://img.shields.io/badge/Dwains%20Dashboard-Default-299ec2.svg" />
  </a>
  <a href="https://github.com/LRvdLinden/unifi_dashboard_dd_addon">
    <img src="https://img.shields.io/github/v/release/LRvdLinden/unifi_dashboard_dd_addon" />
  </a>
      <a href="https://github.com/LRvdLinden/unifi_dashboard_dd_addon/commits">
    <img src="https://img.shields.io/github/last-commit/LRvdLinden/unifi_dashboard_dd_addon.svg?style=plasticr" />
  </a>
    <a href="https://github.com/LRvdLinden/">
    <img src="https://img.shields.io/github/followers/LRvdLinden?style=social" />
  </a>
    </a>
    <a href="https://discord.gg/7yt64uX">
    <img src="https://img.shields.io/discord/688401603811999885" />
  </a>
</p>
<p align="center">Unifi Dashboard in Home Assistant Dwains Dashboard.</p>


<p align="center">Created by <a href="https://github.com/RubenDijk/dwains-theme-addons/tree/master/more_page/ubiquiti">Ruben Dijk</a>
and little customize by <a href="https://github.com/LRvdLinden">Léon van der Linden</a>
</p> 


<p align="center">
  <img src="https://user-images.githubusercontent.com/77990847/118371039-e66e7b00-b5aa-11eb-9d60-64015622c288.png" />
</p>







## Prerequisite
---
- Install [Unifigateway](https://github.com/custom-components/sensor.unifigateway) from [HACS](https://hacs.xyz).
- Install [Multiple-entity-row](https://github.com/benct/lovelace-multiple-entity-row) from [HACS](https://hacs.xyz).
- Install [Vertical Stack In Card](https://github.com/ofekashery/vertical-stack-in-card) from [HACS](https://hacs.xyz).
- Install [Bar-card](https://github.com/custom-cards/bar-card) from [HACS](https://hacs.xyz).
- Install [Card-Mod](https://github.com/thomasloven/lovelace-card-mod) from [HACS](https://hacs.xyz).

:warning: Please reboot Home Assistant after config the sensors! :warning:



## Installation Add-on
---
- Manually install the next custom component from https://github.com/RubenDijk/homeassistant
- Copy the my_unifi to your custom component folder.
- Copy the directory `unifi_dashboard`  to your `<config dir>/dwains-dashboard/addons/more_page/` directory.
- Configure your `more_page.yaml` file in `<config dir>/dwains-dashboard/configs` with config below.
- Add unifi controller (Home-Assistant integration)
- Restart Home Assistant.
- Reload the theme configuration via Theme Settings

### Usage
To use this add-on in your Dwains Theme, add the following to your `more_page.yaml` file:

````yaml
# Example more_page.yaml entry
more_page:
    addons:
      - name: Ubiquiti UniFi
        icon: 'mdi:router-network'
        path: 'dwains-dashboard/addons/more_page/unifi_dashboard/unifi.yaml'
````

### Optional for room addon:

````yaml
addons:
  - name: Ubiquiti UniFi
    icon: mdi:router-wireless
    path: 'dwains-dashboard/addons/more_page/unifi_dashboard/unifi.yaml'
    button_path: 'dwains-dashboard/addons/rooms/hello-room/button.yaml'
    data:
      entity: sensor.unifi_gateway_alerts
````
Add the following package to your config [Ubiquiti](https://github.com/RubenDijk/dwains-theme-addons/blob/master/more_page/ubiquiti/ubiquiti.yaml/)

## Replace the following
---
Change the next line's
| Line | Fill in | directory/file |
|------|:--------------:|:------------ |
| Nr.8 | ip adres switch | sensor_ubiquiti.yaml |
| Nr.22 | ip adres switch | sensor_ubiquiti.yaml |
| Nr.27 | ip adres switch | sensor_ubiquiti.yaml |
| Nr.32 | ip adres ap | sensor_ubiquiti.yaml |
| Nr.46 | ip adres ap | sensor_ubiquiti.yaml |
| Nr.51 | ip adres ap | sensor_ubiquiti.yaml |
| Nr.138 | ip adres controller | sensor_ubiquiti.yaml |
| Nr.139 | Site-id (optional) | sensor_ubiquiti.yaml |
| Nr.140 | username | sensor_ubiquiti.yaml |
| Nr.141 | password or secret | sensor_ubiquiti.yaml |
| Nr.155 | Site-id (optional) | sensor_ubiquiti.yaml |
| Nr.156  | username | sensor_ubiquiti.yaml |
| Nr.157 | password or secret | sensor_ubiquiti.yaml |
| Nr.158 | ip adres controller | sensor_ubiquiti.yaml |
| Nr.63 | ip adres of the controller | /unifi_dashboard/unifi.yaml |
| Nr.289 | correct entity | /unifi_dashboard/unifi.yaml |
| Nr.290| correct name | /unifi_dashboard/unifi.yaml |
| Nr.311 | correct entity | /unifi_dashboard/unifi.yaml |
| Nr.312| correct name | /unifi_dashboard/unifi.yaml |

## WiFi SSID sensors
- Copy the this line and place it in your template.yaml or sensor.yaml
- Fill in your main SSID and your GUEST SSID

```yaml
  - platform: template
    sensors:
      wifi_vdlinden_count:
        friendly_name: "MAIN SSID" # <- MAIN SSID NAME
        unit_of_measurement: 'devices'
        value_template: "{{ state_attr('sensor.unifi', 'YOUR MAIN SSID') }}"
        icon_template: mdi:wifi

  - platform: template
    sensors:
      gast_vdlinden_count:
        friendly_name: "GUEST SSID NAME" # <- GUEST SSID NAME
        unit_of_measurement: 'devices'
        value_template: "{{ state_attr('sensor.unifi', 'FILL IN YOUR GUEST SSID') }}"
        icon_template: mdi:wifi
```



## Result
---


| **Light Themed** | **Dark Themed** | 
| ----------- | ----------  | 
| ![Light Themed](https://user-images.githubusercontent.com/77990847/118410366-581ff500-b68f-11eb-8505-c97708724720.png) | ![Dark Themed](https://user-images.githubusercontent.com/77990847/118410213-9ff24c80-b68e-11eb-9932-abae44e2eae0.png) | 

![simple-ipad-pro-mockup-23619](https://user-images.githubusercontent.com/77990847/118374128-bdee7d00-b5ba-11eb-80c4-e1964970735f.png)

![simple-ipad-pro-mockup-23619](https://user-images.githubusercontent.com/77990847/118371270-23873d00-b5ac-11eb-86d0-603b152b6a09.png)




---
Enjoy my card? Help me out for a couple of :beers: or a :coffee:!

[![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/LRvdLinden)








