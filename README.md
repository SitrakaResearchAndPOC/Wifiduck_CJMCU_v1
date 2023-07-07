# Wifiduck_CJMCU_v1
This is a wifiduck using version v1 (with locale option for languages of keyboard)  
* Tools by spacehuhn for hacking HID using wifi (wifiduck using CJMCU devices)
* Could be used to act as keyboard wireless with pre-programmed payload
* Devices : wifiducky CJMCU, wifiducky DSTIKE, malduino W
* Tested devices : wifiducky CJMCU
<img src="https://github.com/SitrakaResearchAndPOC/Wifiduck_CJMCU_old/blob/main/cjmcu1.jpeg" width="250px" align="center">

# Installing driver of USB (could be CP21x, FT23X, CH340G, PL23X)
(In my case, it's [CP21x](https://drive.google.com/file/d/18dX5ws61_A4EaHKuIYNDSMMeMPuJHZG5/view?usp=drive_link))
* [CH34xG](https://www.wch-ic.com/downloads/CH341SER_ZIP.html)
* [FTDI and FT232RL](https://ftdichip.com/drivers/)
* [CP210x](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)

# Finding port of CJMCU
* Plug CJMCU
* search : "devices manager" and click it
* click "Ports (COM and LTP)"
* remind the number of port come noted as COMX
* click on COMx and click "all parameters" memories the baudrates note as Y 
* Close all

# Downloading firmeware of malduino_w_esp8266_v1.1.0 (version 2021)
* [malduino_w_esp8266_v1.1.0.bin](https://drive.google.com/file/d/1SSjDP6GQkt_XkdyqZivZoHEdDv-dNrCT/view?usp=drive_link)
  
# Installation ESP8266Flasher
* Download [esp8266Flasher](https://drive.google.com/file/d/1YC0DqRsgMTjVpCc77wQt9xKFKphjFWGM/view?usp=drive_link)
* Launch ESP8266Flasher.exe

# Flashing malduino_w_esp8266_v1.1.0
* Download Arduino and upload this code [step1](https://github.com/SitrakaResearchAndPOC/Wifiduck_CJMCU_old/blob/main/step1.ino)  (select following port and type of board before uploading) 
* Connect The two pins as :
  
    <img src="https://github.com/SitrakaResearchAndPOC/Wifiduck_CJMCU_old/blob/main/cjmcu2.jpeg" width="750px" align="center">
    <img src="https://github.com/SitrakaResearchAndPOC/Wifiduck_CJMCU_old/blob/main/cjmcu3.jpeg" width="350px" align="center"></img>

* Run esp8266 flasher named as  : ESP8266Flasher.exe
* In operation, Change port com as COMx
* In config, change with the firmeware malduino_w_esp8266_v1.1.0.bin
* In Advanced, change bauderate as Y at the first step
* After successfull flashing, don't the two pins in the first step
* Upload this code [atmega_duck.ino](https://drive.google.com/file/d/1zHDqU84Nn2bEMdnKmmQQGBDXHRQz9c20/view?usp=drive_link)  (select following port and type of board before uploading)
* Open arduino IDE and open the project atmega_duck/atmega_duck.ino
* uncomment line 16 in config.h like this
```
  /*! ===== Communication Settings ===== */
#define ENABLE_SERIAL
```

# Using wifiduck
* Reuplug the wifiduck
* Finding wifi network name <i>wifiduk</i> and password <i>wifiduck</i>
* On broswer enter : http://192.168.4.1
* Test this script ducky :
```
LOCALE FR
DEFAULTDELAY 100

WINDOWS r
STRING notepad.exe
DELAY 100
ENTER
STRING YOUR PC IS HACKED!
CTRL s
STRING test.txt
ENTER
LEFT
ENTER
```
  
# Documentations
* https://github.com/SpacehuhnTech/WiFiDuck/releases
* https://github.com/SpacehuhnTech/WiFiDuck/issues/124
* https://github.com/SpacehuhnTech/WiFiDuck
