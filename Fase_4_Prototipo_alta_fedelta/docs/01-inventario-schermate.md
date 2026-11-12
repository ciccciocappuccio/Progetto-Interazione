# Inventario delle schermate

13 schermate. Le prime 7 derivano dai wireframe approvati in Fase 2 e corretti in Fase 3.
Le ultime 6 sono nuove: la Fase 3 ha dimostrato che servono e che la loro assenza bloccava
la correzione di sette problemi.

| # | Nome frame | Origine | Wireframe | Priorità |
|---|---|---|---|---|
| 1 | `S01 · Home` | Fase 2 + correzioni | `01-home.svg` | P0 |
| 2 | `S02 · Aggiunta · passo 1` | Fase 2 + correzioni | `02-aggiunta.svg` | P0 |
| 3 | `S03 · Aggiunta · passo 2` | Fase 2 + correzioni | `03-aggiunta-dettagli.svg` | P0 |
| 4 | `S04 · Dispensa` | Fase 2 + correzioni | `04-dispensa.svg` | P0 |
| 5 | `S05 · Notifica` | Fase 2 + correzioni | `05-notifica.svg` | P1 |
| 6 | `S06 · Ricette` | Fase 2 + correzioni | `06-ricette.svg` | P1 |
| 7 | `S07 · Spreco` | Fase 2 + correzioni | `07-spreco.svg` | P1 |
| 8 | `S08 · Scheda prodotto` | nuova (Fase 3, E06/E16/E20/E22/E26) | — | P1 |
| 9 | `S09 · Dettaglio ricetta` | nuova (citata dalla Fase 2, mai disegnata) | — | P1 |
| 10 | `S10 · Spreco · dettaglio mese` | nuova (Fase 3, E31/E32) | — | P2 |
| 11 | `S11 · Dispensa vuota` | nuova (Fase 3, E08/E30) | — | P1 |
| 12 | `S12 · Primo utilizzo` | nuova (Fase 3, E08) | — | P2 |
| 13 | `S13 · Impostazioni notifiche` | nuova (Fase 3, E24) | — | P2 |

## Frame di stato (aggiuntivi)

Cinque schermate hanno uno **stato** oltre al frame base. In Figma sono frame autonomi, non varianti di
un'unica schermata: uno stato di schermata cambia il contenuto di più componenti insieme, mentre una
variante serve a un elemento ripetuto.

| Frame | Stato | Note |
|---|---|---|
| `S02 · Aggiunta · passo 1` · `stato=digitazione` | campo con cursore e testo `mozz`, 2 risultati |
| `S03 · Aggiunta · passo 2` · `stato=focus-data` | campo scadenza attivo, `cambia` evidenziato |
| `S04 · Dispensa` · `stato=filtro-attivo` | chip `Frigo (11)` attiva, 11 prodotti |
| `S05 · Notifica` · `stato=espansa` | entrambi i banner |
| `S08 · Scheda prodotto` · `stato=modifica` | campi modificabili, `Fine` in app bar |

Il frame base è sempre lo stato `default`. Il file ha quindi **18 frame**: 13 di schermata + 5 di stato.

## Note sulle priorità

- **P0** — senza queste quattro schermate il prototipo non si può testare: sono il percorso critico.
- **P1** — servono per uno user test credibile, ma il prototipo resta navigabile anche senza.
- **P2** — completamento; se il tempo è poco, si tagliano per prime.

## Ambito escluso

Le seguenti funzioni non fanno parte del perimetro del prodotto definito nelle fasi precedenti:

- onboarding e registrazione dell'account;
- lista della spesa;
- scansione dello scontrino, dettatura vocale, codice a barre;
- impostazioni del profilo;
- sincronizzazione fra dispositivi e condivisione familiare;
- stati di errore di rete.

Il perimetro è coerente con le esclusioni documentate nella Fase 2, §7.3.
