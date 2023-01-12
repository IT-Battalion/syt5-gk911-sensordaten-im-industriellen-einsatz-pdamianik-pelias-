# SYT GK 9.1.1

## Fragestellungen

- Welche Übertragungsreichweiten und Geschwindigkeiten kommen beim CAN-Bus zum Einsatz?
  
  > | Bitrate     | Kabellänge |
  > | ----------- | ---------- |
  > | 10 kbits/s  | 6,7 km     |
  > | 20 kbits/s  | 3,3 km     |
  > | 50 kbits/s  | 1,3 km     |
  > | 125 kbits/s | 530m       |
  > | 250 kbits/s | 270m       |
  > | 500 kbits/s | 130m       |
  > | 1 Mbits/s   | 40m        |
  > 
  > [1]

- Welche Möglichkeiten des einfachen Deployments bieten sich an, wenn 
  verschiedene Services zur Darstellung von Sensordaten miteinander 
  agieren sollen?

- Wieviele Teilnehmer können dabei miteinander kommunizieren?

- Wie können Grenzwerte definiert werden, die zur Steuerung bzw. Notifikation herangezogen werden?

## Implementierung

![Aufbau](img_aufbau.png)



## Quellen

[1] "Grundlagen zum CAN Bus"; [mikrocontroller.net](https://www.mikrocontroller.net/attachment/6819/canbus.pdf); zuletzt aufgerufen am 12.01.2023

[2] "RaspberryPi PinOut"; [raspberypi.com](https://datasheets.raspberrypi.com/pico/Pico-R3-A4-Pinout.pdf); zuletzt aufgerufen am 12.01.2023

[3] "MCP2515 Datasheet"; [microchip.com](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP2515-Stand-Alone-CAN-Controller-with-SPI-20001801J.pdf); zuletzt aufgerufen am 12.01.2023

[5] "CAN Module | Joy-IT"; [joy-it.net](https://joy-it.net/en/products/SBC-CAN01); zuletzt aufgerufen am 12.01.2023

[6] "SBC Can-01"; [joy-it.net](https://joy-it.net/files/files/Produkte/SBC-CAN01/SBC-CAN01-Anschlussplan.pdf); zuletzt aufgerufen am 12.01.2023

[7] "Can Interface & Receiver"; [joy-it.net](https://joy-it.net/files/files/Produkte/SBC-CAN01/SBC-CAN01-Datenblatt.pdf); zuletzt aufgerufen am 12.01.2023
