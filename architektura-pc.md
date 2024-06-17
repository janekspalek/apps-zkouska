# Architektura počítačů

- Počítač se skládá z menších částí, jejichž propojením vzniká funkční celek

## John Von Neumann

- Základní koncepci definoval v roce 1945 John Von Neumann - `EDVAC`
  - Struktura PC je nezávislá na typu řešené úlohy
  - Data jsou také v paměti, pro instrukce i data lze přistupovat jednotným způsobem
  - Paměť je rozdělena do buněk stejné velikosti, jejich pořadová čísla se využívají jako adresy
  - Následující krok počítače je závislý na tom předchozím
  - Program je tvořen posloupností instrukcí, ty jsou vykonávány sekvenčně
  - Změna pořadí instrukcí se provede podmíněným či nepodmíněným skokem
  - Pro reprezentaci dat se používá dvojková číselná soustava (binární)
- Dnešní počítače vychází z tohoto původního modelu
- Původní schéma má samostatně `řadič` a `ALU`
- Dnešní PC mají řadič a ALU v jednom obvodu - `CPU`
- Počítač musí mít procesor, paměť a periférie - bez nich by PC nebyl funkční

**Výhody:**
1. Rozdělení paměti pro program a data určuje programátor
2. Jedna sběrnice - jednodušší a levnější výroba
3. Přístup do paměti je pro data i program stejným způsobem

**Nevýhody:**
1. Společné uložení programu i dat může mít za následek přepsání vlastního programu
2. Jediná sběrnice tvoří úzké místo

![nojmanpico](https://github.com/janekspalek/apps-zkouska/assets/98762780/6430e43f-127f-4763-81bd-8b4ffa2853d0)



## Hardvardská architektura

- Několik let po Von Neumannovi přišli odborníci z Hardvardské univerzity
- Vyřešily pár nedostatků - rozdělily paměť pro **data** a **program**
  
**Výhody:**
1. Program nemůže přepsat sám sebe
2. Paměti mohou být vyrobeny odlišnými technologiemi
3. Dvě sběrnice - mohou naráz přistupovat k datům i k programu

**Nevýhody:**
1. Dvě sběrnice - dražší a komplikovanější výroba
2. Nevyužitou část pro program nelze využít pro data a naopak

![image](https://github.com/janekspalek/apps/assets/98762780/38d80844-52c4-47c3-a836-1ee9e438f184)


## Princip fungování počítače

- Procesor je sekvenční obvod - instrukce jsou vykonávány sekvenčně
- Paměť má i samotný CPU - ve formě registrů
- Jedním z těchto registrů je `IP (Instruction Pointer)` - ukazatel do paměti na instrukci, která má být provedena
- Má-li CPU vykonat instrukci, získá si ji pomocí IP registru z paměti. Po provedení zvýší IP o délku právě provedené instrukce a celý cyklus se opakuje
- Tyto základní koncepty ale neumožňovaly paralelní zpracování dat
