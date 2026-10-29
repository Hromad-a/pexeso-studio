# Pexeso studio

Jednosouborový nástroj (`index.html`) pro přípravu tiskového pexesa, kde jeden kus páru je obrázek a druhý text uprostřed dlaždice. Žádný build krok, žádné závislosti kromě Google Fonts.

Online verze: https://hromad-a.github.io/pexeso-studio/

## Co umí

- čtvercové dlaždice s nastavitelnou stranou v mm a spadávkou (výchozí 3 mm)
- ořezové značky u každé dlaždice
- A4 na výšku i na šířku, duplex s otáčením přes dlouhou nebo krátkou hranu (rub se zrcadlí, aby seděl na líc)
- korekce posunu rubu v mm pro tiskárny, které rub při duplexu posouvají
- jeden společný rub pro obrázkové dlaždice a jeden pro textové
- měřítko, otočení a posun každého obrázku (tažením myší, kolečkem, posuvníky, šipkami)
- výběr fontu z Google Fonts a vlastní velikost textu (u každého páru jde přepsat)
- export PDF ve 300 dpi (obsah dlaždic jako obrázek přesně v 300 dpi, ořezové značky vektorově)
- víc projektů v jednom prohlížeči: seznam posledních projektů, otevření, přejmenování, duplikace, smazání
- vše se ukládá automaticky hned po každé změně do prohlížeče (IndexedDB)
- ruční uložení do souboru JSON a průběžné ukládání do propojeného souboru (Chrome, Edge)

## Použití

Otevři `index.html` v prohlížeči nebo online verzi. Pro Google Fonty je potřeba internet. Pro průběžné ukládání přímo do souboru na disku použij Chrome nebo Edge (tlačítko Propojit soubor). Projekty v prohlížeči jsou vázané na konkrétní prohlížeč a adresu stránky, pro zálohu nebo přenos jinam použij Uložit do souboru. Otevřený soubor JSON se vždy založí jako nový projekt, takže nic nepřepíše.

## Poznámky k tisku

- Tiskni ve skutečné velikosti (100 %), bez přizpůsobení stránce.
- PDF obsahuje obrázky ve 300 dpi v RGB. Pokud tiskárna vyžaduje CMYK nebo PDF/X, je potřeba PDF převést v dalším programu.
- Před velkým nákladem vytiskni jeden list oboustranně a zkontroluj, že líc a rub sedí. Když tiskárna rub posouvá, změř o kolik a zadej to do Korekce rubu.
- Projekt v souboru JSON obsahuje i obrázky, soubor proto může být velký.

## Ověření sesazení líce a rubu

Exportované PDF bylo vyrenderováno v 600 dpi a polohy dlaždic na líci byly porovnány se zrcadlenými polohami na rubu. Pro A4 na výšku i na šířku a pro otáčení přes dlouhou i krátkou hranu je odchylka středů dlaždic do 0,04 mm, tedy pod velikostí jednoho pixelu při 300 dpi. Vektorové ořezové značky leží na hraně ořezu s přesností 0,01 mm.
