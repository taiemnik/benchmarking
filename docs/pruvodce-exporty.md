# Průvodce exporty z BVS

Aplikace nabízí **10 variant** exportu do XLS. Pro strojové zpracování používej **kanonické duo**.

## Stahuj tyto dva

| Tlačítko v BVS | Obsah |
|----------------|--------|
| **Souhrnný export vstupních dat do XLS po datových polích, s názvy** | D-kódy, všechny roky, všechna města |
| **Souhrnný export ukazatelů do XLS po ukazatelích, s názvy** | Přepočty, všechny roky, všechna města |

**Proč:** jeden soubor = celá časová řada; názvy = oficiální terminologie; struktura vertikálních bloků (kompatibilní s parsery).

## Nepoužívat pro pipeline

- Export **bez názvů** — ztráta kontextu
- Export **po obdobích** — jiná orientace tabulky (roky jako řádky)
- Export **jednoho roku** — neúplná časová řada
- Export **jen jednoho města** — pro síťové srovnání nevhodné

## Vzorníky v `priklady-exportu/`

12 souborů XLS — Kopřivnice, 2020–2025 — všechny varianty. Prohlédni strukturu, ne jako primární data.

## Struktura kanonického exportu (zjednodušeně)

```
[D9.1 Počet sledovaných úkonů]
obec / období | R2020 | R2021 | ...
115           | 1200  | 1250  | ...
114           | 980   | 1000  | ...
```

Každý D-kód = jeden blok. Řádky = `city_id`. Sloupce = roky.
