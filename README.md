# ESPHome-jgstew
example yaml files for esphome devices

## Prerequisites:
- Home Assistant
- [ESPHome Device Builder Add-On](https://my.home-assistant.io/redirect/supervisor_addon/?addon=5c53de3b_esphome&repository_url=https%3A%2F%2Fgithub.com%2Fesphome%2Fhome-assistant-addon) in Home Assistant

## Process:

Use the [ESPHome Web Interface](https://web.esphome.io/?dashboard_wizard) on a computer with the ESP connected via USB the first time to setup the device with the OTA firmware and configure WiFi.

Then go into [ESPHome Device Builder Add-On WebUI](http://homeassistant.local:8123/hassio/ingress/5c53de3b_esphome) in Home Assistant to find the device. It should be auto discovered. Then use that interface to configure the desired YAML file to the device.
