# Paměti

## Rozdělení podle typu přístupu:

1. `RAM` _(Random Access Memory)_ - paměť s libovolným přístupem
2. `SAM` _(Serial Access Memory)_ - paměť se sériovým přístupem
3. Paměti se speciálním typem přístupu - zásobník, fronta...

## Rozdělení podle možnosti zápisu/čtení:

1. `ROM` _(Read Only Memory)_ - paměť pouze pro čtení
2. `RWM` _(Read Write Memory)_ - paměť pro čtení i zápis

## Rozdělení podle principu elementární buňky:

1. `SRAM` - statická paměť
2. `DRAM` - dynamická paměť
3. **PROM**, **EPROM**, **EEPROM**, **FLASH**

## Rozdělení podle uchování dat po odpojení napájení:

1. `Volatile` - paměť ztrácí uložená data po odpojení napájení (DRAM, SRAM)
2. `Non-Volatile` - paměť uchová data i po odpojení napájení (xxROM)

> RAMka by byla tedy Volatile RWM DRAM

## Dynamické paměti

- Data jsou zde uložena ve formě **elektrického náboje** v `kondenzátoru`
- Může být buď nabitý _(logická 1)_ nebo vybitý _(logická 0)_
- Jsou složeny s velkého počtu miniaturních kondenzátorů
- Kvůli jejich velikost je jejich kapacita velmi malá - **náboj neudrží dlouho**
- Proto je nutné je **občerstvit**
- Typy občerstvení:
  - **RAS-only** - nejjednodušší metoda
  - **CAS-before-RAS**
- Dynamické paměti zapomenou všechny informace za přibližně 10 ms
- Paměťové buňky jsou uspořádány do **čtvercové matice**
- Pro výběr buňky tedy musíme znát **sloupec** i **řádek**
- Toto se provádí pomocí **řádkového** a **sloupcového dekóderu** pro úsporu vodičů
- Adresy jdou za sebou postupně = `multiplexing`
- Každá buňka krome kondenzátoru obsahuje i `přístupový tranzistor` - slouží pro výběr kondenzátoru

![dram](https://github.com/janekspalek/apps-zkouska/assets/98762780/e75021ff-a9b5-4aa0-a5b8-04fd9861f72a)

## Statické paměti

- Zde je informace uložena pomocí stavu `klopného obvodu` - 4-6 tranzistorů
- Buňky jsou místo 3D matice upořádány pouze do `2D mřížky`
- Jeden řádek = jedno **datové slovo** _(word)_
- Adresy řádků se musí poskytovat jako jedna informace - chybí zde multiplexing
- Je zapotřebí více pinů - SRAM čipy jsou větší než DRAM
- Vnitřní adresování je ale jednodušší - jsou rychlejší
- Není potřeba refresh - stav klopného obvodu se udrží tak dlouho, dokud neodpojíme napájení
- SRAM je o dost dražší než DRAM, pojme také mnohem méně dat

![image](https://github.com/janekspalek/apps-zkouska/assets/98762780/838497fb-12df-49ee-bd0f-e542bf7bc33f)

## Paměti s trvalým obsahem

- Data jsou zde uložena energeticky nezávislým způsobem
- Používají se například k uložení BIOSu

### ROM

> Read Only Memory
- Slouží pouze pro čtení
- Buňka paměti je elektrická pojistka
- Výrobce pak některé z nich přepálí - nebudou vést proud
- Přepálené = logická 1, nepřepálené = logická 0

### PROM

> Programmable ROM
- Lze do nich jednou zapsat, poté již pouze číst
- Složením jsou velmi podobné ROM

### EPROM

> Erasable PROM
- Lze do nich opakovaně zapisovat i číst
- Data jsou uložená ve formě elektrického náboje, který je kvalitně izolován (udrží svoji hodnotu i po odpojení zdroje)
- Data lze ale smazat pouze pomocí UV - zbytečně složité
- Informace si udrží cca 20 let

### EEPROM

> Electrically Erasable PROM
- Zapisovat i číst lze pomocí elektrického proudu, není potřeba UV

### FLASH

- V posledních letech velmi využívaná paměť
- Prakticky stejná jako EEPROM
- Udrží informaci až po dobu 100 let

### Další typy pamětí

**1. VRAM**
- Video RAM
- Obyčejné DRAM by neumožnily vyšší obnovovací frekvenci, proto byla vyvinuta VRAM

**2. Cache paměti**
- Mezisklad informací mezi různě rychlými částmi PC


