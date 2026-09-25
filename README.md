# EastMesh EU Observer

Fork of [EastMesh Observer](https://github.com/xJARiD/MeshCore-EastMesh) with EU/Romania support for [MeshCore](https://meshcore.co.uk) networks.

## What's different from the original

- **CoreScope RO preset** -- one-click connection to the Romanian MeshCore network (mqtt.meshcore.com.ro:8883) with automatic TLS
- **MQTT TLS auto-detection** -- TCP connections on port 8883 automatically use SSL/TLS
- **EU/Romania IATA regions** -- dropdown with AR, BEG, BV, CS, CV, GR, IS, MD, OTP, PDV, PH, RES, SOF, TM, TSR
- **Topic uses node name** -- publishes to meshcore/{IATA}/{NODE_NAME}/packets, compatible with CoreScope RO
- **Client version** -- identifies as eastmesh-eu-observer

## Supported boards

| Board | Firmware |
|-------|----------|
| Heltec WiFi LoRa 32 V3 | Heltec_v3_observer.bin / Heltec_v3_observer_merged.bin |
| Heltec WiFi LoRa 32 V4 | Heltec_v4_observer.bin / Heltec_v4_observer_merged.bin |

Use non-merged to update without erasing settings.
Use merged for a clean install on a new board.

## Flashing

1. Go to https://observer.gessaman.com
2. Connect your board via USB
3. Click Custom Firmware
4. Select the correct .bin file from the Releases page for your board (V3 or V4)
5. Click Flash

## Initial setup via serial console

After flashing, open the Console tab on https://observer.gessaman.com and run:

set wifi.ssid YourWiFiName
set wifi.pwd YourWiFiPassword
password YourAdminPassword

Reset the board after (physical button or disconnect USB).

## Web panel configuration

Open https://YOUR_OBSERVER_IP in your browser and accept the self-signed certificate warning. Log in with the admin password you set above.

1. Node Name -- choose any name for your observer
2. Location -- set latitude and longitude
3. MQTT IATA -- select your region from the dropdown
4. Primary MQTT -- MeshMapper
5. Secondary MQTT -- CoreScope RO
6. Enter Username and Password provided by the CoreScope RO administrator
7. Enable Ghost Node Mode -- pure listener, no repeat, no adverts

## Verifying it works

- https://map.meshcore.com.ro -- Observers -- your node should appear as Online
- https://meshmapper.net -- your node should also appear there

## Romanian MeshCore network

- Frequency: 869.6179809 MHz, BW62.5, SF8, CR8
- For CoreScope RO credentials contact the administrator at https://map.meshcore.com.ro

## Credits

- Original EastMesh firmware: https://github.com/xJARiD/MeshCore-EastMesh
- MeshCore: https://meshcore.co.uk
- Romanian CoreScope: https://map.meshcore.com.ro
