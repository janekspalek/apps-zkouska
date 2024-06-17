# Čítače

- Je to registr o N bitech
- **Čítá vnější události**
- Lze nastavit, zdali provádí inkrementaci při **náběžné** nebo **sestupné** hraně vnějšího signálu
- Počáteční hodnota se nastavuje programově

![citac](https://github.com/janekspalek/apps-zkouska/assets/98762780/c801a04a-0275-4cf3-84b0-9f8792212391)

# Časovač

- Velmi podobný jak čítač
- Není inkrementován vnějším signálem, ale přímo **vnitřním hodinovým signálem** používaného pro řízení samotného mikropočítače
- Také lze nastavit počáteční hodnotu

![casovac](https://github.com/janekspalek/apps-zkouska/assets/98762780/f439ce8e-a1cb-4fee-8c39-ab7b87ffb873)

# A/D převodníky

- Do mikropočítače většinou vstupují veličiny `analogově` - **napětím, proudem...**
- Pro zpracování ale potřebujeme jejich digitální podobu
- Tyto převodníky převádí analogové veličiny (nejčastěji napětí) na digitální data

## Komparační A/D převodníky

- Fungují na principu porovnávání `vstupního napětí` s `referenční hodnotou`
- S větším počtem komparátorů roste i jeho rozlišovací schopnost
- Jsou velmi **rychlé** ale **drahé** a složité při stoupající přesnosti

## A/D převodníky s D/A převodem

### Sledovací převodníky

- Mění referenční hodnotu o jeden krok nahoru nebo dolů
- Není to ale moc vhodné pro skokové signály
- Používají se pro **pomalu měnící** se hodnoty, jako například `teplota`, `vlhkost` apod.

### Aproximační převodníky

- Princip binárního vyhledávacího stromu
- Referenční hodnota je na začátku v polovině maximálního napětí
- Pokud je naměřená hodnota vyšší, nastaví se na polovinu vyšší poloviny a naopak

# D/A převodníky

- Signál z PC může být buď `0` nebo `1`

# Speciální periferie

- Pro TV existují obvody pro zobrazení informací `On screen`
- Řízení dobíjení baterií
- Vysílače a příjímače IR signálu
- USB
