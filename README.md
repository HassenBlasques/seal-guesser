# Seal Guesser 3 – Large photo database

Velká databázová verze Seal Guesseru pro GitHub Pages.

## Co je nové
- 18 žijících druhů pravých tuleňů (Phocidae)
- české + anglické názvy
- až 30 různých fotografií na každý druh
- primární výběr z research-grade pozorování iNaturalist označených jako Adult
- u vzácných druhů fallback na research-grade pozorování bez explicitního označení životního stadia
- explicitně označená mláďata a mrtví jedinci jsou odfiltrováni
- jednoduchý textový filtr navíc vyřazuje záznamy popsané jako pup / juvenile / baby / carcass / dead apod.
- jedna fotografie z jednoho pozorování, aby fond obsahoval co nejvíc různých jedinců
- fotografie použité v předchozích hrách se ukládají do localStorage; hra přednostně vybírá dosud neviděné snímky
- autor / licence / zdroj se zobrazí až po odpovědi

## Licence fotografií
Aplikace požaduje pouze fotografie s licencí:
- CC0
- CC BY
- CC BY-SA

Samotná fotografie zůstává načítaná ze serveru iNaturalist / jeho obrazového úložiště.
Po odpovědi je vždy k dispozici odkaz na původní pozorování.

## Proč nejsou stovky JPEGů přímo v ZIPu
Místo pevného balíku obrázků si hra sestaví a na 7 dní zapamatuje fotografický fond pro každý druh.
Výhody:
- GitHub repo zůstává malé
- zdroj a licence zůstávají svázané s každou fotografií
- fond lze po týdnu automaticky obnovit
- stejný druh má desítky různých snímků

## Aktualizace na GitHub Pages
1. Rozbal ZIP.
2. Nahraj nový `index.html` do kořene repozitáře `seal-guesser` a nahraď starý.
3. Volitelně nahraj i tento `README.md`.
4. Commit changes.
5. Počkej, než GitHub Pages publikuje změnu.
6. Obnov stránku (případně Ctrl+F5).

## Poznámka k mláďatům
Tato verze se jim snaží vyhnout. Samostatný režim mláďat / pups lze přidat později.
