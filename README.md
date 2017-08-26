# Home Assistant 
Here you can find my [Home Assistant](https://home-assistant.io/) configuration files. And installation setup. 

# My installation:
1. https://home-assistant.io/docs/installation/virtualenv/
2. nano /etc/systemd/system/home-assistant@homeassistant.service
```
[Unit]
Description=Home Assistant
After=network.target

[Service]
Type=simple
User=%i
ExecStart=/srv/homeassistant/bin/hass -c "/home/homeassistant/.homeassistant"

[Install]
WantedBy=multi-user.target
```
3. sudo systemctl --system daemon-reload
4. sudo systemctl enable home-assistant@homeassistant
5. sudo systemctl start home-assistant@homeassistant

# MQTT - Mosquitto

1. sudo apt-get install mosquitto
2. sudo apt-get install mosquitto-clients
3. sudo nano /etc/mosquitto/mosquitto.conf
4. sudo mosquitto_passwd -c /etc/mosquitto/pwfile mosquitto

Add:
```
allow_anonymous false
password_file /etc/mosquitto/pwfile
listener 1883
```