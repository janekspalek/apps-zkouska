# CUDA

> Compute Unified Device Architecture

- Umožňuje využití výkonu GPU
- Vyvinuta společností **NVIDIA** - nelze spustit s grafikou od AMD

Hlavní vlastnosti:

1. **Paralelní výpočty**:
   - Umožňuje provádět paralelní výpočty pomocí velkého množství výpočetních jednotek GPU
   - Je to ideální pro úlohy, které lze rozdělit na malé části, které lze zpracovávat současně (např. práce s pixely)
2. **Bloky a mřížky**
   - CUDA organizuje paralelní výpočty do mřížek `grids` a bloků `blocks`
   - Mřížka obsahuje mnoho bloků a každý blok obsahuje mnoho vláken `threads`
   - Bloky jsou prováděny paralelně, každé vlákno v bloku provádí instanci kernel funkce
3. Paměťová hierarchie
   - **Globální pamět**: sdílená paměť mezi všemi bloky a vlákny, ale je pomalejší
   - **Sdílená paměť**: Rychlejší paměť sdílená mezi vlákny v jednom bloku

## Principy pro programátora

- Je nutné identifikovat úlohy, které mohou být prováděny paralelně
- `Kernel` je funkce, která běží na GPU. Musí být definována s ___global___
- `Thread` je nejmenší jednotka práce, má jedinečný identifikátor v rámci bloku
- `Blocks` sada vláken, které běží současně a mohou sdílet paměť. Každý blok má jedinečný identifikátor
- `Grids` sada bloků
- `dim` struktura, určuje počet dimenzí - dim, dim2, dim3

### Přesouvání paměti

- Data, která chceme zpracovat na GPU, musí být nejprve zkopírována z CPU do GPU
- Po zpracování dat na GPU je potřeba výsledek zkopírovat zpět do CPU
- `Host (CPU)` - hlavní paměť PC
- `Device (GPU)` - paměť na grafické kartě, která je využívána pro paralelní výpočty
- Lze použít `Unified memory` (sjednocenou paměť) - paměť, která je automaticky spravována jak pro CPU, tak pro GPU bez nutnosti kopírování mezi nimi

![CUDA](https://nyu-cds.github.io/python-gpu/fig/02-threadmapping.png)

# Otázky

## Co je to architektura CUDA?
- Je to paralelní výpočetní platforma a programovací model vyvinutý společností NVIDIA
- Umožňuje využít GPU pro obecné výpočty mimo grafiku
- Zjednodušuje práci vývojářům
- Umožňuje provádění paralelních výpočtů pomocí velkého množství výpočetních jednotek
- Ideální pro úlohy, které se dají rozdělit na více menších úloh

## Nakreslete a vysvětlete organizaci vláken pro realizaci výpočtu
- `Grid`
  - Obsahuje bloky, které jsou uspořádány do dvourozměrné nebo třídimenzionální mřížky
  - Grid je spouštěn jedním voláním kernelu
- `Blocks`
  - Každý blok obsahuje vlákna uspořádané do jedné, dvou nebo třídimenzionálního pole
  - Každý blok má unikátní identifikátor v rámci mřížky
  - Velikost bloku lze získat pomocí blockDim
- `Threads`
  - Jsou nejmenší jednotky práce
  - Každé vlákno má unikátní identifikátor v rámci bloku, který je kombinací jeho pozice v bloku

## Vysvětlete, jaký je postup výpočtu programu

- Zprvu jsou data připravena v hlavní paměti počítače _(host)_
- Dále se zavolá kernel, který běží na GPU
- Musí se synchronizovat, aby všechny operace na GPU byly dokončeny před pokračováním na CPU
- Použitím unified memory nemusíme kopírovat data z GPU na CPU, můžeme je přímo použít

## Jaké rozšíření jazyka C/C++ si CUDA vyžádala?
- **Nová klíčová slova**
  - `__global__` pro deklaraci kernelu, funkce, která běží na GPU a je volána z CPU
  - `__device__` běží na GPU
  - `__host__` běží na CPU
  - `kernelFunction<<<gridDim, blockDim>>>(par)` volání kernel funkce z CPU
