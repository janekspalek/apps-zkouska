# 1. Magnetické paměti

## Princip ukládání dat

- Záznamové médium má tvar **kruhové** desky _(disk, disketa)_ nebo **dlouhé pásky** _(magnetická páska)_
- Médium je pokryto `magnetickou vrstvou` a pohybuje se konstantní rychlostí
- Médium je vytvořeno z velkého množství miniaturních `magnetických domén`
- Tyto domény mohou být zmagnetizovány jedním ze dvou směrů
- Tyto paměti využívají `hlavu`, ke čtení nebo zápisu dat
- Při přivedení proudu do cívky v zápisové hlavě se vytvoří **magnetické pole**
- Pokud se změní směr proudu, změní se i směr magnetického pole - můžeme měnit orientaci magnetických domén na plotně
- Když hlavička čte z domén, změna v polaritě znamená hodnotu 1, pokud zůstala stejná, tak 0
- Místa, kde dochází ke změně polarity, se nazývají _magnetické reverzace_

## HDD (pevný disk)

> Hard Disk Drive

- Uzavřená jednotka v PC, slouží k **trvalému uchování dat** (data zůstanou uchována i po vypnutí napájení)
- HDD obsahuje pevné plotny diskového tvaru, které jsou většinou vyrobeny ze slitiny hliníku nebo skla
- Plotny na rozdíl od disket nelze ohýbat, proto název **pevný disk**

### Jednotlivé části

1. Plotny disku
2. Hlavy pro čtení a zápis
3. Pohon hlav
4. Pohon ploten disků
5. Řídící deska
6. Vzduchový filtr

### Geometrie

- Je to uspořádání prostoru na disku
- Počet `hlav`, `cylindrů` a `stop`
- Data jsou na disk ukládána v bytech, byty jsou uspořádány do skupin po 512 - neboli `sektorů`
- Sektor je nejmenší jednotka dat, na kterou lze zapsat nebo z ní číst
- Sektory jsou uspořádány do `stop`
- Stopy jsou uspořádány do skupin zvaných `cylindry` (válce)
- Disk má nejméně dva povrchy
- **Stopy**
  - Každá strana každé plotny je rozdělena na soustředné kružnice
  - Při jedné poloze hlav je na každém povrchu přístupná jedna stopa
- **Cylindry**
  - Pevné disky mají většinou více disků, umístěných nad sebou
  - Každý disk má dvě strany, na které je možno ukládat data
  - Diskové hlavy nemohou být vystavovány nezávisle - Souhrn stop v jedné poloze hlav se nazývá cylindr

![HDD](https://github.com/janekspalek/apps/assets/98762780/43070dad-75c8-4e97-bc97-0711593b585b)

- **Sektory**
  - Jedna stopa je moc velká - proto se rozděluje do několika očíslovaných částí zvaných `sektory`
  - Velikost se určí při formátování disku _(standardně 512 B)_
  - Na začátku každého sektoru je tzv. _hlavička_, obsahující číslo sektoru 
  - Na konci sektoru je _kontrolní součet_
  - Pro čtení se hlava přemístí nad požadovanou stopu
  - Potom se čeká, až je disk natočen tak, aby byl daný sektor pod hlavou
  - Dále probíhá samotné čtení
  - Nejrychleji se čtou soubory, umístěné na jedné stopě, nebo nad sebou (na jednom cylindru)
 
![Sektory](https://github.com/janekspalek/apps/assets/98762780/73d75218-1085-45e6-871a-d7944d0213c6)
 
### Kolmé vs. podélné rozložení domén

- Kolmé umožňuje větší hustotu dat - **větší kapacitu**
- Podélné je typické pro starší HDD

![Kolmé](https://cdn.discordapp.com/attachments/1213418988462407722/1249684711161462795/image.png?ex=66683315&is=6666e195&hm=6d527afd4921c59ad2c463ec1b5fd999cad867bc55d0fa93c36dc574c65e1f3d&)
![Podélné](https://cdn.discordapp.com/attachments/1213418988462407722/1249684934038388829/image.png?ex=6668334a&is=6666e1ca&hm=4c5d959504bc11f6c9e4bf49c0e34a907f7baf9e077f5a3a56903ab6b679bd1c&)


# Optické paměti

## Princip ukládání dat

- Data jsou na povrchu zaznamenána do spirálové stopy, ty jsou dále rozděleny do sektorů
- Záznam se provádí v podobě prohlubní a ostrůvků - `pitů` a `polí`
- Jedničky jsou na médiu zapsané jako **přechod mezi pitem a polem**, příp. naopak
- Datové nuly se nezapisují
- Přechody jsou obdobou **magnetických reverzací** u magnetických médií
- Při čtení dopadá laserový paprsek na médium, pokud narazí na ostrůvek, laser se odrazí do senzoru, který signál rozpozná
- `CD-WORM` _(Write Once Read Many times)_ neboli CD-R byly technologickým pokrokem, uživatel na ně mohl zapsat, ale pouze jen jednou
- Zápis se provádí vypalováním pitů do kovové vrstvy 
- Další stupeň jsou přepisovatelné disky `CD-RW`, které lze opakovaně přepisovat i číst

![CD](https://www.phy.cuhk.edu.hk/phyworld/articles/cdrom/cdrom_work_e.gif)

## CD-ROM

> Compact Disk Read Only Memory

- Média, která lze po zapsání dat pouze číst
- Označují se takhle i **mechaniky**, které slouží pro práci s těmito médii
- Další formáty jsou CD-R _(CD - Recordable)_, CD-RW _(CD - ReWritable)_
- Kvůli spirálovitému tvaru stop se musí měnit rychlost otáčení média
- Číst se začíná ve vnitřních stopách k vnějším, rychlost čtení musí být konstantní

## DVD

> Digital Versitale Disc

- Vysokokapacitní CD
- V DVD-ROM mechanikách lze číst i CD-ROM
- Zvýšenou kapacitu mají především díky **zvýšení frekvence laseru**
- Mohou být oboustranné - ještě vyšší kapacita
