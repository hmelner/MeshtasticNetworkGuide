# Step by Step Guide

## **Step 1: Choose a Device**
*Can be installed on a range of development boards*
Community Favorites:
* RAK Meshtastic Start Kit <ul>
- Wisblock Starter Kit <ul>
* Customizable, Beginner friendly, nRF52840 chip, Bluetooth, no soldering
* No built-in GPS, No Screen </ul></ul>
* HELTEC LoRa V3<ul>
- Better handheld, More customization available, built-in OLED displays, ESP32, Ready-to-go, Wifi
- No GPS, Not easy to customize</ul>
* LILYGO LoRa T3-S3<ul>
- T-Echo<ul>
* Backlit E-Ink screen, 5.0 Bluetooth, GPS, SX1262 chip, 850 mSh battery, no soldering, nRF52840, Ready-to-use product
* No Wifi, not easy to customize</ul>
- T-Beam<ul>
* ESP32 microcontroller, LoRa radio module, OLED Display, GPS, Ready-to-go, GPS, Wifi
* Not easy to customize</ul></ul>
* Nano G2 Ultra<ul>
- Portable, durable, uses low power MCU NRF52840, battery life ~5 days</ul>
* Station G2<ul>
- Designed to be a base station or in a vehicle (not very portable)</ul><br>

Note:<br>

Recommend devices with newer “Semtech SX126x or LR11xx series”
- Increased receive and transmit performance<br>
Recommend using “nRF52-based devices” – preferred for solar and handset

**Best for Beginners: RAK Meshtastic Starter Kit or LILYGO T-Echo**
* Look for these features: <ul>
* SX126x or LR11xx chip (better performance)
* nRF52-based devices (great for solar/handheld) </ul>


## Step 2: Flash and Configure Device
*Initial Configuration*
1) **Identify your Region** - Based on the country you are in, determine the appropriate region code from the list (found on the Meshtastic website)
2) **Set the Region** - Depending on your device (Apple, Android, CLI, Web) follow the steps to set the correct frequency range
3) **Understand Limitations** - Some regions, like EU_433 and EU_868, restrict how often transmissions can occur.

*Configuration*
1) **Radio Configuration** - Manages device operations and connectivity:<ul>
  a. Bluetooth: Enable, Pairing Mode, Fixed PIN Channels: Index, Role, Settings <br>
  b. Device: Role, Serial Output, Debug Log, Factory Reset <br>
  c. Display: Screen Duration, Auto Carousel, GPS Format <br>
  d. LoRa: Region, Modem, Max Hops, Transmit Power, etc. <br>
  e. Network: WiFi & NTP settings <br>
  f. Position: GPS settings & Smart Broadcast <br>
  h. Power: Charge Current, Power Saving, Sleep Intervals <br>
  i. Security: Keys, Admin Access, Debug Logs <br>
  j. User: Long Name, Short Name, Licensing <br></ul>
2) **Module Configuration** - Enhances device functionality:<ul>
a. Ambient Lighting<br>
b. Audio<br>
c. Canned Messages<br>
d. External Alerts<br>
e. Detection Sensor<br>
f. MQTT<br>
g. Neighbor Info<br>
h. Paxcounter<br>
i. Range Test<br>
j. Remote Hardware<br>
k. Serial<br>
l. Store & Forward<br>
m. Telemetry<br>
n. Traceroute <br></ul>
3) **Remote Admin** - Securely manage nodes over the mesh:<br>
Remote Administration is a powerful, advanced feature best suited for experienced users. If misconfigured, it can cause a remote node to disconnect from the mesh entirely. <ul>
a. Security & Access Control<br><ul>
i. Firmware 2.5+: Use Public Key (PKC method)<br>
ii. Older Firmware: Use Admin Channel (Legacy method)<br></ul>
b. Setup<br><ul>
i. PKC Method: Copy the local node’s public key to the remote node’s Admin Keys (up to 3 keys).<br>
ii. Legacy Method: Create an admin channel with a shared PSK and enable Legacy Admin in Security Config.<br></ul>
c. Usage<br><ul>
i. Connect to a local node via the Meshtastic App.<br>
ii. Go to Settings > Configure Node, and select the remote node.<br>
iii. Adjust settings and switch back to your node when done.<br></ul></ul>

**Step 3: Connect to your Device**

