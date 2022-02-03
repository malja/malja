---
title: 'Kam s ní'
author: "Jan Malčák"
description: 'Za chvíli mě čeká opravdová zkouška dospělosti - maturita. A i když je nadpis lehce zavádějící, věřím, že by se naše učitelka češtiny nad touto parafrází nerudova fejetonu alespoň pousmála. Přes časový odstup nás oba pojí stejný problém. Potřebujeme někam něco zašit. Jen snad <em>to něco</em> se změnilo. Se slamníkem bych totiž věděl co a jak.'
date: '2016-02-04T01:50:00+02:00'
keywords: ["google drive", "onedrive", "cloud", "nas", "western digital", "hosting", "záloha"]
tags: ["blog"]
readingTime: 5
---

Já jsem řešil kam bezpečně a trvale uložit zálohu rodinných fotek a ostatních digitálních cenností. A to je, považte, úplně jiný šálek kávy. Už jen z důvodu nepřeberného množství nabízených možnosti.

# Optická media

Asi vím, co si teď myslíte. A popravdě si to myslím také. Optická média mají svůj nejlepší čas za sebou. Nicméně po starších zálohách (kterých jsem se z valné většiny při zimním úklidu zbavil) mi zbylo několik kvalitnějších dvouvrstvých DVD. Myšlenka je znovu po několika letech znovu vytáhnout na světlo mi rozhodně probleskla hlavou. Ale jen na chvilku. Přísahám!

Už teď se mechaniky moc nenosí a do budoucna bude ještě hůř. Vše to završila představa procházení starých placek a přehrávání na nové, abych o nějaká data vlivem stárnutí materiálu nepřišel. No fuj!

# Flashky, paměťové karty

Abych pravdu řekl, o flash pamětních jsem popravdě jako o trvalém úložišti dat nikdy příliš nepřemýšlel. Minimálně od doby, kdy jsem četl, že stačí relativně malý elektromagnetický puls a data jsou v pánu. Na přenesení prezentace do školy dobrý, ale 18 let svého života zachyceného na fotkách jim prostě nesvěřím.

# A co další disk?

Hodit data na externí disk se mi líbilo už od začátku. Některé zálohy jsem tak již měl řešené a osvědčilo se mi to. Vím že disky mají svou životnost (hlavně co se pohyblivých částí týče), ale dostat data z rozbitého disku je dle mého jednodušší než z odporoučené flashky. Nicméně to hledání správného drátu v šuplíku, nutnost jednou za čas disk zkontrolovat a možnost, že si ho některý člen mě rodiny vezme a zálohy přehraje filmy mě přiměla hledat dál.

# Disk na síti či rovnou vlastní mráček?

NAS (network attached disc) není mezi běžnými uživateli tak rozšířený. Rozdíl mezi ním a cloudem (který asi většina bude znát) je v tom, že NAS většinou budete mít doma. Máte tak maximální kontrolu nad tím, kdo má k datům přístup a co se na serveru děje. Rozhodně něco pro paranoika jako jsem já.

Doma se mi poflakoval jeden starší počítač, který jsem ukořistil při školním přechodu na lepší HW. Určitě si umíte představit, jak starý byl, když se ho i škola zbavovala :). Nicméně pro začátek by určité stačil. Povzbuzen pocitem, že budu hrozný geek jsem se pustil do stavby. Posbíral jsem po domě nevyužité disky, ramky a celé to sestavil do relativně funkční sestavy. Protože se mi hodně líbila představa vlastního cloudu, začal jsem hledat software jako alternativu k Google Drive, který jsem do té doby používal. Co mě ale překvapilo byl celkem omezený výběr open source alternativ.

