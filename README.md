# Home Assistant Core Deployment with docker-compose

![alt text][screenshot]

## What is this ?

This is an example Home Assistant Core and Basic Companion stack with docker-compose

## Disclaimer

This repository just for example/development purpose, please use it with your own risk.

## Change requirement value

Rename or Copy `default.env` to `.env`

```
cp default.env .env
```

## Running with docker-compose
```
docker-compose up -d 
```

## Configure

1. Setting Node-RED credentials in ``settings.js`` within ``node-red`` directory

2. Setting proper serial port for zigbee dongle at 

```
    devices:
      - /dev/ttyACM0:/dev/ttyACM0
```

3. Access Home Assistant as you wish

## Access Companion

If you deploy on remote please access with ip address that you running at

- **Home Assistant** http://localhost:8123 or http://homeassistant.local:8123 
- **Node-RED** http://localhost:1880 
- **Zigbee2MQTT** http://localhost:8888 


## Quick version jumping

**When you need to change companion version**

change default value in `.env` file as you wish

| Variable      | Default value |
|---------------|---------------|
| `SET_TZ`      | latest |
| `HA_VER`      | latest |
| `Z2M_VER`     | latest |
| `NR_VER`      | latest |

rebuild with

```
docker-compose up -d --no-deps --build <service>
```

## Issue 

please check the issue tracker for similar issues before creating one.

## Credits

- [Home Assistant Core](https://www.home-assistant.io/faq/ha-vs-hassio/)
- [Home Assistant Docker Images](https://hub.docker.com/r/homeassistant/home-assistant)

## Home Automation Consultant Services
- [RACKSYNC CO., LTD.](https://racksync.com)

[screenshot]: screenshot.png "Home Assistant Training Course by RAcKSYNC CO., LTD."
