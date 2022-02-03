---
title: 'Použití příkazu chmod'
author: "Jan Malčák"
description: 'Jednoduchý tip popisující práci s příkazem <em>chmod</em>.'
date: '2011-03-05T23:06:00+02:00'
keywords: ["linux", "chmod", "command line", "terminal", "příkaz", "chown"]
tags: ["tutoriál", "linux"]
readingTime: 1
---

``chmod`` je linuxový příkaz, který změní přístupová práva k souboru nebo adresáři. Přístupová práva jsou jakési pravidla, která systému říkají, co kdo smí se souborem nebo adresářem dělat. ``chmod`` rozlišuje právo na spouštění, právo na zápis a právo na čtení a jejich vzájemné mutace (o tom za chvíli). Každé právo má své číselné označení:
 
 - **0** - bez práva
 - **1** - právo na spuštění
 - **2** - právo na zápis
 - **4** - právo na čtení
 
Aby se rozlišilo, pro koho dané pravidlo platí, zadávají se v trojmístném čísle: XXX, kde první místo znamená **práva uživatele**, který soubor vlastní, druhé místo jsou **práva skupiny**, ve které uživatel je a třetí jsou **práva ostatních**. 

Nyní se vrátím k tomu, že ``chmod`` používá mutace výše uvedených práv. Je to víc než logické, protože jinak by nešlo zapsat to, aby uživatel měl právo jak zapisovat tak číst. Proto se číselná označení práv sčítají:
	
    1 (právo ke spuštění) + 2 (právo na zápis) = 3 (uživatel může jak číst, tak zapisovat)
    
Nyní už víte vše, co je potřeba a tak doplním plně funkční příklad. Mějme soubor *test.txt*, kterému budeme chtít nastavit:
    
- uživatel může číst, zapisovat i spouštět (4 + 2 + 1)
- skupina může číst a zapisovat (4 + 2)
- ostatní mohou jen číst (4)

Příkaz:

    chmod 764 test.txt

A to je celé.

# Další příkazy

Nastaví souboru *soubor2* stejná práva, jako má *soubor:*

    chmod --reference=soubor soubor2
    
Nastaví práva rekurzivně (tedy bude procházet všechny podadresáře):

    chmod -r 700 ./
    
Změní vlastníka souboru:

    chown root file.txt
    
Změní vlastníka i skupinu:

    chown petr:uzivatele file.txt
