# ZeroTwin 1.0
<div align="center">
<p align="center">
<a href="https://www.pinterest.com/pin/1021472759207960944/"><img title="ZeroTwin Logo" src="https://raw.githubusercontent.com/shinyxn/ZeroTwin/master/images/ZeroTwinLogo.jpg" width="300" height="300"></a><br>

[![forthebadge](https://forthebadge.com/images/badges/made-with-c-plus-plus.svg)](https://github.com/shinyxn/ZeroTwin)

[![GitHub release](https://img.shields.io/github/release/shinyxn/ZeroTwin.svg)](https://github.com/shinyxn/ZeroTwin/releases/) [![GitHub license](https://img.shields.io/github/license/shinyxn/ZeroTwin.svg)](LICENSE)  [![Maintenance](https://img.shields.io/badge/maintained%3F-yes-yellow.svg)](https://github.com/shinyxn/ZeroTwin/graphs/commit-activity) [![GitHub](https://badgen.net/badge/icon/shinyxn?icon=github&label)](https://github.com/shinyxn)

<center>
<b>ESP8266 EvilTwin &amp; deauther all-in-one WiFi pen-testing tools</b><br>
Easy to modify, customize captive portal, and integration with 0.96 inch OLED<br>
</center>
</p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#disclaimer">Disclaimer</a></li>
        <li><a href="#conclusion">Conclusion</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li>
    <a href="#usage">Usage</a>
          <ul>
        <li><a href="#diagram">Diagram</a></li>
        <li><a href="#wiring">Wiring</a></li>
        <li><a href="#how-to-use">How to use</a></li>
        <li><a href="#customization">Customization</a></li>
      </ul>
    </li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="LICENSE">License</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
    <li><a href="#donations">Donations</a></li>
  </ol>
</details>

# About The Project
![ZTBoot](images/ZTBoot.gif)

This project is a development of existing projects such as [ZiFi](https://github.com/sankethj/ZiFi), and [M1z23R](https://github.com/M1z23R/ESP8266-EvHere) with the addition of `0.96 inch OLED Display` integration, `RSSI` (received signal strength indication), several changes to `captive pages`, some fixing and adjustments to the `ESP8266 Boards Manager` to avoid `errors when deauthing`, and fixed other issues like the `captive portal not opening automatically`.

<i>The name of this project is inspired by Zero Two from Darling In The Franxx</i>

## Disclaimer
__IMPORTANT:__
- This tool is for testing and educational purposes
- Please use this tool for pen-testing purposes on your **own network or a network that you have permission for**
- All consequences of using this tool are the user's responsibility, so **DWYOR** (*Do With Your Own Risk*).

**I don't take any responsibility for what you do with this program in the future**

## Conclusion
<p align="center">
<img title="ZeroTwin Logo" src="https://raw.githubusercontent.com/shinyxn/ZeroTwin/master/images/ZTBoot.jpg" width="200" height="200">
<img title="ZeroTwin Deauth" src="https://raw.githubusercontent.com/shinyxn/ZeroTwin/master/images/ZTDeauth.jpg" width="200" height="200">
<!-- <img title="ZeroTwin EvilTwin" src="https://raw.githubusercontent.com/shinyxn/ZeroTwin/master/images/ZeroTwinEvilTwin.jpg" width="300" height="400"> -->
</p>
This tool utilizes the deauth attack, which is used to disconnect devices from their WiFi network. After the client disconnects, this tool creates a clone SSID of the target WiFi. 

*After that EvilTwin will do his job.*
<br>

# Getting Started
Here are some steps on how to compile this project and a guide for using it.

Untuk intstruksi dalam Bahasa Indonesia silahkan [__buka halaman ini__]().

## Prerequisites
Here are the things you need to prepare:
- ESP8266 Development Board (NodeMCU, Wemos D1 Mini, etc)
- [Arduino IDE](https://www.arduino.cc/en/software)
- OLED 0.96” I2C Display (optional)
- Project board and some jumper cables (optional)

## Installation
- Open your Arduino IDE and add [**Deauther ESP8266 Boards**](https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json) URL in the Additional Board Manager (`File` > `Preferences` > `Additional Board Manager URLs`), then add/paste this URL 
`https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json`
<br>or you can refer to the [Spacehuhn Deauther ESP8266 Boards installation wiki](https://github.com/spacehuhntech/esp8266_deauther/wiki/Installation#compiling-using-arduino-ide)
- Go to `Tools` > `Board` > `Boards Manager`, search `deauther` and install `Deauther ESP8266 Boards`
- Go To `Tools` > `Board` > `Deauther ESP8266 Boards` (make sure it's `Deauther ESP8266 Boards`) and select your board. 
<br>Because I using NodeMCU, so I choose NodeMCU
- Download [this ZeroTwin projects](https://github.com/shinyxn/ZeroTwin/releases/), and open the `ZeroTwin v1.0.ino - English` with Arduino IDE
- Go To `Tools` > `Manage Libraries`, then type `Adafruit SSD1306` in the search box and install the library. (make sure the library is `Adafruit SSD1306 by Adafruit`)
- Choose the correct COM port, click "`Upload`" to start the compiling process, and upload the source code to the ESP8266 board.
- You are done!

# Usage
**If you don't want to integrate with OLED, you can [skip](#how-to-use) the following step**

## Diagram

![Diagram](images/Diagram.png)

Or you can use the following table as a reference

## Wiring

| OLED PIN      | ESP8266       |
| ------------- | ------------- |
|  VCC          |  `3.3V`       |
|  GND          |  `GND`        |
|  SCL          |  `D1`         |
|  SDA          |  `D2`         |

## How to use
- After completing the steps above, connect to the SSID named `ZeroTwin v1.0` with password `zero8888` (you can customize it later)
- Wait until the portal page automatically opens, if not opening automatically, go to `192.168.4.1` in your favorite browser
- Select the target SSID
- Look on att4ck panel and click `Start Deauth`
- After a while, click `Start Evil-Twin`

The AP's mode will stopped and starting Evil-Twin mode

<center><img title="ZeroTwin Deauth" src="https://raw.githubusercontent.com/shinyxn/ZeroTwin/master/images/ZTDeauth.jpg" width="300" height="200"></center>
<br>

The OLED display will show the log and captured events of the tools. If the password entered in the captive portal is true, the clone SSID will disappear, and deauth automatically stop. Then connect to `Zero Twin v1.0`, the result will appear at the bottom of the pages.

<center><img title="ZeroTwin Deauth" src="https://raw.githubusercontent.com/shinyxn/ZeroTwin/master/images/ZTEvilTwin.jpg" width="300" height="300"></center>
<br>

## Customization
You can easily find some variables at the top of the source code, you can doing something such as changing the default SSID and password, customizing the captive portal, etc.

# Contributing
If you have a suggestion that would make this better, please fork the repo and create a pull request. Don't forget to give the project a star and follow my GitHub account! Thanks

Steps if you want to make a translated version for your languages:
1. [Fork](https://github.com/shinyxn/ZeroTwin/fork) the repository
2. Create a folder with names "`ESP8266-ZeroTwin [Languages]`". (Example: "`ESP8266-ZeroTwin English`").
3. Also rename the files as "`ESP8266-ZeroTwin [Languages].ino`"
4. Commit your changes and open a pull request [here](https://github.com/shinyxn/ZeroTwin/pulls)

# Acknowledgements
A huge thanks to:
- [@sankethj](https://github.com/sankethj)
- [@M1z23R](https://github.com/M1z23R)
- [@spacehuhn](https://github.com/spacehuhn)

# Donations
If you liked my project and want to support me, you can give me a cup of coffee :)

<a href="https://coindrop.to/shinyxn" target="_blank"><img src="https://coindrop.to/embed-button.png" style="border-radius: 10px; height: 57px !important;width: 229px !important;" alt="Coindrop.to me"></img></a>

[![Bitcoin](https://img.shields.io/badge/Bitcoin-000?style=for-the-badge&logo=bitcoin&logoColor=white)](https://coindrop.to/shinyxn) [![Ethereum](https://img.shields.io/badge/Ethereum-3C3C3D?style=for-the-badge&logo=Ethereum&logoColor=white)](https://coindrop.to/shinyxn)
