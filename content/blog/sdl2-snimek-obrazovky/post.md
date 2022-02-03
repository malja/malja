---
title: 'SDL2: Snímek obrazovky'
author: "Jan Malčák"
headline: 'Jak zachytit to, co se děje v okně generované knihovnou SDL2?'
date: '2014-03-19T20:57:00+02:00'
keywords: ["SDL", "screenshot", "png", "bmp", "sdl_surface", "sdl_texture", "img_savepng"]
tags: ["programování", "tutoriál", "cpp"]
readingTime: 1
---

SDL s sebou ve druhé verzi přinesl i změnu vykreslování na obrazovku. Místo v RAM uložených [SDL_Surface](https://wiki.libsdl.org/SDL_Surface) je v SDL2 použita [SDL_Texture](https://wiki.libsdl.org/SDL_Texture) uložená na video RAM, kde je plně v jurisdikci GPU. Krom citelných změn na rychlost vykreslování se také změnil způsob, jakým lze zachytit snímek obrazovky.

Při použití textur se ``SDL_Surface`` okna neaktualizuje, pokud bychom použili dřívější způsob, dostali bychom prázdný snímek. Bohužel standardní funkce [SDL_SaveBMP](https://wiki.libsdl.org/SDL_SaveBMP) (ani její nedokumentovaná obdoba v rozšíření ``SDL_image`` - ``IMG_SavePNG``) nepodporuje uložení ``SDL_Texture``. Je proto nejprve nutná konverze z ``SDL_Texture`` na ``SDL_Surface``. Teprve pak je možné snímek obrazovky uložit.

<script src="https://gist.github.com/malja/2193bd656fe50c203f264ce554919976.js"></script>

# Použité funkce

- [SDL_RenderGetViewport](https://wiki.libsdl.org/SDL_RenderGetViewport)
- [SDL_CreateRGBSurface](https://wiki.libsdl.org/SDL_CreateRGBSurface)
- [SDL_GetError](https://wiki.libsdl.org/SDL_GetError)
- [SDL_RenderReadPixels](https://wiki.libsdl.org/SDL_RenderReadPixels)
- [SDL_FreeSurface](https://wiki.libsdl.org/SDL_FreeSurface)
