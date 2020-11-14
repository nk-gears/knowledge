# Raspberry Pi

#### Overview 
- 2016 : Raspberry PI Model B
- This has been my goto home server
- Used to run Automations via NodeRED
- Manage Routing Ingress via NGINX Proxy Manager with SSL Support from LE



#### Details

The following are the apps running on the device 

- Docker
- Portainer
- lirc
- NGINX Proxy Manager


#### LIRC Challenges

- Spent almost 6 Months to getthe LIRC to work on Raspberry PI
- The main culprit is the buster os. 
- Then i switched back to the Stretch OS
- Now i can able to programme for any remote quickly using irrecord

#### Streamlne LIRC Signals
- Instead of directly dealing with the LIRC Handler Processing, I used the MQTT Protocol to capture the data and Process via MQTT Clients
- This way it supports short and long press that can be easily captured and sent to MQTT Cients via http


#### App Port Details

