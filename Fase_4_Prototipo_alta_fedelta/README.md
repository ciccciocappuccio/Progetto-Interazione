# Fase 4 — Prototipo ad alta fedeltà

Documentazione progettuale per il prototipo interattivo ad alta fedeltà dell'app **Dispensa**, dedicata alla gestione della dispensa domestica e alla riduzione dello spreco alimentare.

## Obiettivo e perimetro

La fase sviluppa i wireframe revisionati durante la valutazione euristica e completa i flussi necessari per un successivo test con utenti. Il prototipo è pensato per rappresentare in dettaglio interfaccia, contenuti e navigazione; non include servizi o dati reali.

Sono previste 13 schermate: sette derivano dai wireframe della Fase 3 e sei aggiungono scheda prodotto, dettaglio ricetta, dettaglio mensile dello spreco, stato vuoto della Dispensa, primo utilizzo e impostazioni delle notifiche. L'inventario descrive inoltre cinque stati aggiuntivi.

## Documenti

| Documento | Contenuto |
|---|---|
| `docs/00-ORDINE-DI-LAVORO.md` | Percorso di progettazione e articolazione delle attività |
| `docs/01-inventario-schermate.md` | Schermate, stati, fonti e priorità |
| `docs/02-specifiche-schermate.md` | Struttura, misure e contenuti delle schermate |
| `docs/03-design-tokens.md` | Colori, tipografia, spaziature, raggi, elevazioni e icone |
| `docs/04-contenuti-e-microcopy.md` | Testi dell'interfaccia e regole editoriali |
| `docs/05-flusso-e-prototipo.md` | Transizioni, overlay e percorsi da verificare |
| `docs/06-componenti.md` | Componenti, proprietà e varianti |
| `docs/07-domande-aperte.md` | Decisioni progettuali e ipotesi da validare |
| `docs/08-definizione-di-fatto.md` | Criteri di controllo della completezza e coerenza |
| `assets/wireframes-v2/` | Wireframe SVG revisionati nella Fase 3, usati come riferimento |

## Principi di lettura

- Le prime sette schermate mantengono la struttura dei wireframe v2 e recepiscono le correzioni documentate nella Fase 3.
- Le schermate complementari sono specificate in `docs/02-specifiche-schermate.md`.
- Le priorità P0, P1 e P2 indicano rispettivamente il flusso essenziale, le schermate utili a un test completo e gli elementi di completamento.
- La direzione visiva usa una base neutra con accenti cromatici funzionali; `docs/03-design-tokens.md` ne definisce i valori.
- Le questioni non ancora consolidate sono distinte dalle specifiche e raccolte in `docs/07-domande-aperte.md`.

## Risultato previsto

Un prototipo navigabile con interfaccia ad alta fedeltà, coerente con gli artefatti delle fasi precedenti e verificabile attraverso i percorsi descritti in `docs/05-flusso-e-prototipo.md`. I criteri di completezza e qualità sono elencati in `docs/08-definizione-di-fatto.md`.
