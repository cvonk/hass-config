# Installation

* Install and configure [HACS](https://hacs.xyz/)

* Within HACS Frontend add the following repositories
  * [button-card](https://github.com/custom-cards/button-card)
  * [card-mod](https://github.com/thomasloven/lovelace-card-mod)
  * [layout-card](https://github.com/thomasloven/lovelace-layout-card)
  * [Swipe Card](https://github.com/bramkragten/swipe-card)

* Manually copy over these files from [cvonk/hass-config](https://github.com/cvonk/hass-config)
  * `lovelace.yaml`
  * `themes/` folder
  * `packages/` folder
  * `www/` folder
  * `automations.yaml`
  * `scripts.yaml`
  * `groups.yaml`

* In `configuration.yaml` add lines [[docs](https://www.home-assistant.io/lovelace/dashboards/)]

  ```yaml
  frontend:
    extra_module_url:
      - /hacsfiles/lovelace-card-mod/card-mod.js
    themes: !include_dir_merge_named themes
  ```

* [Restart](https://my.home-assistant.io/redirect/server_controls/) Home Assistant

* **Select dark mode and [Frosted Glass cvonk](https://my.home-assistant.io/redirect/profile/) ← DON'T SKIP THIS STEP!**

Then add your entities, [browser_mod](https://github.com/thomasloven/hass-browser_mod) for popups etc...

## For your information

* I use the following addons:

  * [Get HACS](https://www.hacs.xyz/docs/use/download/download/), to install cards/integrations from GitHub
  * [Let's Encrypt](https://community.home-assistant.io/t/how-to-configure-lets-encrypt-ssl-certificates-for-home-assistant-completely-100-free-updated-for-2022-2023/508329), to be enable to HTTPS to HA
  * [Mosquito broker](https://github.com/home-assistant/addons/tree/master/mosquitto), a MQTT broker
  * [Node-RED](https://github.com/hassio-addons/addon-node-red), for fire alarm flow
  * [Samba share](https://github.com/home-assistant/addons/tree/master/samba), SMB/CIFS access to HA folders

* These are the key integrations that I use:

  * From HA Integrations, I added:

    * [ecobee](https://www.home-assistant.io/integrations/ecobee/), thermostat
    * [Flo](https://www.home-assistant.io/integrations/flo/), water shutoff
    * [Leviton Decora Wi-Fi](https://www.home-assistant.io/integrations/decora_wifi/)
    * [Mobile App](https://www.home-assistant.io/integrations/mobile_app/)
    * [MQTT](https://www.home-assistant.io/integrations/mqtt/), for [OPNpool](https://github.com/cvonk/OPNpool)
    * [Network UPS Tools (NUT)](https://www.home-assistant.io/integrations/nut/)
    * [OPNsense](https://www.home-assistant.io/integrations/opnsense/), router
    * [Ping (ICMP)](https://www.home-assistant.io/integrations/ping/)
    * [PurpleAir](https://www.home-assistant.io/integrations/purpleair/), air quality
    * [Synology DSM](https://www.home-assistant.io/integrations/synology_dsm/)

  * From HACS, I downloaded and then added:
    * [Browser Mod](https://github.com/thomasloven/hass-browser_mod), **essential!** Used to e.g. show popup windows
    * [Arlo Camera Support](https://github.com/twrecked/hass-aarlo), security cameras
    * [Cable Modem Monitor](https://github.com/solentlabs/cable_modem_monitor)
    * [Nest Protect](https://github.com/iMicknl/ha-nest-protect), for smoke detectors
    * [Node-RED Companion](https://github.com/zachowj/hass-node-red)
    * [Noonlight Alarm](https://github.com/konnected-io/noonlight-hass), calls E911 in the USA
    * [OpenSprinkler](https://github.com/vinteo/hass-opensprinkler)
    * [Pirate Weather](https://github.com/Pirate-Weather/pirate-weather-ha)
    * [SNMP Printer](https://github.com/DSorlov/snmp_printer)


## FAQ

**Something isn't working!**</br>
1. Read the documentation for that card e.g. https://github.com/custom-cards/button-card
2. Search forum topic e.g. https://community.home-assistant.io/t/lovelace-button-card/65981
3. This is not a help center for everything Home Assistant

**Why is the text in popups inverted?**</br>
You didn't select dark mode in your [user profile](https://my.home-assistant.io/redirect/profile/)

**Why does a broken icon appear when I toggle a button?**</br>
You need to add [www/loader.svg](https://github.com/cvonk/hass-config/blob/master/www/loader.svg)

**In the update popup I get an error saying "marked"**</br>
Add [www/marked.min.js](https://github.com/cvonk/hass-config/blob/master/www/marked.min.js) and under [resources](https://github.com/cvonk/hass-config/blob/39bbedd2f9de03f8558bd909a8392ae4925f4b09/configuration.yaml#L38) add that file as a module

**How do I get the tilt effect?**</br>
Add [www/vanilla-tilt.min.js](https://github.com/cvonk/hass-config/blob/master/www/vanilla-tilt.min.js) and under [resources](https://github.com/cvonk/hass-config/blob/39bbedd2f9de03f8558bd909a8392ae4925f4b09/configuration.yaml#L39) add that file as a module

**How do I add fonts?**</br>
Copy [www/fonts.css](https://github.com/cvonk/hass-config/blob/master/www/fonts.css) and read the comment in that file and under [resources](https://github.com/cvonk/hass-config/blob/39bbedd2f9de03f8558bd909a8392ae4925f4b09/configuration.yaml#L41) add that file as css

**How do I get popups to work?**</br>
Read the the [browser_mod](https://github.com/thomasloven/hass-browser_mod) documentation
