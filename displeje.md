# LCD displej

> Liquid Crystal Display

- Pro zobrazování využívá `tekuté krystaly`
- Starší technologie `TN-TFT` *(Twisted Nematic - Thin Film Transistor)*
- Novější technologie `IPS` *(In Plane Switching)*
- **Výhody**: kvalita obrazu, životnost, spotřeba energie
- **Nevýhody**: citlivost na teplotu, vadné pixely, doba odezvy

## Princip TN-TFT

> Twisted Nematic - Thin Film Transistor

- Využívá `nematické krystaly`, které jsou v LCD uspořádány do šroubovice
- Nepolarizované světlo nejprve projde prvním polarizačním filtrem a polarizuje se
- Poté prochází vrstvami pootočených tekutých krystalů, které světlo otočí o 90°
- Dále světlo projde i druhým polarizačním filtrem, které je otočeno o 90° proti prvnímu
- Takto se TN-LCD chová v klidovém stavu (bez elektrického proudu)
- Jakmile začne tekutými krystaly protékat elektrický proud, natočí se podle směru toku proudu
- Všechna zrnka se tedy otočí jedním směrem a přestane docházet k otáčení světla
- Intenzitu světla lze měnit pomocí `střídavého proudu`
- Vrstva tekutých krystalů je rozdělena na malé buňky (jednotlivé body) displeje
- LCD musí být podsvětlen bílým světlem
- 0 proudu = bod svítí

![image](https://github.com/janekspalek/apps-zkouska/assets/98762780/4a5c161c-9da1-45b6-9eb7-0c4b07e51de9)


## Princip IPS

> In Plane Switching

- Pokročilejší technologie LCD displejů než TN-TFT
- **Mají lepší barvy a širší pozorovací úhly**
- Krystaly již netvoří šroubovici, ale jsou uspořádány v **rovině**
- Při přivedení proudu se krystaly začnou opět otáčet, tím dojde k otočení celé roviny krystalů
- **V klidovém stavu krystaly světlo neotáčí = buňka nesvítí**

![image](https://github.com/janekspalek/apps-zkouska/assets/98762780/439e9a4a-ed65-485d-b72d-9883c41146a4)

## Barevné LCD displeje

- Konstrukce je téměř stejná jako u jednobarevných
- Každý pixel se skládá ze tří sub-pixelům, které filtrují RGB barvy
- Kombinací těchto tří barev se vytvoří výsledná barva

## Aktivní vs. pasivní LCD displeje

**Pasivní**
- Maticové rozložení pixelů
- Každý řádek a sloupec má vlastní elektrody
- Méně ostrý a konstrastní obraz, pomalejší odezva
- Levnější
- Používá se v hodinkách, kalkulačkách apod.

**Aktivní**
- Používají tranzistorové matice pro každý pixel
- Každý pixel má vlastní tranzistor pro lepší ovládání
- Vysoký kontrast, ostrý obraz
- Vyšší cena i spotřeba energie
- Používají se v monitorech, televizorech, mobilních telefonech

# OLED displeje

> Organic Light Emitting Diode

- Nepotřebuje žádné podsvícení
- Mezi katodu a anodu je přivedeno napětí
- Dochází k `rekombinaci` elektronů a děr - vzniká excitovaný stav
- Při tomto jevu se uvolňuje energie ve formě fotonů - ty lze vidět lidským okem jako světlo
- Podle typu použitého organického materiálu má toto světlo barvu
- **Výhody**: perfektní černá, vysoký konstrast, barvy, nízká spotřeba, dobré pozorovací úhly, rychlá odezva
- **Nevýhody**: vyšší cena

![OLED displej](https://notebook.cz/clanky/technologie/2009/oled/oled-schema.gif)

## RGB OLED

- Způsoby řazení barev mohou být různé:
1. Vedle sebe (_horizontálně_)
3. Pod sebou (_vertikálně_)
4. Pod sebou + bílá barva - `RGBW`

![image](https://github.com/janekspalek/apps-zkouska/assets/98762780/283a7f1c-f4d6-4db1-9c60-852b68845bd9)


## AMOLED vs. PMOLED

> Active/Passive Matrix OLED

- Jde o stejný princip jako aktivní a pasivní LCD displeje
- U aktivních má každý pixel svůj vlastní tranzistor
- Pasivní mají dvojice elektrod

# E-Ink displeje

> Elektronický inkoust

- Pro zařízení, která k zobrazení statické informace nepotřebují elektrický proud
- EPD = Electronic Paper Device
- Jednotlivé body jsou tvořeny malými kapslemi - obsahují `elektroforetický` (elektricky-separovatený) roztok
- V tomto průsvitném roztoku jsou **záporně nabité částice - černé**, a **kladně nabité částice - bílé**
- Kapsle jsou umístěny mezi horní a dolní elektrodu, na kterou se částice podle svého náboje přítáhnou
- Lze také vytvářet několik odstínů šedé pomocí dělených elektrod
- Černé částice jsou z uhlíku
- Po odpojení napájení již není potřeba proud pro udržení částic v dané poloze
- U čteček se udává počet stránek na jedno nabití (počet změn na displeji)
- Existují i barevné E-Ink displeje - fungují stejně jak LCD přes barevné filtry, ale mají velmi malý počet barev
- **Výhody**: velmi nízká spotřeba energie (pouze při změně obsahu), výborná čitelnost na slunci, vynikající pozorovací úhly
- **Nevýhody**: nízká obnovovací frekvence, nižší rozlišení, pouze 16 odstínů šedé, malý rozsah barev

![E-Ink displej](https://myelectrical.com/Portals/0/SunBlogNuke/2/Windows-Live-Writer/E-Ink_F1B9/eInkTechnology_2.jpg)
