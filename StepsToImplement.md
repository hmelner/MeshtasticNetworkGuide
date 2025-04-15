# Step by Step Guide

### **Step 1: Choose a Device**
Can be installed on a range of development boards
Community Favorites:
  RAK Meshtastic Start Kit
    Wisblock Starter Kit
      Customizable, Beginner friendly, nRF52840 chip, Bluetooth, no soldering
      No built-in GPS, No Screen
    HELTEC LoRa V3
      Better handheld, More customization available, built-in OLED displays, ESP32, Ready-to-go, Wifi
      No GPS, Not easy to customize
    LILYGO LoRa T3-S3
      T-Echo	
        Backlit E-Ink screen, 5.0 Bluetooth, GPS, SX1262 chip, 850 mSh battery, no soldering, nRF52840, Ready-to-use product
        No Wifi, not easy to customize
      T-Beam 
        ESP32 microcontroller, LoRa radio module, OLED Display, GPS, Ready-to-go, GPS, Wifi
        Not easy to customize
      Nano G2 Ultra
        Portable, durable, uses low power MCU NRF52840, battery life ~5 days
      Station G2
        Designed to be a base station or in a vehicle (not very portable)
Note: 
Recommend devices with newer “Semtech SX126x or LR11xx series”
  -Increased receive and transmit performance
Recommend using “nRF52-based devices” – preferred for solar and handset

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
3) **Remote Admin** - Securely manage nodes over the mesh:
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

## Step 3: Connect to your Device




