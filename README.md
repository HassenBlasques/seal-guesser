# Seal Guesser v4.1 — Multi-source + silent auto-skip

## Změny podle testování
- Pokud pro vybraný druh není použitelná fotografie, uživatel neuvidí chybovou hlášku ani možnosti odpovědí.
- Aplikace takový vzorek automaticky přeskočí a ve stejném kole zkusí jiný druh.
- Pokud selže samotné načtení obrázku, obrázek se lokálně blacklistuje a automaticky se zkusí další.

## Zdroje fotografií
1. **iNaturalist** — první volba:
   - research grade
   - přesná druhová shoda
   - explicitně Alive
   - přednost Adult
   - pouze single-photo observations, aby se minimalizovalo riziko, že se vybere vedlejší fotografie (např. pták)
   - CC0 / CC BY / CC BY-SA

2. **GBIF** — fallback pro druhy s malým fondem:
   - StillImage occurrence records
   - přesná druhová shoda
   - přednost záznamům mimo iNaturalist, aby zdroj skutečně rozšířil databázi
   - CC0 / CC BY / CC BY-SA
   - jeden obrázek na occurrence

3. **Wikipedia** — poslední fallback:
   - titulní druhová fotografie
   - použije se jen pokud je fond stále velmi malý

## Nevhodná fotka
Tlačítko „Nevhodná fotka“:
- nezapočítá kolo,
- obrázek uloží na lokální blacklist,
- zkusí jinou fotografii stejného druhu,
- pokud už žádná není, automaticky přejde na jiný druh.

## GitHub Pages update
Nahraď `index.html` v kořeni repozitáře novým souborem a commitni změnu.
