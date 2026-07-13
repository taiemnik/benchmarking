# Pravidla práce s daty

## Populační báze

| D-kód | Význam | Kdy použít |
|-------|--------|------------|
| D1.1 | Obyvatelé obce | Metriky na úrovni obce |
| D1.3 | Obyvatelé ORP | Většina přepočtů na 1000 obyvatel |
| D1.4 | Matriční obvod | Agenda matrika |
| D1.5 | Stavební obvod | Agenda stavební úřad |

Špatná báze = neplatný závěr. Vždy ověř v metodice ukazatele.

## Transformace hodnot

| Typ pole | Transformace v analýze |
|----------|------------------------|
| Procenta v exportu (např. D1.16) | ÷ 100 pro desetinné podíly |
| Tis. Kč (např. D9.7) | × 1000 pro koruny |
| Počty, úvazky | Beze změny |

Wide CSV používá sloupce `D9_7` (podtržítko místo tečky).

## Null policy

- `NA`, prázdné buňky = **chybějící hodnota** (null)
- **Neimputovat** — nevyplňovat průměrem ani extrapolací
- Null se propaguje do odvozených metrik

## Formáty souborů

| Soubor | Formát |
|--------|--------|
| `koprivnice-dkody.csv` | long: `city_id, year, code, name, kind, value` |
| `koprivnice-dkody-wide.csv` | wide: `city_id, year, D1_1, D1_3, …` |
| `koprivnice-prepocty.csv` | long: přepočtené ukazatele (`kind=prepocet`) |

## Druh ukazatele H/V

- **H** (hlavní) — primární metrika agendy
- **V** (vedlejší) — doplňkový kontext

Viz `metodika-ukazatele.csv`, sloupec `druh`.

## Hard rules

1. Jen D-kódy z `registr-ukazatelu.csv` — nevymýšlet kódy
2. Fakta ≠ hypotézy ≠ doporučení
3. Korelace není kauzalita
4. YoY trendy ignorovat roky s >90 % chybějících hodnot
