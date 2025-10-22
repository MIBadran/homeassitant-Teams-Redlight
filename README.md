# homeassitant-Teams-Redlight

This automation captures when a Teams call is happening in ytour LAN and adjust light and/or sounds of devices accordingly.
Suggestions:
  1- Turn office light to Red
  2- Mute Google Home and Alexa Microphone
  3- Set volume low on All TVs and Speaker Devices

First Install Syslog receiver from Homme Assistant Community https://community.home-assistant.io/t/introducing-syslog-receiver-a-new-hacs-integration-for-ingesting-syslog-into-home-assistant/899687

Then configure your router to send Teams client source ports Logs to Syslog in HA using just IPTables https://github.com/MIBadran/homeassitant-Teams-Redlight/blob/main/routerScript

Finaly add this automation from this repository https://github.com/MIBadran/homeassitant-Teams-Redlight  and adjust as needed .


