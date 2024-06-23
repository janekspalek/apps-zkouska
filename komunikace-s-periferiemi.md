# Komunikace s perifériemi

## Sběrnice

- Slouží pro přenos dat mezi procesorem a ostatními částmi PC
- Slouží také pro přenos dát přímo v procesoru a mezi počítačem a okolím
- Všechny bloky počítače jsou paralelně propojeny souborem vodičů společnou sběrnicí - `bus`
- Bloky počítače jsou schopny data jak **přijímat, tak i předávat**
- **Musí se vždy určit, který blok bude snímat a který přijímat**
- Téměř **vždy** se tohoto proceso účastní také **mikroprocesor**
- Sběrnice dělíme na:
  - `Adresové`
  - `Datové`
  - `Řídící`
   
### 1. Adresová sběrnice

- Pokud chce mikroprocesor data číst nebo zapisovat, musí sdělit **konkrétní místo**
- Toto místo je identifikováno `adresou`, zdrojem této informace je mikroprocesor
- Počet bitů sběrnice, neboli počet vodičů odpovídá počtu bitů adresy
- Příklad: šestnáctibitová sběrnice 2<sup>16</sup> = 65536 adres

### 2. Řídící sběrnice

- Souhrn signálů aktivních v různých časových okamžicích
- Určuje, co se má právě dít
- Nejčastější signály:
  - `RESET` - obsahuje jej každý mikroprocesor, tento signál uvede mikroprocesor do jeho výchozího stavu
  - `Memory Read` _(MR)_ - čtení z pamětí
  - `Memory Write` _(MW)_ - zápis do pamětí
  - `Ready` - připravenost obvodu

### 3. Datová sběrnice

- Slouží pro přenos všech dat v počítačí (například přenos dat z paměti do mikroprocesoru)
- V jednom okamžiku může být aktivní pouze jeden vysílač _(budič sběrnice)_
- Při nedodržení této podmínky by mohlo dojít ke zničení obvodů
- Proto je tedy nutné vybavit bloky obvody, které umožní odpojení tohoto bloku od sběrnice - `Třístavové budiče sběrnice`
- Jeden z parametrů datové sběrnice je její šířka _(počet bitů)_ - určuje, kolik bitů lze přenést najednou
- Jednou z možností jak ušetřit vodiče je použití `multiplexování sběrnic`
- Toto spočívá ve vedení signálů adresové i datové sběrnice ve společných vodičích - jednotlivé signály jsou vedeny v různou dobu
- Sběrnice se dále dělí na:
  - `Vnitřní sběrnice mikroprocesoru`
  - `Vnitřní sběrnice počítače` - propojuje mikroprocesor s ostatními částmi PC
  - `Vnější sběrnice počítače` - pro systémy sestavených z několika PC
 
## Technika V/V Bran

> Vstupně/výstupní brána
- Obvod, který zprostředkovává přenos dat mezi sběrnicí počítače a periferiemi
- Máme zde možnost použití brány s/bez paměti

### 1. Nepodmíněný vstup/výstup
- Procesor vyšle signál `RD`, čímž příkáže vstupnímu zařízení poslat data do procesoru
- V případě výstupu procesor vyšle signál `WR` a současně vyšle i data
- **Očekává se, že je zařízení vždy připraveno**

![nepodmineny](https://github.com/janekspalek/apps-zkouska/assets/98762780/9415351b-017b-46dd-b588-26059648565c)

  
### 2. Podmíněný neúplný vstup/výstup
- **Vždy se čeká se na dostupnost procesoru**
- Vstupní zařízení pošle signál, který nastaví `indikátor Q` na `1`
- Jakmile má procesor čas, tento signál přečte, a data si od zařízení vyžádá pomocí signálu `RD`
- **Zároveň vynuluje indikátor Q**
- Při zapisování lze říct, že indikátor Q slouží, že procesor může zaslat další příkazy
- **Periferie musí být opět stále na pozoru**

![podmineny](https://github.com/janekspalek/apps-zkouska/assets/98762780/d62000be-69dc-42ab-b1b2-4d27ccbc64d7)


### 3. Podmíněný úplný vstup/výstup
- Obsahuje navíc `vyrovnávací pamět` _(registr)_ - **uchovává data mezi procesorem a zařízením**
- `Q` značí, zdali se v tomto registru nachází nějaká data či nikoliv
- V případě čtení pošle periferie data do tohoto registru, a zároveň nastaví indikátor `Q` na hodnotu `1`
- **Procesor poté, až bude mít čas, tento signál přečte**
- Pokud má Q hodnotu 1, procesor si data vyžádá pomocí signálu `RD` a zároveň `Q` _vynuluje_
- V případě zápisu dat procesor svá data zašle na _registr_ a nastaví `Q` na hodnotu `1`
- **Poté periferie, až bude mít čas, tento signál přečte**
- Pokud má Q hodnotu 1, periferie si vyžádá data z _registru_ a indikátor Q _vynuluje_

![podmineny+buffer](https://github.com/janekspalek/apps-zkouska/assets/98762780/6e558e85-7d1e-482d-9daf-3a9b6c7dff35)


## Programové řízení komunikace

- Využívají se zde instrukce pro `vstup/výstup` ve spojení s instrukcemi pro `testování logických proměnných` a instrukcí `skoku`
- Procesor stále testuje `signální bit`
- Pokud je tento bit nastaven, procesor pomocí podmíněného skoku přeskočí na rutinu, kde tato data zpracuje a pak se vrací zpět
- Procesor bit kontroluje opakovaně - může tak rychle reagovat na změny stavu periferií

## Řízení komunikace pomocí přerušení

- Jakmile periferie požaduje od počítače `obsluhu` _(např. přenos dat)_, aktivuje `přerušovací signál`
- Po zjištění žádosti o obsluhu procesor přeruší aktuálně běžící program a přejde do `obslužného programu`
- Po jeho dokončení se procesor **vrátí zpět**
- U tohoto řízení nastává problém při obsluze více periférií naráz

## Přímý přístup do paměti - DMA

> Direct Memory Access
- Funguje na principu přesunu informací **bez účasti procesoru** mezi vyrovnávacím registrem a hlavní pamětí
- Procesor na dobu přesunu přepně všechny budiče sběrnic do `třetího stavu`
- Sběrnice ale nemá kdo řídit - k tomu existuje `blok DMA`, který je schopný **generovat adresu** a určovat okamžiky přesunu dat
- Procesor nejprve naprogramuje DMA řadič s informacemi, **odkud brát data**, **kam je zapisovat** a **kolik dat přenést**
- Podle hodinových fází se s procesorem střídá v přístupu do paměti
- DMA řadič generuje adresy pro čtení/zápis dat
- Po každém přesunu navyšuje adresu pro další, a snižuje čítač přesunů o jedničku
- Tento cyklus se opakuje, dokud není čítač na hodnotě 0
- Přímý přístup do paměti se pak realizuje během hlavní činnosti procesoru
- `Čítač přesunů` - počet slov, která mají být ještě přesunuta
- `Registr dat` - obsahuje slovo, které má být přesunuto
- `Registr adres` - obsahuje adresu hlavní paměti, do/z které mají být data přesunuta

![dma](https://github.com/janekspalek/apps-zkouska/assets/98762780/68eb3710-15f6-4cfe-804a-aef8cc26b844)

<img width="500" alt="image" src="https://github.com/janekspalek/apps-zkouska/assets/98762780/467f52d1-b7b2-44f9-8fd2-2ba3e0800744">



