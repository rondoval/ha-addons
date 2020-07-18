This is Panasonic Aquarea Service Cloud to MQTT gateway.
It queries the Service Cloud web interface and feeds all data to MQTT into following topics:
- aquarea/{deviceID}/log/* - all statistics from Statistics page
- aquarea/{deviceID}/state/* - current device status
- aquarea/{deviceID}/settings* - User settings page (note: Service settings are not available)
- aquarea/state - Service status; "online" if conneted to Service Cloud
- homeassistant/+/{deviceID}/* - Home Assistant MQTT configuration topics for sensors, binary sensors and switches

In order to change settings send message to aquarea/{deviceID}/settings/+/set with one of the values specified in aquarea/{deviceID}/settings/+/options
Example:
  aquarea/B25xxxxxx/settings/Operation/set "Power: Off"
will power off the device.

Requirements:
- Aquarea Service Cloud account, with the heat pump registered
- MQTT broker
