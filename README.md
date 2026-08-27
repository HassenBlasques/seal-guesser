# Seal Guesser v4 – Quality Rules

Aktualizace založená na reálném testování předchozí verze.

## Co řeší tato verze
Předchozí test odhalil tři typy vad:
1. mrtvý tuleň,
2. tuleň jako malá tečka v dálce,
3. fotografie jiného živočicha (pták).

Proto je v4 přísnější.

## Nová pravidla
- research-grade iNaturalist observations
- přesná shoda taxonu pozorování s konkrétním latinským druhem
- pouze fotografie s CC0 / CC BY / CC BY-SA
- pouze záznamy explicitně označené `Alive`
- přednost pro záznamy explicitně označené `Adult`
- explicitně Juvenile jsou vyřazeni
- textový filtr pro pup / baby / juvenile / carcass / dead / skull / skeleton / taxiderm
- minimální rozlišení fotografie, pokud jsou rozměry v metadatech dostupné
- výsledky se řadí tak, aby měly přednost Adult a záznamy s vyšším počtem identifikací
- náhodný snímek se bere jen z lépe hodnocené poloviny fotografického fondu
- použité fotografie se neopakují, dokud se fond nevyčerpá

## Tlačítko „Nevhodná fotka“
Pokud se přesto objeví:
- zvíře příliš daleko,
- jiný objekt / jiný živočich,
- nevhodná kompozice,
- jinak neférová fotografie,

klikni `Nevhodná fotka`.

Fotografie se:
- nezapočítá do skóre,
- lokálně uloží na blacklist,
- nahradí jinou fotografií stejného druhu,
- v tomto prohlížeči se už znovu nepoužije.

## Čepcol hřebenatý
Poznávací text byl zpřesněn: nápadný nafukovací „čepec“ je typický hlavně pro dospělého samce.
Samice a mladší jedinci mohou být bez nápadného čepce.

## Aktualizace GitHub Pages
Nahraď v kořeni repozitáře soubor `index.html` novým a commitni změnu.
