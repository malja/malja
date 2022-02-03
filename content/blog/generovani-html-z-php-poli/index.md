---
title: 'Generování HTML z PHP polí'
author: "Jan Malčák"
date: '2013-08-28T10:53:00+02:00'
keywords: ["formátování", "print_r", "var_dump", "tabletizer"]
tags: ["tutoriál", "programování", "php"]
readingTime: 1
showFullContent: true
---

Při výpisu objemných PHP polí byli mými nejlepšími společníky funkce ``print_r()`` a ``var_dump()``. Výpis z nich se navíc musí dále obalit přinejmenším do tagů ``pre``, aby výstup byl alespoň trochu čitelný. Navíc postup, který jsem k tomu používal:

```php
echo "<pre>";print_r($promenna);echo "</pre>";
```

se mi v kódu vůbec nelíbil. Proto jsem si vytvořil třídu, která formátování obstará za mě. Tak vznikla třída ``Tabletizer``. Díky ní je vytvoření pěkné tabulky otázkou pár řádků:

```php
$table = new Tabletizer();
echo $table->fromArray($promenna);
```

Jasně, řádky neušetřím, ale vypadá to o mnoho lépe. 

**Poznámka z roku 2018:** Zpětně by bylo vhodnější využít kratší název třídy a metodu ``fromArray`` udělat statickou. 

A to je vše. Výstupem může být třeba i takováto tabulka. 

{{< figure src="https://github.com/malja/archive/blob/master/php/Tabletizer/website/img/tabletizer.png?raw=true" alt="Tabletizer" caption="Tabletizer" >}}

Díky tomu, že hlavní tabulce je přiřazena třída ``.tabletizer``, je velice jednoduché vytvořit si jakýkoli styl, který sedí do okolního "prostředí". Vzhled tabulky si je možné jakkoli přizpůsobit.

Odkaz ke stažení, spolu s návodem a seznamem změn je možné najít na [této stránce](https://github.com/malja/archive/tree/master/php/Tabletizer)