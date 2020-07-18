v1.3:
- graceful shutdown
- availability reporting

v1.2:
- improved topic naming scheme
- Holiday Mode Shift temperature values fixed

v1.1.6: bugfix

v1.1.5: bugfix

v1.1.4: HA discovery - sensors added
- using values from .../log/... topics
- note: multi-select and value settings do not have HA discovery

v1.1.3 Initial support for Home Assistant MQTT discovery
- configuration topics are posted on start up, for 2-state switches only
- topic: homeassistant/switch/...

v1.1.2: Initial version
- feeds data to MQTT
- able to change settings of the heat pump
Note: this is still work in progress, some noticable missing functionality:
- does not advertise as a HVAC device to Home Assistant
- no error handling on changin settings
- may not recover from network outage
