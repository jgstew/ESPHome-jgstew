# ESPHome-jgstew
example yaml files for esphome devices

## Prerequisites:
- Home Assistant
- [ESPHome Device Builder Add-On](https://my.home-assistant.io/redirect/supervisor_addon/?addon=5c53de3b_esphome&repository_url=https%3A%2F%2Fgithub.com%2Fesphome%2Fhome-assistant-addon) in Home Assistant

## Process:

Use the [ESPHome Web Interface](https://web.esphome.io/?dashboard_wizard) on a computer with the ESP connected via USB the first time to setup the device with the ESPHome Over The Air (OTA) firmware and configure WiFi.

Then go into [ESPHome Device Builder Add-On WebUI](http://homeassistant.local:8123/hassio/ingress/5c53de3b_esphome) in Home Assistant to find the device. It should be auto discovered. Then use that interface to configure the desired YAML file to the device.

## Setup Secrets:

Configure WiFi and Home Assistant API keys in the secrets YAML file.

In the [ESPHome Device Builder Add-On WebUI](http://homeassistant.local:8123/hassio/ingress/5c53de3b_esphome), click the `secrets` button in the top right.

Find the value for `api_encryption_key` in the WebUI by clicking the 3 dots under one of the devices, then click "Show API Key" button. You need at least 1 devices to show up in the ESPHome Device builder for this option to appear.

```
# Your Wi-Fi SSID and password
wifi_ssid: "your_wifi_name"
wifi_password: "your_wifi_password"

# home_assistant api key
api_encryption_key: "api_key_found_in_esphome_webui"

# ota password
ota_password: "random_password"
```

Then you can use these secrets in YAML files like this:

```
# Enable Home Assistant API
api:
  encryption:
    key: !secret api_encryption_key

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password
```

## ESPHome Integration

Once you have at least 1 device configured, the [ESPHome Integration](https://www.home-assistant.io/integrations/esphome/) should be auto discovered as needed and able to be added in Home Assistant as a discovered device.
