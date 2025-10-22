# homeassitant-Teams-Redlight
Teams call in home starts Automation script in HA
First Install Syslog receiver from Homme Assistant Community https://community.home-assistant.io/t/introducing-syslog-receiver-a-new-hacs-integration-for-ingesting-syslog-into-home-assistant/899687

Then configure your router to send Teams client source ports Logs to Syslog in HA using just IPTables:
##################################################################################################################################
#!/bin/sh
iptables -N TEAMS_MEDIA_LOG 2>/dev/null
iptables -F TEAMS_MEDIA_LOG
iptables -D FORWARD -j TEAMS_MEDIA_LOG 2>/dev/null
iptables -I FORWARD 1 -j TEAMS_MEDIA_LOG

iptables -A TEAMS_MEDIA_LOG -p udp --sport 50000:50059 -d 52.112.0.0/14  -m limit --limit 1/second --limit-burst 1 -j LOG --log-prefix "TEAMS-MEDIA: " --log-level 5
iptables -A TEAMS_MEDIA_LOG -p udp --dport 50000:50059 -s 52.112.0.0/14  -m limit --limit 1/second --limit-burst 1 -j LOG --log-prefix "TEAMS-MEDIA: " --log-level 5
iptables -A TEAMS_MEDIA_LOG -p udp --sport 50000:50059 -d 52.122.0.0/15  -m limit --limit 1/second --limit-burst 1 -j LOG --log-prefix "TEAMS-MEDIA: " --log-level 5
iptables -A TEAMS_MEDIA_LOG -p udp --dport 50000:50059 -s 52.122.0.0/15  -m limit --limit 1/second --limit-burst 1 -j LOG --log-prefix "TEAMS-MEDIA: " --log-level 5
################################################################################################################################

Finaly add this automation from this repository https://github.com/MIBadran/homeassitant-Teams-Redlight  and adjust as needed 