Většina byla běžící na webovém serveru, což se mi vůbec nelíbilo. Apache je občas úzké hrdlo i webovým stránkám. Jako první jsem narazil na [ownCloud](https://owncloud.org). Instalace byla jednoduchá, funkce vyhovující (dokonce má vlastní [Andoidí aplikaci](https://play.google.com/store/apps/details?id=com.owncloud.android&amp;hl=cs)) a vše vypadalo, že jsem u konce hledání. Zkusil jsem prostor přidělit kamarádovi a začal testovat sdílení souborů a pokročilejší funkce. Už druhy den jámě ale narazili na podivný problém. Sdílení souborů občas fungovalo jen chvíli a sem tam zmizel dokonce celý soubor. Uznávám, že mě to celkem vyděsilo. Představa že bych tímto způsobem měl přijít o zálohy se mi ani trochu nelíbil. Uznávám, že to pravděpodobně bylo zapříčiněno špatným nastavením, nicméně jsem nepřišel na to jak problém vyřešit. OwnCloud jsem tedy uložil k ledu.

[Pydio](https://pyd.io) jsem zavrhl bez testování kvůli rané fázi vývoje. [Seafile](https://www.seafile.com/en/home/) nenabízí v free verzi některé požadované funkce. [Cozy](https://cozy.io/en/), který se mi původně hodně líbil, se mi nezdařil nainstalovat. Navíc se mi nelíbí že soubory ukládá do databáze.

Při hledání jsem narazil i na nástroje pro synchronizaci souborů mezi více zařízeními - [BitTorrent Sync](https://www.getsync.com), [SyncThing](https://syncthing.net) a další. Netestoval jsem je, protože pro zálohování jsem chtěl jeden centrální server. Opravdu nepotřebuji mít stovky GB fotek nasdileno do mobilu.

## Hotové vs. podomácku vytvořené řešení

Během testování software mi odešel jeden disk a já si plně uvědomil, že kromě software jsem limitován i HW. Problém je, že jako student mám celkem malý rozpočet. Počítač, který by odpovídal požadavkům stál okolo osmi tisíc. Disky by stály dalších pět až deset tisíc (podle počtu). Suma sumárum trochu mimo mé možnosti. Za pár let bych je navíc musel vyměnit.

Zkusil jsem se poohlédnout po hotových řešeních. Z velkých hráčů na trhu bych jmenoval QNAP, WD a Synology. Líbilo se mi řešení od WD -  disky v ceně, vlastní aplikace pro android, dostatek funkcí, pěkná krabička (ano i to je hledisko :D).

Mým problémem je, že když už něco kupuji, snažím se, aby věc uměla něco nad rámec mých požadavků. Člověk se tím vyhne tomu, že zrovna ta funkce, o které si při koupi říkal, že ji rozhodně nikdy potřebovat nebude, chybí. U levnějších řešení jde vlastně o disky doplněné nějakým uzavřeným balast OS. Což mi vadí asi nejvíc. Chybí mi volnost doinstalovat si co budu chtít, mít plnou kontrolu nad tím, kam se do odesílá.

# Přicházejí mračna

Po výtkách k uzavřeným systémům hotových NAS řešení může moje rozhodutí působit trochu divně. Jelikož jsem s mávnutím ruky odmítnul téměř veškerá nabízená řešení a ofrňoval, zbyla jen hotová cloudová řešení velkých hráčů. Velkých proto, že mají servery po celém světě a je větší pravděpodobnost, že bude rychlost nahrávání a stahování vyšší.

## Microsoft OneCloud

První padl los na řešení od Microsoftu. Popravdě jsem provedl jen povrchní srovnání a Microsoft za stejnou cenu nabízel navíc Microsoft Office 365. Celkem mě unavovalo neustále řešit problémy nekompatibility s OpenOffice ve škole. Navíc mi přišlo jako dobrý nápad necpat všechna má osobní data Googlu do chřtánu - mám od něj prohlížeč, vyhledávač, mail a OS v mobilu.

Až na hrozné UI se vše zdálo OK. Oproti Googlu má Microsoft hodně co dohánět hlavně po stránce použitelnosti. Brzy jsem ale narazil na problém. Nejde sdílet soubory s někým, kdo nemá Microsoft účet. Tím se pro mě cloud stal nepoužitelný.

## Google GDrive

Google Drive používám už nějaký ten pátek na školní zápisky a sdílení souborů po internetu celkově. Byl jsem spokojený, takže po fiasku u Microsoftu šlo o druhého adepta.

I zde se ale brzy dostavily problémy. Desktopová aplikace je super na nahrávání obrázků a malých souborů. Rychlost se ale rapidně snižuje s velikostí souborů. A protože mou hlavní motivací pro tohle vše byla záloha 100gb rodinných fotek, je to celkem problém. Už přes dva týdny se snažím nahrát zálohy, ani jeden je stále nenahrál.

Hledání pokračuje...