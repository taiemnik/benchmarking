# Datový model

## Entity

```
Město (city_id) ──┬── Vstupní pole (D-kód) ── hodnota za rok
                  └── Ukazatel (přepočet) ── hodnota za rok (vzorec nad D-kódy)
```

## Long vs wide

### Long (`koprivnice-dkody.csv`)

Jeden řádek = jedna hodnota jednoho D-kódu v jednom roce.

```csv
city_id,year,code,name,kind,value
115,2023,D9.1,Počet sledovaných úkonů,dkod,1250
```

### Wide (`koprivnice-dkody-wide.csv`)

Jeden řádek = všechny D-kódy města v jednom roce. Sloupce `D1_1`, `D9_1` (tečka → podtržítko).

```csv
city_id,year,D1_1,D1_3,D9_1,...
115,2023,21886,41268,1250,...
```

### Přepočty (`koprivnice-prepocty.csv`)

Stejný long formát, `kind=prepocet`, `code` = číslo ukazatele (např. `9.1`).

## Lookup měst (`mesta.csv`)

```csv
city_id,nazev,skupina,kraj
115,Koprivnice,C,Moravskoslezsky kraj
```

155 měst — **bez hodnot ukazatelů** (jen metadata pro budoucí srovnání).

## Vazba D-kód ↔ ukazatel

- **metodika-datova-pole.csv** — definice D-kódu (co zadat, odkud, k 31.12.)
- **metodika-ukazatele.csv** — vzorec ukazatele (např. `D9.1/D1.3*1000`)
- **registr-ukazatelu.csv** — které kódy jsou reálně v exportu

## kind

| kind | Význam |
|------|--------|
| `dkod` | Vstupní datové pole |
| `prepocet` | Vypočtený ukazatel ze systému BVS |

## Chybějící hodnoty

`NA` nebo prázdné → interpretuj jako null. Viz `metodiky/pravidla-dat.md`.
