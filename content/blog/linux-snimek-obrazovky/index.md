---
title: 'Linux: Snímek obrazovky'
author: "Jan Malčák"
description: 'Pokud někdy budete potřebovat zachytit snímek obrazovky, aktuálního okna, vybrané části nebo dokonce celé webové stránky, bude se Vám hodit některý ze zde popsaných programů a příkazů do konzole.'
date: '2009-08-09T21:43:00+02:00'
keywords: ["linux", "screenshot", "snímek obrazovky", "gimp", "xwd", "import", "printscreen", "screengrab", "firefox"]
tags: ["tutoriál", "linux"]
readingTime: 2
---

# Applet do panelu
Asi nejdednoduším způsobem je aplet, který si velice jednoduše vložíte do panelu. Po přidání se objeví ikonka která po stisku zachytí požadovaný obrázek. Tato varianta nemá mnoho nastavení a možností, zato však stojí nejméně práce a je funkčí skoro ihned.

## Přidání apletu

Pravým tlačítkem myši klikněte na panel, kam chcete aplet přidat. Po kliknutí se objeví malé okénko - klikněte na **Přidat nové položky**. Po otevření okna najděte plet jménem **Snímek obrazovky** a klikněte na **Přidat**. Po přidání si musíte aplet nastavit - vše je čistě na vás (Nastavení jde později neomezeně měnit). 

## Použití apletu

Pokud budete není potřebovat aplet použít, stačí kliknout na ikonku fotoaparátu.

# Gimp

Na pořízení snímku lze také použít grafický editor Gimp. Pořízení snímku provedete následovně: Klikněte na položku *Soubor*  -> *Create (Vytvořit)* a vyberte *Snímek obrazovky*. Vše si nastavte dle libosti.

# Příkaz ``import``

Snímek můžete pořídit i tak, že do konzole zadáte příkaz:
    
    import -window root obrazek.png
    
Samozřejmě si musíte upravit adresu kam se soubor uloží (v tomto případě je to složka ``root``) a také jméno souboru (v tomto případě je to ``obrazek.png``). Pro správný běh musíte nainstalovat balíček ``imagemagic``. 

# Příkaz ``xwd``

Postup je skoro totožný jako u příkazu ``import``. Po zapnutí konzole napište příkaz:

    xwd > obrazek.xwd
    
Zachycený obrázek bude ve formátu xwd – ten si musíte převést na něco známějšího (např. jpg), k tomu může posloužit třeba Gimp.

# Klávesa PrintScreen

Pokud máte prostředí Gnome a na vaší klávesnici je tlačítko PrintScreen (nebo PrtScr) můžete si jejím stiskem vytvořit snímek obrazovky. Není zde žádné nastavení,ale tato možnost nepotřebuje žádný program a je asi nejrychlejší že všech popsaných možností.

# Screengrab

Screengrab je rozšíření pro Firefox, které umožňuje pořídit snímek celé (opravdu celé, ne jen části kterou vidíte) stránky, který si následně uložíte. Screengrab si jde stáhnout [zde](https://addons.mozilla.org/cs/firefox/addon/screengrab-fix-version/)

# Snímek konzole

Pokud nemáte grafické prostředí (nastavujete systém, apod.) můžete si pořídit snímek pomocí příkazu:

    fbgrab -s 5 obrazek.png
    
Tento příkaz počká 5 vteřin, a pak zachytí snímek jménem ``obrazek.png``.