# RISC procesory

> Reduced Instruction Set Computer

- Počítač s redukovaným počtem instrukcí
- Procesoru nechali pouze nezbytně nutné činnosti
- Programátoři využívali pouze omezenou část instrukcí - proto počet instrukcí snížili na konci 70. let
- Dnes neexistuje žádný čistý RISC nebo CISC procesor - každý má v sobě něco z obou kategorií

**Hlavní vlastnosti RISC:**

1. V každém strojovém cyklu by měla být dokončena právě **jedna** instrukce
2. **Zřetězené** zpracování instrukcí
3. Data jsou z hlavní paměti vybírána a ukládána jen pomocí `STORE` a `LOAD`
4. Navýšený počet registrů
5. Instrukce mají jednotnou délku - rychlejší práce s pamětí

## Proudové zpracování instrukcí

- Procesor je `sekvenční obvod`
- Vstupem jsou _strojové instrukce_ a _data_ z paměti
- Další instrukce se nezačne výkonávat dříve, dokud nebyl předchozí cyklus zcela dokončen
- Kdybychom jednotlivé fáze rozdělily na samostatné obvody - jednotlivé úkony
- Zpracování bude mnohem rychlejší, ALE toto s sebou přináší mnohé nástrahy, úskalí a problémy

### Problémy zřetězeného zpracování

**1. Datové a strukturální hazardy**
- `Datové hazardy` vzniknou například tehdy, když některá rozpracovaná instrukce potřebuje mít k dispozici data z předchozí instrukce, ale ta ještě nejsou k dispozici
- `Strukturální hazardy` vznikají tehdy, když je potřeba komunikovat přes sběrnici _(takže skoro pořád)_, ta je ale pouze jedna, a nelze k ní povolit přístup více jednotkám zároveň. Přístup na sběrnici je třeba _koordinovat_, což ale přinese další **zpomalení**

**2. Problémy plnění fronty instrukcí**
- Problémy nastávají u `podmíněných skoků` - u něj známe adresu, ale nevíme, zdali se provede či nikoliv
- Nejjednodušší řešení je pokračovat sekvenčním zpracováním a pokud se skok neprovede, tak se rozpracovaná fronta provede


## ARM Cortex-A35

- Až 4 jádra
- Zaměřený na vysokou energetickou efektivnost
- 1-1,5 GHz
- Podpora L1 a L2 cache

![A35](https://cdn.discordapp.com/attachments/1078965904093745252/1245482535392116738/2015_-_A35.jpg?ex=66622400&is=6660d280&hm=30c3685c883cd4fcb4efa3292171cb3e254e4dc6ce60d3f3057becf11ef87f8f&)



[https://drive.google.com/drive/folders/1tbuhnU2iSmzuK3gYcsxs4wDkD-CoLmQr?usp=sharing](https://drive.google.com/file/d/1DaWny9DOk2mCjM2If83rQAXQa-oupr-4/view?usp=drive_link)
