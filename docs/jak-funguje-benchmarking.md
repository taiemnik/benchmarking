# Jak funguje benchmarking ve veřejné správě

## Co to je

**Benchmarking ve veřejné správě (BMVS)** je celostátní systém srovnávání výkonnosti měst a obcí v ČR. Je to podnikání soukromé společnosti Benchmarking ve veřejné správě, s.r.o., která data sbírá od měst (města vyplňují sami dle pokynů) a na základě nich vypracovává analýzy jednotlivých agend. Města vyplňují **vstupní datová pole (D-kódy)** — počty úkonů, úvazky, příjmy, obyvatelstvo. Systém z nich počítá **ukazatele (přepočty)** — metriky na obyvatele, podíly, efektivitu. **Města mohou data všech měst z databáze exportovat a interpretovat podle sebe.**

## Rozsah dat


| Dimenze                | Hodnota                                                          |
| ---------------------- | ---------------------------------------------------------------- |
| Města v síti           | ~155 (lookup v `data/mesta.csv`), seznam měst se každoročně mění |
| Města v tomto exportu  | 96                                                               |
| Roky                   | 2010–2025                                                        |
| Agendy                 | 60+ (matrika, stavební, doprava, finance, …)                     |
| D-kódů v exportu       | 309                                                              |
| Přepočtových ukazatelů | 294                                                              |




## Jak se dnes typicky pracuje

1. **Dashboardy BVS** — vestavěné grafy a tabulky v webové aplikaci
2. **Ruční čtení** — porovnávají se hodnoty města vs. průměr skupiny (jsme lepší/horší)
3. **Export do XLS** — pro hlubší analýzu v Excelu (10 variant exportu)
4. **Konzultanti BVS** — metodická podpora a interpretace, zpracování hlubších analýz



## Co chybí (příležitost pro AI)

- Propojení **příběhu** napříč agendami („proč klesá X když roste Y")
- Rychlé **ověření hypotéz** bez ručního hledání v tabulkách
- **Interaktivní** prezentace pro radu / občany
- Poctivá **hraniční odpověď** — co data neumožňují



## Kopřivnice v síti

- `city_id`: **115**
- Název: Kopřivnice
- Skupina: **C** (střední města)
- Kraj: Moravskoslezský

Srovnávací skupina C obsahuje další města stejné velikostní kategorie — jejich data nejsou v tomto repu, ale struktura je identická.

## Zdroj

[Aplikace Benchmarking ve veřejné správě — bmvs.cz](https://www.bmvs.cz/)