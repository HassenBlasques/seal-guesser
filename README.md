# Seal Guesser v5 — Commons feeding

Tato verze cíleně řeší druhy s malými fondy fotografií.

## Co jsme zjistili diagnostikou
Předchozí cache měla mimo jiné:
- Ross seal: 1
- Ribbon seal: 1
- Spotted seal: 1
- Caspian seal: 1
- Bearded seal: 2
- Mediterranean monk seal: 4
- Harp seal: 4
- Baikal seal: 4

## Nový zdroj: celé druhové kategorie Wikimedia Commons
V4 používala z Wikipedie jen titulní fotografii. V5 prohledává přímo `Category:<latin name>` na Wikimedia Commons.

Pro některé slabé druhy jsou navíc přidané bohaté podkategorie:
- `Erignathus barbatus in Svalbard`
- `Pusa sibirica at the Ushkan Islands`

### Filtry Commons
Automaticky se vyřazují názvy / popisy obsahující např.:
- map, range, distribution, area
- logo, stamp
- museum, specimen
- skull, skeleton, anatomy
- skin, fur
- illustration, drawing, engraving
- pup, juvenile, newborn, baby, whitecoat
- dead, death, carcass, killed, hunting

Použijí se jen soubory s povolenou licencí (CC0, CC BY, CC BY-SA nebo Public Domain) a rozumným rozlišením.

## Pořadí zdrojů
1. iNaturalist — research-grade + Alive, přednost Adult
2. Wikimedia Commons — druhové kategorie
3. GBIF
4. Wikipedia — titulní obrázek jako poslední fallback

## Deduplikace
Stejný obraz se deduplikuje podle normalizované URL, takže se nemá započítat vícekrát jen proto, že existuje v jiné velikosti nebo přes jiný záznam.

## Blacklist
Blacklist z v4.3 zůstává zachován.
Fotografie označená `Nevhodná fotka` se dál ukládá podle ID i normalizované URL.

## Aktualizace
Nahraď v GitHub repozitáři stávající `index.html`.
V5 používá nový cache namespace, takže nové fondy se sestaví automaticky; není nutné ručně mazat starou cache.

## Diagnostika po odehrání / načtení
V konzoli lze zkontrolovat lokální fondy:

```js
console.table(
  species.map(s => {
    const raw = localStorage.getItem(poolKey(s.latin));
    const pool = raw ? (JSON.parse(raw).photos || []) : [];
    return {
      Species: `${s.cs} (${s.en})`,
      Total: pool.length,
      iNaturalist: pool.filter(x => x.source === "iNaturalist").length,
      Commons: pool.filter(x => x.source === "Wikimedia Commons").length,
      GBIF: pool.filter(x => x.source === "GBIF").length,
      Wikipedia: pool.filter(x => x.source === "Wikipedia").length
    };
  })
);
```
