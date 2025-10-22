# homeassitant-Teams-Redlight
Teams call in home starts Automation script in HA
First Install Syslog receiver from Homme Assistant Community https://community.home-assistant.io/t/introducing-syslog-receiver-a-new-hacs-integration-for-ingesting-syslog-into-home-assistant/899687

Then configure your router to send Teams client source ports Logs to Syslog in HA using just IPTables https://github.com/MIBadran/homeassitant-Teams-Redlight/blob/main/routerScript

Finaly add this automation from this repository https://github.com/MIBadran/homeassitant-Teams-Redlight  and adjust as needed .


