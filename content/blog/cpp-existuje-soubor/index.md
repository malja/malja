---
title: 'C++: Existuje soubor?'
author: "Jan Malčák"
description: 'Dnes jsem při programování "Úžasné megalomanské hry, která mi určitě zajistí milióny" narazil na problém jak zjistit, zda soubor, který chci načíst existuje. '
date: '2013-07-04T14:20:00+02:00'
keywords: ["linux", "open", "soubor", "existuje", "exists", "file", "access", "stat"]
tags: ["tutoriál", "linux", "cpp"]
readingTime: 1
---

Pokud bych chtěl jsen přečíst data, jde o problém celkem triviální. Stačí se pokusit tento soubor otevřít. Cest je opět několik:

<script src="https://gist.github.com/malja/6d8ce3dbe39af056e0e690f8cdac3719.js?file=file_exists_open.cpp"></script>    

Takový postup bude ve většině případů plně dostačující. Pro úplnost uvedu ještě příklad s využitím funkce ``access``

<script src="https://gist.github.com/malja/6d8ce3dbe39af056e0e690f8cdac3719.js?file=file_exists_access.cpp"></script>

Co ale dělat v případě, že chceme o souboru zjistit více informací? Je soubor spustitelný? Jaká je jeho velikost? Jaké je ID vlastníka? V takovém případě se můžeme opřít o funkci ``stat``

    // Funkce bere jako parametr jméno souboru a ukazatel na strukturu do které má doplnit data
    int stat(const char *filename, struct stat *buf);
    
Obsah struktury jde vyčíst třeba na [Wiki](http://en.wikipedia.org/wiki/Stat_(system_call))

- **st_dev** - ID zařízení, na kterém je soubor uložen
- **st_ino** - Číslo [inode](http://cs.wikipedia.org/wiki/Inode)
- **st_mode** -Obsahuje práva k souboru
- **st_nlink** - Počet [pevných odkazů]("http://cs.wikipedia.org/wiki/Pevn%C3%BD_odkaz)
- **st_uid** - ID vlastníka 
- **st_gid** - ID skupiny ve, které je vlastník
- **st_size** - Celková velikost v bytech
- **st_atime** - Čas posledního přístupu k souboru
- **st_mtime** - Čas poslední změny
- **st_ctime** - Poslední změna statusu (= změna čísla inode)

Pro další využití bude nejdůležitější obsah ``st_mode``. Pro testování jeho obsahu jsou zavedeny mimo jiné [mimo jiné](http://pubs.opengroup.org/onlinepubs/7908799/xsh/sysstat.h.html) tyto masky:

- **S_IFREG** - Jde o soubor
- **S_IFLNK** - Jde o symbolický odkaz
- **S_IFDIR** - Jde o adresář
- **S_IRUSR** - Práva pro čtení vlastníkem
- **S_IWUSR** - Práva pro zápis vlastníkem
- **S_IXUSR** - Práva pro spuštění vlastníkem

Krom masek existuje ještě několik maker. Jako jediný parametr ``m`` se jim předává ``st_mode``. Návratovou hodnotou maker je buď 0, v případě že test neuspěl nebo nenulová hodnota pokud test uspěl.

- **S_ISDIR(m)** - Jde o adresář
- **S_ISFIFO(m)** - Jde o [rouru](http://cs.wikipedia.org/wiki/Roura_(Unix)) nebo speciální soubor [FIFO]("https://cs.wikipedia.org/wiki/Metoda_FIFO)
- **S_ISREG(m)** - Jde o soubor
- **S_ISLNK(m)** - Jde o symbolický adresář

Konečně je čas na ukázku použití funkce ``stat`` v akci: 

<script src="https://gist.github.com/malja/6d8ce3dbe39af056e0e690f8cdac3719.js?file=file_exists_stat.cpp"></script>