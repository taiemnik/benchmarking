# Benchmarking Hackathon — AI datový asistent

Veřejná datová sada a metodiky pro návrh **AI asistenta nad daty Benchmarkingu ve veřejné správě** (BVS).

**Cíl:** Navrhnout asistenta, který umí pracovat s časovými řadami městských ukazatelů — interpretovat, ověřovat hypotézy a prezentovat výsledky. V tomto repu jsou **pouze data města Kopřivnice** (`city_id=115`); stejná struktura dat existuje pro ~96 dalších měst (2010–2025) — asistent má být navržen tak, aby srovnání a trendy fungovaly, až se data doplní.

## Čtyři schopnosti asistenta

1. **Hledat příběhy za čísly** — neservírovat tabulky, ale interpretaci: co se děje, proč, s čím to souvisí (trend, srovnání, anomálie).
2. **Ověřovat pocity proti datům** — např. „mám pocit, že nám lidi utíkají k sousedovi" → najít relevantní ukazatele a potvrdit/vyvrátit.
3. **Odpovědět na jakoukoli otázku — včetně poctivého „z BI dat to nelze zodpovědět"** — znát hranice datasetu, nehalucinovat, umět říct, co by k odpovědi chybělo.
4. **Prezentovat data sexy způsobem** — animované dashboardy (koláče, sloupce) i interaktivní dashboardy s filtry a vyhledáváním; výstupy k tisku i na web.

## Struktura repozitáře

```
├── data/                 # Data Kopřivnice + seznam měst (bez dat ostatních měst)
├── metodiky/             # Oficiální metodiky BVS (CSV) + pravidla transformací
├── docs/                 # Popis systému, datový model, průvodce exporty
├── priklady-exportu/     # Vzorník 12 XLS exportů z BVS (Kopřivnice)
└── inspirace/            # Popisné postřehy (disclaimer — ne závazná metodika)
```

## Rychlý start

1. Přečti `docs/jak-funguje-benchmarking.md` a `docs/datovy-model.md`
2. Prohlédni `metodiky/registr-ukazatelu.csv` — co je v datech k dispozici
3. Načti `data/koprivnice-dkody-wide.csv` pro analýzu (wide = 1 řádek na rok)
4. Vzorce ukazatelů: `metodiky/metodika-ukazatele.csv`
5. Definice vstupních polí: `metodiky/metodika-datova-pole.csv`

## Publikace na GitHub

```bash
cd benchmarking-public
git init
git add .
git commit -m "Initial hackathon dataset — Kopřivnice + metodiky"
git remote add origin https://github.com/taiemnik/benchmarking.git
git push -u origin main
```

## Citlivost a licence

- **Data:** pouze Kopřivnice (veřejné statistiky města o sobě)
- **Seznam měst:** veřejná informace, bez hodnot ukazatelů ostatních měst
- **Metodiky:** oficiální texty z aplikace BVS — citujte zdroj
- Viz `LICENSE` a `DISCLAIMER.md`

## Zdroj

Aplikace [Benchmarking ve veřejné správě](https://www.benchmarking.cz/) v8.6 — projekt MÚ Kopřivnice / Datová analytika.
