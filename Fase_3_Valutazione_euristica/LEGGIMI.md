# Fase 3 — Valutazione euristica

Consegna della terza fase del caso di studio: ispezione di usabilità dei wireframe della Fase 2
con le euristiche di Nielsen.

## Che cosa contiene

| File / cartella | Che cos'è |
|---|---|
| `Fase_3_Relazione.pdf` | **Il documento da consegnare.** 27 pagine: metodo, le 10 euristiche tradotte nel dominio, scala di severità, registro dei 34 problemi, i 9 problemi maggiori raccontati per esteso, grafici, confronto prima/dopo, decisioni di non correzione, passaggio alla Fase 4 |
| `Fase_3_Relazione.md` | Il sorgente del documento |
| `wireframe_v2/` | I 7 wireframe **rivisti** dopo la valutazione: le 19 correzioni sono già applicate |
| `grafici/` | I tre grafici della relazione in PNG, riutilizzabili in una presentazione |

## I numeri della valutazione

| | |
|---|---|
| Problemi trovati | **34** |
| Per principio violato | H2 il più violato (6 problemi): il linguaggio, non il layout |
| Per severità | 5 cosmetici · 17 minori · 11 maggiori · 1 catastrofico |
| Corretti | **19** (12 ridisegnando la schermata, 7 cambiando un testo) |
| Rinviati | 14, in tre categorie con motivazioni diverse |
| Accettati | 1, con motivazione |

## Il problema più grave

**E17** — il pulsante «usa» nella Dispensa, severità 4. È il passaggio che realizza la catena di valore
del prodotto (registro → avviso → pasto) ed era etichettato con un verbo senza oggetto. Corretto in
«Cucina». Il dettaglio è nel §6 della relazione.

## Un problema trovato *dopo* le correzioni

**E35** — affiancando «Modifica» e «Cucina» nella riga della Dispensa, i due comandi hanno la stessa
larghezza e quello meno importante ruba spazio al nome del prodotto. È registrato nel §8.1: correggere
introduce difetti nuovi, e dirlo è parte del metodo.

## Attenzione a non confondere le cartelle

| Se ti serve… | Vai in… |
|---|---|
| il prototipo **come è stato valutato** | `Fase_2_Prototipo_bassa_fedelta/wireframe_v1/` |
| il prototipo **dopo le correzioni** | questa cartella, `wireframe_v2/` |

Se devi costruire l'alta fedeltà, parti da `wireframe_v2/`: è quello approvato.

## Prima di consegnare

- [ ] Il PDF si apre e le coppie prima/dopo sono affiancate correttamente
- [ ] I nomi dei valutatori non ci sono: vanno aggiunti nel §2.1 se il docente li chiede
- [ ] La data delle due sessioni di ispezione non è indicata: da aggiungere
