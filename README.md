---
obsidianUIMode: preview
banner: "[[z_media/Header.jpg]]"
banner-x: 48
banner-y: 47
banner-height: 540
content-start: 76
banner-fade: -180
banner-radius: 21
pixel-banner-flag-color: black
---

> [!cards|4]
> **MUNDO: ARCOS**
> [![[Banner_Arcos.png]]](ARCOS/ARCOS.md)
> 
> **PERSONAJES**
> [![[Header_People.jpg]]](Personajes/Bóveda.base)
>
> **GREMIOS**
> [![[m2.png\|sban htiny ctr]]](NOTES.md)
> 
> **MAIN HEADING 4**
> [![[m4.png\|sban htiny ctr]]](NOTES.md)
>



> [!world]- THE FINER DETAILS OF YOUR WORLD
> ```datacards 
> TABLE cover FROM #home
> SORT file.name asc
> 
> // Settings 
> preset: dense 
> columns: 5
> imageProperty: cover
> cardSpacing: 4
> imageHeight: 30px
> ```


<div class="homepage">
<hr>
</div>

> [!infobox]
>```calendarium
>```
> **LATEST CHAPTERS:**
>```datacards 
>TABLE cover, date, description FROM #story
>SORT file.ctime desc
>limit 1
>
>// Settings 
>preset: square 
>columns: 1 
>imageProperty: cover
>imageWidth: 50px
>```

> [!home]+ Personajes editados RECIENTEMENTE
> ```dataview
> table 
>  "<img src='" + thumbnail + "' width='60' style='border-radius:4px;box-shadow:0 0 3px rgba(255, 255, 255, 0.4);' />" as "IMAGE",
>   status, 
>   role, 
>   district, 
>   territory, 
>   faction, 
>   religion,
>   "<span style='font-size: 0.85em; color: #bbb;'>" + date(file.mtime) + "</span>" as "TIME/DATE"
> from "Personajes"
> where contains(tags, "character")
> sort file.mtime desc
> limit 2
> ```

> [!news]+ INFORMATION
> #### Notes:
> - Main Headings can have more than 4 columns. Be sure to note the number in the [!cards] property.
> - Sub-Headings, created with the datacards plug-in can have up to six columns. Datacards layouts can be changed by altering the "preset" in the markdown settings of a datacard. Available layouts are: **grid, portrait, square compact, dense**
> - Column to the right side of the screen (Calendar on home page and portraits on character pages) are created with "> [!infobox]"
> - The colored links are created using the Supercharged Links plug-in. Then styled using the Style Settings plug-in.
> - Inside the Style Settings plug-in settings > ITS Theme Settings, you can change the colors of the theme.
> - The calendar is created using the Calendarium plug-in.
> - The timeline is created using the Chronos Timeline plug-in.
> - Beside the callout boxes use "+" to always keep the box open, or "-" to have to click it open.
>   #### Visit @pratt_design on youtube for walk-throughs and tutorials.



> [!note]- TERRITORIES
> ```datacards
> TABLE cover, region, leader, population FROM #territory
> SORT name DESC
> 
> // Settings
> preset: grid
> columns: 6
> imageProperty: cover
> cardSpacing: 4
> ```

<br>

```dataview
 TABLE WITHOUT ID
   link(file.path, file.folder + " / " + file.name) AS "Last Modified",
   file.mtime AS "Date"
 FROM "/"
 WHERE file.mtime >= date(today) - dur(30 days)
 AND file.name != this.file.name
     AND !contains(file.path, "z_Assets")
    AND !contains(file.path, "Inline Scripts")
     AND !contains(file.path, "z_Templates")
     AND !contains(file.path, "daily notes")
     AND !contains(file.path, "BRAT")
 SORT file.mtime DESC
 LIMIT 10
```

---

2025, © **Prattdesign.ca**
