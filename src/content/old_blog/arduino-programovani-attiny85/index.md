---
title: 'Arduino: Programování Attiny85'
author: "Jan Malčák"
description: 'Z nějakého důvodu mi kdysi přišlo jako opravdu cool nápad koupit si několik miniaturních čipů ATtiny85. Ne že bych věděl co s nimi, spíš pro sichr. Jak se říká, co je doma, to se počítá.'
date: '2016-03-26T22:50:00+02:00'
keywords: ["arduino", "uno", "attiny85", "isp", "programmer"]
tags: ["tutoriál", "programování", "cpp"]
readingTime: 2
---

Teď, možná po roce či dvou, jsem je vyhrabal z krabice. Stále jsem přesně netušil, co s nimi, ale v hlavě se mi pár nápadů rýsovalo.

Z mých posledních pokusů jsem si pamatoval, že standardní USBisp, které jsem si koupil na programování čipů ATmega328 nejde použít. Nejjednodušší náhradou se mi jevilo využít Arduino Uno. Na internetu jsem našel velké množství tutoriálů, navíc jde o celkem jednoduchou záležitost.

Prvně je třeba přidat podporu pro čipy rodiny ATtiny do Arduino IDE. Od posledně se situace radikálně zlepšila a není třeba ručně cokoliv stahovat, rozbalovat a kopírovat na správné místo.

V Arduino IDE otevřete **Nastavení** -> **File** -> **Preferences** a do kolonky *Additional Boards Manager URLs* vložte jednu z následujících adres:
    
- https://raw.githubusercontent.com/damellis/attiny/ide-1.6.x-boards-manager/package_damellis_attiny_index.json
- http://drazzy.com/package_drazzy.com_index.json

První z nich přidává podporu jen pro ATtiny 44/45/84/85. Druhá je mnohem rozsáhlejší. Pro mé potřeby až zbytečně.

{{< figure src="AddAttinySupport.gif" caption="Přidání podpory pro Attiny" position="center" alt="Přidání podpory pro Attiny" >}}

Nyní v **Tools** -> **Board** -> **Boards Manager** vyberte a nainstalujeme ATtiny.

{{< figure src="AddAttinySupport2.gif" caption="Výše popsaný postup pro přidání podpory Attiny do Arduino IDE" position="center" >}}

Tím jsme naučili Arduino IDE hovořit jazykem ATtiny kmene. Už stačí jen udělat z Arduina programátor. Po připojení Arduina k počítači v IDE stačí vybrat vzorový příklad **ArduinoISP**
(**File** -> **Examples** -> **ArduinoISP** -> **ArduinoISP**) a nahrát ho. Tím se z Arduina stal programátor, který propojíme s ATtiny a můžeme začít.

{{< figure src="attiny85-pinout-simplified.png" caption="Popis pinů. Počítáno z levé horní strany po řádcích: (1) Reset (8) VCC, (2) A3 (7) Pin D2, (3) Pin A2 (6) Pin D1, (4) GND (5) Pin D0" position="center" >}}

Propojení je následující:

{{< figure src="http://highlowtech.org/wp-content/uploads/2011/06/Screen-shot-2011-06-06-at-1.46.39-PM.png" caption="Zapojení Arduina UNO a Attiny85 pro programování. Vypůjčeno z http://highlowtech.org/?p=1706" position="center" >}}

- ATtiny pin **2** do Arduino pinu **13**
- ATtiny pin **1** do Arduino pinu **12**
- ATtiny pin **0** do Arduino pinu **11**
- ATtiny pin **Reset** do Arduino pinu **10**

Teď už jen stačí otevřít Sketch, vybrat čip, který budete programovat a nastavit jako programátor **Arduino as ISP** a vše nahrát.

A ještě krátká poznámka na konec. Pokud stejně jako já, budete mít trable s nastavením exsterního oscilátoru, doporučuji před nahráním Sketche vypálit *Bootloader* (**Tools** -> **Burn Bootloader**)