**Prerequisites:**

- **Advanced Feature:** Intended for experienced users; incorrect settings can disconnect a node from the mesh. Test changes on a separate node first.
- **Function:** Allows secure remote administration of Meshtastic nodes over the mesh network.
- **Default Security:** Nodes only accept admin commands via USB, Bluetooth, or TCP unless configured for remote administration.
- **Firmware 2.5+:** Requires storing the local node’s public key in the remote node’s Admin Key fields (supports up to three keys).
- **Firmware 2.4. x and Earlier:** Uses an admin channel with a shared PSK to allow remote management.
- **Legacy Support:** The admin channel method can still be used in firmware 2.5+, but only for pre-2.5 nodes and must be enabled manually.
- **Managed Mode:** Optional setting that restricts radio configurations but is not required for remote administration.

**Platforms:**

1. **iOS App**
    1. **Using the PKC Method (Firmware 2.5+)**
        1. Connect to the local node (admin node).
        2. Enable Administration in Settings > App Settings.
        3. Find and copy the public key under Settings > Radio Configuration > Security.
        4. Connect to the remote node.
        5. Add the copied public key as an Admin Key under Security (up to 3 keys can be added).
    2. **Using the Legacy Method (Firmware 2.4.x and earlier)**
        1. Create an Admin channel by setting up a secondary channel named admin.
        2. Enable the Legacy Admin channel in Security Config.
    3. **Carrying Out Remote Admin Tasks**
        1. Open the Meshtastic App and connect to the local node.
        2. Go to Settings > Configure Node and select the remote node.
        3. Adjust supported Radio and Module settings as needed.
        4. When done, switch back to your local node in Settings > Configure Node.
2. **Android App**
    1. **Using the PKC Method (Firmware 2.5+)**
        1. Connect to the local (admin) node.
        2. Go to ⋮ > Radio Configuration > Security and copy the public key.
        3. Connect to the remote node.
        4. In the same Security menu, press "Add" and paste the public key into the Admin Key field.
        5. Up to 3 Admin Keys can be added, allowing multiple controlling nodes.
    2. **Using the Legacy Method (Firmware 2.4.x and earlier)**
        1. Set up an Admin channel by creating a secondary channel named admin.
        2. Enable the Legacy Admin channel in Security Config.
    3. **Carrying Out Remote Admin Tasks**
        1. Open the Meshtastic App and connect to the local node.
        2. In the node list pane, tap the Short Name in the colored bubble, then select More details.
        3. Select Remote Administration (gear icon).
        4. Configure Radio and Module settings as needed.
3. **Web Client**
    1. **Using the PKC Method (Firmware 2.5+)**
        1. Connect to the local (admin) node.
        2. Go to Config > Radio Config > Security and copy the public key.
        3. Connect to the remote node.
        4. In the same Security menu, add the public key as an Admin Key (only one Admin Key can be added via the web interface).
        5. Save the configuration.
    2. **Carrying Out Remote Admin Tasks**
        1. Remote administration commands are not supported in the Meshtastic Web Client.
4. **Python CLI/SDK**
    1. **Using the PKC Method (Firmware 2.5+)**
        1. Connect via USB to the local (admin) node.
        2. Retrieve its public key by running:
            1. meshtastic --get security.public_key
        3. Copy the public key for configuring the remote node.
        4. Connect via USB to the remote node.
        5. Set the Admin Key on the remote node by running:
            1. meshtastic --set security.admin_key "base64:PASTEPUBLICKEYHERE"
        6. Up to 3 Admin Keys can be added, allowing multiple controlling nodes.
    2. **Using the Legacy Method (Firmware 2.4.x and earlier)**
        1. Create an Admin channel as a secondary channel named admin.
        2. Enable Legacy Admin channel in Security Config by running:
            1. meshtastic --set security.admin_channel_enabled
    3. **Carrying Out Remote Admin Tasks**
        1. Use the --dest argument with the !nodeid of the target node.
        2. Only --set and --get commands are supported for remote administration.
        3. Example command to modify parameters or retrieve settings:
            1. meshtastic --set security.admin_key "PASTEPUBLICKEYHERE" --dest '!28979058'
                1. Linux/Mac: Use single quotes for --dest ('!nodeid').
                2. Windows: Quotes are not required (!nodeid).




