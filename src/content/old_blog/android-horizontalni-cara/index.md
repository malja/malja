---
title: 'Android: Horizontální čára'
author: 'Jan Malčák'
date: '2013-08-28T15:03:00+02:00'
publish_date: '28-08-2013 15:03'
keywords: ['android, horizontal line, horizontální čára, view, line, čára, xml']
tags: ["tutoriál", "android", "programování"]
showFullContent: true
readingTime: 1
---

V Androidu neexistuje (alespoň o tom nevím) žádná nativní cesta jak vytvořit horizontální čáru. Naštěstí si jde vypomoci i jinak:

```xml
<View
    android:layout_width="match_parent"
    android:layout_height="1dip"
    android:background="#000000">
```