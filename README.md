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
  
  > Theoretisch unendlich, praktisch ist es physisch begrenzt, da jeder Teilnehmer eine ID benötigt, und es nicht unendlich gibt.

- Wie können Grenzwerte definiert werden, die zur Steuerung bzw. Notifikation herangezogen werden?

## Implementierung

![Aufbau](img_aufbau.png)


Grundsätzlich besteht unser Aufbau aus einem Raspberry Pi Pico, der über SPI mit dem JOY-IT CAN module verbunden ist. Dieses Modul besteht aus dem MCP2515, einem "Stand-Alone CAN Controller with SPI Interface" [3]. Zwischen dem Pico und dem CAN module befindet sich ein Spannungswandler, der zusammen mit dem Raspberry Pi Pico auf dem Breadboard angebracht ist. Auf der Seite des Rasbperry Pi Picos sind neben der Spannungsversorgung von 5V und der GND die vier Pins von SPI0 (21, 22, 24, 25) mit dem CAN module verbunden, was das SPI Interface bereitstellt [2]. Auf der CAN module Seite gibt es zwei Spannungsversorgende Pins (VCC, VCC1), GND, CS (verbunden mit CSn), SCK (verbunden mit SCK), SI (verbunden mit TX), SO (verbunden mit RX) [6].

Zum Testen der Verbindung haben wir auf der anderen Seite einen ähnlichen Aufbau mit einem Raspberry Pi 3B statt einem Raspberry Pi Pico aufgebaut.
Beim RaspberryPi war bereits eine static IP Adresse konfiguriert, was wir zuerst nicht gewusst haben und davon ausgegangen sind, dass man sich via. `raspberrypi.local` verbinden kann. Das haben wir dann festgestllt, die IP Adresse ausgelesen und dann hat das verbinden via. SSH funktioniert. [8]

> > 

## Quellen

[1] "Grundlagen zum CAN Bus"; [mikrocontroller.net](https://www.mikrocontroller.net/attachment/6819/canbus.pdf); zuletzt aufgerufen am 12.01.2023

[2] "RaspberryPi PinOut"; [raspberypi.com](https://datasheets.raspberrypi.com/pico/Pico-R3-A4-Pinout.pdf); zuletzt aufgerufen am 12.01.2023

[3] "MCP2515 Datasheet"; [microchip.com](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP2515-Stand-Alone-CAN-Controller-with-SPI-20001801J.pdf); zuletzt aufgerufen am 12.01.2023

[5] "CAN Module | Joy-IT"; [joy-it.net](https://joy-it.net/en/products/SBC-CAN01); zuletzt aufgerufen am 12.01.2023

[6] "SBC Can-01"; [joy-it.net](https://joy-it.net/files/files/Produkte/SBC-CAN01/SBC-CAN01-Anschlussplan.pdf); zuletzt aufgerufen am 12.01.2023

[7] "Can Interface & Receiver"; [joy-it.net](https://joy-it.net/files/files/Produkte/SBC-CAN01/SBC-CAN01-Datenblatt.pdf); zuletzt aufgerufen am 12.01.2023

[8] "Raspberry Pi: Configure Static IP before booting"; [labcrasher.com](https://labcrasher.com/2021/08/24/raspberry-pi-configure-static-ip-before-booting/); zuletzt aufgerufen am 12.01.2023
