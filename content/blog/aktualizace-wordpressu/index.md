---
title: 'Aktualizace WordPressu'
description: 'Aktualizovat doporučuji na každou novou stabilní verzi, pro případ nekompatibilit, které v tomto případě budou co nejmenší. '
author: 'Jan Malčák'
tags: ["tutoriál", "web"]
readingTime: 1
draft: false
date: '2009-06-12T16:35:00+02:00'
---

**Poznámka z roku 2018:** Tenhle článek je obsahem hodně za zenitem. Aktualizace WP je dnes otázkou dvou kliknutí. Všechno je automatizované a až na výjimky bezpečné (ve smyslu rozbití stránky a ztráty dat). Na druhou stranu jde o můj nejstarší zachovalý publikovaný článek. Krásně demonstruje dvě věci. Zaprvé vývoj mého psaného projevu (snad k lepšímu) a zadruhé posun v "přístupnosti" IT. Takže si zaslouží tu být :D.

Nyní si povíme jak aktualizovat náš Wordpress, bez ztráty dat:

- Proveďte zálohu databáze přes PhpMyAdmin
- Proveďte zálohu všech souborů
- Deaktivujte všechny pluginy (pro případ nekompatibilit)
- Smažte všechny soubory 	WordPressu, ale pozor, adesáře ``wp-content``, ``wp-config.php`` a soubor ``.htaccess`` (pokud ho máte). Ty nemažte, obsahují nastavení, obrázky, pluginy atd.
- Nahrajte nejnovější verzi [Českého WordPressu](http://acci.cz/wordpress)
- Nahrajte nejnovější verze používaných pluginů.
- Pomocí prohlížeče přejďete 	na ``http://vasweb.cz/wp-admin/upgrade.php`` a odklikněte upgrade databáze.

S trochou štěstí by Váš web měl fungovat. Doporučuji si ještě zkontrolovat, zda je Váš vzhled kompatibilní s novou verzí Wordpressu.
