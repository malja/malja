---
title: 'Debian: Problém s LC_MESSAGES'
author: "Jan Malčák"
date: '2013-05-07T21:33:00+02:00'
keywords: ["linux", "debian", "locales", "lc_messages"]
tags: ["linux"]
readingTime: 1
showFullContent: true
---

Po dlouhé době spokojeného používání Debianu jsem dnes po troše šťourání se v systémových knihovnách znovu instaloval. Při ``apt-get dist-upgrade`` jsem ale narazil na následující chybovou hlášku: 

    locale: Cannot set LC_CTYPE to default locale: No such file or directory
    locale: Cannot set LC_MESSAGES to default locale: No such file or directory
    locale: Cannot set LC_COLLATE to default locale: No such file or directory

Řešením nakonec bylo nainstalovat balík ``locales`` a ``locales-all`` a spustit příkaz:

    locale-gen

Při hledání řešení jsem také narazil na možnost, že není uveden seznam lokalizací, ze kterých se má vybírat. V takovém případě editujte soubor ``/etc/locale.gen`` a odkomentujte (odstraňte znak # na začátku řádku) řádky s vaší lokalizací. Například v mém případě to je:

    cs_CZ.UTF-8 UTF-8

Teprve pak je možné spustit příkaz ``locale-gen``.