# Seal Guesser v4.3 — persistent blacklist fix

Oprava podle testu, kdy se fotografie označená jako `Nevhodná fotka` v pozdější hře objevila znovu.

## Proč se to mohlo stát
Starší verze ukládala na blacklist pouze interní ID konkrétního záznamu.

Stejná fotografie ale může být dostupná:
- přes jiný GBIF occurrence record,
- přes jinou velikost/URL náhledu,
- případně přes jiný datový zdroj.

Pak měla jiné ID a aplikace ji považovala za nový obrázek.

## V4.3
Při stisku `Nevhodná fotka` se nyní ukládá:
1. ID záznamu fotografie,
2. normalizovaný identifikátor samotného obrázku / URL.

Při výběru další fotografie se kontrolují oba.

Navíc v4.3 importuje starý blacklist z v4.1/v4.2, takže dříve odmítnutá ID nezapomene.

### iNaturalist
U URL iNaturalist se blacklist váže přímo na stabilní photo ID, takže `large.jpg`, `medium.jpg` apod. jsou považovány za tutéž fotografii.

### Wikimedia
Různé velikosti thumbnailu se normalizují, aby se tentýž snímek nevrátil jen v jiném rozlišení.

## Odkaz na zdroj
`Zdroj fotografie` se záměrně zobrazuje až po odpovědi. Odkaz nebo URL mohou obsahovat název taxonu a před odpovědí by mohly prozradit správný druh.

## GitHub Pages
Nahraď stávající `index.html` novým a commitni změnu.
