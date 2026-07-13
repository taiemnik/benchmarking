# Inspirace — popisné postřehy

> **⚠️ DISCLAIMER:** Toto jsou **interní postřehy z experimentální práce** — ne oficiální metodika BVS, ne ověřené výstupy. Může obsahovat slepé uličky. Vždy validuj proti `metodiky/` a datům. **Žádné konkrétní analýzy ani hotové dashboardy zde nejsou.**

## Odvozené metriky nad standardními ukazateli

BVS počítá standardní přepočty. Pro manažerské otázky často chybí vrstva **„co to znamená v praxi"**:

- **Úkony na FTE** — zatížení lidí (ne jen na 1000 obyvatel)
- **Příjem na úkon** — ekonomická efektivita agendy
- **YoY delta s kontextem** — ne jen procento, ale i absolutní dopad
- **Kompozitní skóre** — kombinace více H ukazatelů (opatrně, transparentně)



## Blend modely (populační + druhá proměnná)

U některých agend nestačí čistě populační model (obyvatelé ORP). Smysl dává **blend**:

- např. 60 % očekávání z populace + 40 % z provozní proměnné (autoškola, stavební řízení, …)
- účel: odhad **demand gap** — kde je provoz nad/pod očekáváním
- **riziko:** blend je hypotéza — vždy oddělit fakta od modelu



## Hard rules (co se osvědčilo)

1. **Populační báze** — vždy explicitně (D1.1 vs D1.3 vs D1.4 vs D1.5)
2. **Null = null** — neimputovat
3. **Trimmed průměr** — u srovnání skupin zvážit ořez outlierů
4. **Fakta / hypotéza / doporučení** — tři oddělené vrstvy odpovědi
5. **„Z dat to nejde"** — legitimní a žádoucí odpověď
6. **Ne všechna města vyplňují data správně a ne všechna města vyplňují stejně** - je třeba kriticky hodnotit výsledky a klást si otázku, jestli to dává smysl



## Prezentace

- Dashboard pro radu ≠ dashboard pro analytika
- Animace má **komunikovat informaci**, ne zdobit, zároveň je to prostředek, jak zaujmout oko pozorovatele
- Filtr podle agendy + fulltext v názvech ukazatelů šetří čas vedení



## Co záměrně chybí

- Konkrétní čísla a závěry z interních analýz
- Data ostatních měst

Pro oficiální definice použij `metodika-ukazatele.csv` a `metodika-datova-pole.csv`.