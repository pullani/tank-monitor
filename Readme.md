# A Fully Frugal IoT Device

# Particle App
https://go.particle.io/shared_apps/5f48b4aafb925e0016011adb

# Description (Version 02)
The main idea of the project is to develop an IoT device that can solve multiple common day problems through a frugal approach. Technically the project demonstrates how an IoT device can transmit data encrypted at all stages from device to cloud.

Hardware (Receiving end):
- Particle Argon
- LoRa module
- SPI/I2C OLED screen
- Li-Ion cell
- External antenna for LoRa (865 - 867MHz)

Hardware (Sending end):
- Arduino Pro Mini
- IP rated ultrasonic car reverse sensor based on HCSR04
- LoRa module
- External antenna for LoRa (865 - 867MHz)
- Sparkfun SunnyBuddy solar charger circuit
- Solar panel (9 - 12 Vmp, > 700mA Imp)
- Li-Ion cell
# Working
Water level will be periodically monitored by the Arduino Pro Mini through the ultrasonic sensor at the sending end. And each time this data is relayed via LoRa module to the receiver kept at ground level at a nearby power socket point (a house here). Receiver LoRa module data will be read by the particle Argon and data is sent to the Particle cloud account.
# Stages of transmission and encryption
1. LoRa to LoRa: The sending device can only talk to the receiving LoRa device. Eventhough this data is not encrpted, the receiver should know the secret device ID programmed to the sending one and vice versa. Also the air baudrate should be matched. Since the devices are local and a basic authentication is required, the end-to-end LoRa transmission can be considered secure.
2. Particle Argon to Cloud: Particle argon to Particle cloud is AES encrypted. Particle cloud can call a function (webhook) based on a particluar event posted by the argon device. This will trigger webhooks for email generation via SendGrid, SMS generation via Textlocal and also log data to a Thingspeak channel.
Textlocal accounts are subjected to a regulatory approval in India. In that case API calls to SMS services like Twilio can be tried in simar way.

# Connectivity:
A low cost 4G/3G pocket modem is being used to provide WiFi connection to the particle argon. Both reciever device and modem will be connected to a USB adapter connected to the wall socket.

# Project
Project solved a specific rural municipal water supply issue in Manro village in Kerala. Project provided water level monitoring of a municipal tank supplying water to a rural community. Critical level statuses were sent by SMS to the tank operator who is a few miles away from the tank. IEEE Student Branch of T.K.M College of Engineering conducted the project under its SIGHT (Special Interest Group for Humanitarian Technology). Project completed in 2016 with a version 01.

# Version 01
This project was selected by IEEE Humanitarian Activities Council for funding in frugal innovation section. 
Electronic hardware used were SIM900 module (2G), Arduino UNO board, HCSR04 based Ultrasonic sensor, Solar panel assembly and Li Battery.
Device was installed on top of the 50,000 litres tank on a pilot phase, and sent messages at critical points of water levels - Close to empty and close to overflow.

# Version 02
Version 01 did not last well in the pilot phase itself due to harsh weather, it faces issues from unreliable 2G network aswell. But the challenge faced by comminity was noticed by the authorities.
Version 02 is more complex and used best IoT hardware in the market. It ready to deploy.

Feel free to clone and use the code!

| |
|:-------------------------:|
|<img width="1604" alt="screen shot 2017-08-07 at 12 18 15 pm" src="https://github.com/pullani/tank-monitor/blob/master/guide/diagram.jpg">  Diagramatic representation |


| |
|:-------------------------:|
|<img width="1604" alt="screen shot 2017-08-07 at 12 18 15 pm" src="https://github.com/pullani/tank-monitor/blob/master/guide/device03.jpg">  Image 01 |

| | |
|:-------------------------:|:-------------------------:|
|<img width="1604" alt="screen shot 2017-08-07 at 12 18 15 pm" src="https://github.com/pullani/tank-monitor/blob/master/guide/device01.jpg">  Image 02 |  <img width="1604" alt="screen shot 2017-08-07 at 12 18 15 pm" src="https://github.com/pullani/tank-monitor/blob/master/guide/device02.jpg"> Image 03 |

