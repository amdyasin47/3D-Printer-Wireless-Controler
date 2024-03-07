# 3D Printer Wireless Gateway

I noticed that the Ender 3 v2s don't come with Wi-Fi, so this is my attempt to fix that.

![Dashboard](https://gitlab.com/MrDIYca/3DPWG/-/raw/main/img/dashboard.gif)

This project is explained in a lot more details in [my video](https://www.youtube.com/watch?v=VNWlUPR5YXM). I highly recommend you start by watching that first.

This project allows for the serial port of a 3D printer running G-Code (ex: Marlin firmware) to be accessed wirelessly using an ESP8266 micro-controller. Using this remote access, a web page running JavaScript is used to parse the Serial messages and display its data in a neat dashboord ( shown above). I have tested it on my Ender3 V2 but it should work on any 3D printers running G-Code.

# Installation

You will need an ESP8266 board. You can use an ESP01/S module, Wemos D1 mini or [my companion board](https://store.mrdiy.ca/p/3d-printer-wireless-gateway/). Moving forward I will refer to any of these boards as "the 3DWPG board".

1) Flash the 3DWPG board online using my [online flasher tool](https://mrdiyca.gitlab.io/mrdiy-esp-online-flasher/?projectId=3dprinter-wifi). You can also flash it using your favorite flashing tool. You will find the BIN files are in the /firmware folder.

2) Connect: There ar 4 wires to connect between the 3DWPG board and the 3D printer.
* Rx connects to Tx
* Tx connects to RX
* Power to Power Source from the printer ( ex: 5x for Wemos d1 mini, 3,3v for ESP01 ...etc)
* Ground to Any Ground on the 3D printer

For example, here is an example on how I did it on my Ender 3 V2 3D printer.

![Rx Tx Soldering](https://gitlab.com/MrDIYca/3DPWG/-/raw/main/img/serial_soldering.gif)

You will need to find a power source (5v or 3.3v)  from your 3D printer to power the ESP8266 board. The easiest way to find them is by checking your motherboard's schematic. If you are using [my companon board](https://store.mrdiy.ca/p/3d-printer-wireless-gateway/), then simply plug it in between the LCD cable and the motherboard, like this

![Companion board](https://gitlab.com/MrDIYca/3DPWG/-/raw/main/img/companion_board.gif)

# Setup

One you install the 3DWPG board and power it up, it will create a new access point called 'MrDIY 3DWPG'. Connect to it, the password is 'mrdiy.ca', and enter your Wi-Fi's credentials. If your browser doesn't popup, open it and visit http://192.168.4.1

# Usage

To start using the dashbaord, visit the [dashbaord URL](http://mrdiyca.gitlab.io/3DPWG/index.html), then enter your 3DWPG board IP address. You can find the IP address on the printer's screen or in your router's DHCP table. 

![Preview](https://gitlab.com/MrDIYca/3DPWG/-/raw/bd07013f915ed5e072a60b8881b8f3bdd605a3c2/frontend/img/preview.png)


