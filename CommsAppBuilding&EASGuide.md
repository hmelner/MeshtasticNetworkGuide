## **Basics of Building of SMS and Arduino Apps**

## SMS App
```mermaid
  graph LR
  A["1\) Find an App Developer<br>e.g. React Native, Flutter"]
  style A fill:#67ea94,stroke:#000000,stroke-width:2px
  B["2\) Install software<br>e.g. Node.js"]
  style B fill:#67ea94,stroke:#000000,stroke-width:2px
  C["3\) Design simple UI for easy usage"]
  style C fill:#67ea94,stroke:#000000,stroke-width:2px
  D["4\) Integrate SMS Functionality"]
  style D fill:#67ea94,stroke:#000000,stroke-width:2px
  E["5\) Set up Message Processing"]
  style E fill:#67ea94,stroke:#000000,stroke-width:2px
  F["6\) Test/Publish App"]
  style F fill:#67ea94,stroke:#000000,stroke-width:2px

  A-->B
  B-->C
  C-->D
  D-->E
  E-->F
```
Creating any app requires an app developer, and since our objective here is an SMS app that can be accessible to everyone, we can use platforms like React Native or Flutter which can run on both IOS and Android phones. Next we have to install the necessary software for the platform, like Node.js or React Native, to execute code. Then we design the UI for the app, or how it will look for the user, including a page for the chat channels and the threads in each individual chat. After that we implement the different components necessary for an SMS app through code, like sending and receiving messages and accessing SMS features specifically. And finally, we can test and publish the app.


## Arduino App
```mermaid
  graph LR
  A["1\) Find suitable Arduino board"]
  style A fill:#67ea94,stroke:#000000,stroke-width:2px
  B["2\) Find GSM Module<br> (**G**lobal **S**ystem for **M**obile)"]
  style B fill:#67ea94,stroke:#000000,stroke-width:2px
  C["3\) Install software <br> Arduino IDE"]
  style C fill:#67ea94,stroke:#000000,stroke-width:2px
  D["4\) Connect GSM Module to Arduino"]
  style D fill:#67ea94,stroke:#000000,stroke-width:2px
  E["5\) Write code <br> use AT commands"]
  style E fill:#67ea94,stroke:#000000,stroke-width:2px

  A-->B
  B-->C
  C-->D
  D-->E
```
There are different types of Arduino boards to pick from to create a communication Arduino app; considering the input and output pins on the board, an Arduino MKR GSM 1400 would be a good fit for the following steps. We would then need a GSM module, which is a small device that accepts a phone SIM card and allows the phone to connect to a communication system. When a message is sent, the arduino sends commands to the GSM, which then sends an SMS to the phone specified. Then we install the software, like for the SMS app, and in this case it would be the arduino IDE . After that, we connect the GSM module to the Arduino through pins. And finally, we write the code for the Arduino app, in which we can use AT commands for network connection.


## Key Components of A Messaging App
1) **Authorization -** Give users a personal account, whether it be using a phone number, email, or an app specific user and password login.
2) **Access to Contacts -** Include a feature where users are able to give access to their existing contacts app to transfer that information rather than manually creating new contacts for the new app.
3) **Sharing Location -** Make sure that the user is able to share their location easily, as this is important for emergency situations.
4) **Error-Handling -** The app should be able to handle invalid inputs, failed messages and network issues, and notify the user when this occurs.
5) **SMS Character Limits -** Set character limits for the size of a message to reduce the likelihood of time delays or other errors for message sending.
6) **Time Stamping -** Display time-stamping as this is important in emergency situations.

## **Emergency Alert System (EAS) Integration**

Existing examples of EAS systems include Ambert Alerts, Meshtastic SAME EAS Alerter, and Disaster Radio. Amber Alerts specifically are used to alert about kidnappings of children 17 or younger, only if it’s believed by the law enforcement agency that the child is in imminent danger of injury or death. There’s criteria in place that the scenario has to fit before an amber alert is sent out so that the alert isn’t overused, because that would make it undermined by the public and ineffective. The Meshtastic SAME EAS Alerter is a github project in which the alerter “listens” for warnings or emergency messages, like those from the national weather service, and sends that information in messages through a meshtastic network. It uses RTL SDR, which a low cost software defined radio usb connection device that can receive and transmit signals and also decode radio transmissions. There are two channels, the alert channel for real emergency alerts and the test channel for test messages that make sure the system is working. Disaster Radio is an older github project which implements meshtastic technology with more messaging and networking tools for an area without traditional infrastructure.


## Meshtastic Integration Approach
```mermaid
  graph LR
  A["1\) Implement gateway nodes with SDR reciever"]
  style A fill:#67ea94,stroke:#000000,stroke-width:2px
  B["2\) Gateway node listens for EAS signals"]
  style B fill:#67ea94,stroke:#000000,stroke-width:2px
  C["3\) Node processes info from detected alerts"]
  style C fill:#67ea94,stroke:#000000,stroke-width:2px
  D["4\) Node broadcasts message across meshtastic network"]
  style D fill:#67ea94,stroke:#000000,stroke-width:2px

  A-->B
  B-->C
  C-->D
```
Integrating an EAS system into Meshtastic could be done using gateway nodes, which are like bridges, in that they can recieve alerts from other official sources and put them into the Meshtastic system. For connection, we can use radio signals such as the NOAA weather radio or SAME-coded Amber alerts, and set up an SDR reciever to recieve and decode the alerts. The bridging process begins with the gateway node listening for emergency alert signals, then processing the information from any detected alerts. After this, it will be able to broadcast the message across Meshtastic network to devices within range, then allow those devices to pass on the message to farther devices.

 
## Key Components and Challenges of an EAS App
1) **Verification of information -** Alerts must be accurate and follow a set of criteria to qualify as an emergency (as explained with Amber Alerts) so that they are not undermined and ineffieicnt.
2) **Alert Sending -** All devices or nodes within the range meant to recieve the alert should recieve the alert.
3) **Improve Remote Area EAS Access -** The Meshtastic alert system can be combined with other official alert platforms (e.g. FEMA's IPAWS, NOAA Weather Radio, SAME) so people in more remote areas relying on meshtastic can get real time alerts from those as well.
