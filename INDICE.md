# Progetto — Dispensa: gestione domestica e pianificazione dei pasti anti-spreco

Caso di studio di Interazione Uomo-Macchina · Anno accademico 2026/2027

Il progetto documenta il percorso di progettazione centrato sulle persone, dal materiale di partenza alla definizione del prototipo ad alta fedeltà. Ogni fase conserva i propri artefatti per rendere leggibili le decisioni e le revisioni.

## Struttura della cartella

```text
00_materiale_di_partenza/        dispense, intervista e idea progettuale
Fase_2_Prototipo_bassa_fedelta/  relazione e wireframe iniziali
Fase_3_Valutazione_euristica/    valutazione, grafici e wireframe revisionati
Fase_4_Prototipo_alta_fedelta/   specifiche e materiali per il prototipo ad alta fedeltà
```

## Materiale di partenza

`00_materiale_di_partenza/` raccoglie le dispense del corso, l'intervista simulata della Fase 1 e la descrizione del dominio applicativo. Costituisce il contesto documentale del caso di studio.

## Fase 2 — Prototipo a bassa fedeltà

**Relazione:** `Fase_2_Prototipo_bassa_fedelta/Fase_2_Relazione.pdf`
La relazione presenta il dominio, le scelte di prototipazione, persona e scenari, task analysis, requisiti, flusso, wireframe commentati, tracciabilità e limiti.

**Materiali:** `wireframe_v1/` contiene sette schermate e un diagramma di flusso in SVG e PNG. La cartella conserva la versione precedente alla valutazione euristica.

## Fase 3 — Valutazione euristica

**Relazione:** `Fase_3_Valutazione_euristica/Fase_3_Relazione.pdf`
La valutazione con le euristiche di Nielsen documenta 34 problemi: 19 corretti, 14 rinviati con motivazione e 1 accettato.

**Materiali:** `wireframe_v2/` raccoglie le sette schermate revisionate; `grafici/` contiene le visualizzazioni dei risultati. Questi wireframe costituiscono la base progettuale della Fase 4.

## Fase 4 — Prototipo ad alta fedeltà

`Fase_4_Prototipo_alta_fedelta/` raccoglie le specifiche del prototipo interattivo: inventario delle schermate, layout, design token, microcopy, flussi, componenti, decisioni aperte e criteri di verifica. La cartella include i sette wireframe di riferimento in `assets/wireframes-v2/`.

Il prototipo comprende 13 schermate (le sette schermate revisionate e sei schermate complementari), oltre a cinque stati aggiuntivi. La documentazione è articolata in un `README.md` di fase e nei documenti numerati della cartella `docs/`.

## Sequenza progettuale

```text
Fase 2  →  wireframe iniziali (wireframe_v1/)
               ↓ valutazione euristica
Fase 3  →  problemi documentati e wireframe revisionati (wireframe_v2/)
               ↓ specificazione e sviluppo del prototipo
Fase 4  →  prototipo ad alta fedeltà e navigabile
```

La conservazione degli artefatti delle diverse fasi permette di seguire l'evoluzione delle scelte e la relazione tra valutazione e revisione.

## Stato delle fasi

| Fase | Documento principale | Materiali | Stato documentale |
|---|---|---|---|
| 2 | `Fase_2_Relazione.pdf` | wireframe v1, SVG e PNG | documentata |
| 3 | `Fase_3_Relazione.pdf` | wireframe v2 e grafici | documentata |
| 4 | specifiche in `Fase_4_Prototipo_alta_fedelta/docs/` | wireframe di riferimento e criteri del prototipo | specificata |
| 5 | — | — | da svolgere: test con utenti |

## Note editoriali

I frontespizi delle relazioni PDF non riportano i nomi del gruppo e richiedono l'integrazione prima della consegna, se prevista. I sorgenti Markdown delle relazioni sono conservati accanto ai PDF per consentire l'aggiornamento dei documenti.
