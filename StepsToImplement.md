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
1) **Radio Configuration** - Manages device operations and connectivity:
<ul>
  a) Bluetooth: Enable, Pairing Mode, Fixed PIN Channels: Index, Role, Settings
  b) Device: Role, Serial Output, Debug Log, Factory Reset
  c) Display: Screen Duration, Auto Carousel, GPS Format
  d) LoRa: Region, Modem, Max Hops, Transmit Power, etc.
  e) Network: WiFi & NTP settings
  f) Position: GPS settings & Smart Broadcast
  h) Power: Charge Current, Power Saving, Sleep Intervals
  i) Security: Keys, Admin Access, Debug Logs
  j) User: Long Name, Short Name, Licensing
</ul>
3) **Module Configuration** - Enhances device functionality:
4) **Remote Admin** - Securely manage nodes over the mesh:



