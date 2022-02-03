---
title: ''
date: '14-03-2015 22:49'
publish_date: '14-03-2015 22:49'
metadata:
    keywords: 'arduino, serial, baudrate, 14400, 9600, port'
taxonomy:
    category:
        - tutorialy
    tag:
        - linux
        - programování
        - cpp
        - arduino

title: 'Arduino: Odpojení při nahrávání programu'
author: 'Jan Malčák'
date: '2015-03-14T22:49:00+02:00'
keywords: ["arduino", "serial", "baudrate", "14400", "9600", "port"]
tags: ["tutoriál", "linux", "programování", "cpp"]
readingTime: 1
showFullContent: true
---

Při experimentování s Arduinem jsem narazil na podivný problém. Po několika malých úpravách kódu mi editor při nahrávání programu hlásil 

    Error opening serial port '/dev/ttyACM1'

To vše doplněné dlouhým výpisem kde se chyba vyskytla.

Jako by to nestačilo, Arduino se poté odpojí. Pro připojení bylo nutné vytáhnout a opět zastrčit napájecí USB kabel. Tím se bohužel problém s odpojováním nevyřešil. Obšírným nahlédnutím do složky ``/dev`` jsem zjistil, že soubor ``ttyACM1`` existuje. Příkaz ``lsusb`` Arduino našel. Problém tedy musel být někde jinde.

Problém přetrvával i po změně zdrojového kódu či načtení některého z příkladů. Nezbylo mi tak, než použít Google. Dle všeho šlo o přepsání hodnoty: 

    Serial.begin(9600);
    
na 

    Serial.begin(14400);

Nová hodnota se uloží do uživatelského nastavení. Z nějakého mě neznámého důvodu zůstane tato hodnota v nastavení "zadrblá" i po opětovné úpravě zdrojáků. Je tedy nutné smazat soubor s nastavením (u mě ``~/arduino/preferences.txt`` a restartovat editor.