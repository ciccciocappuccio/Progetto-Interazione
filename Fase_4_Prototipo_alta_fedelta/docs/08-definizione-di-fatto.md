# Definizione di fatto

La Fase 4 è considerata completa quando i criteri pertinenti risultano soddisfatti. La colonna Esito permette di documentare lo stato di ogni verifica (`fatto`, `non fatto` o motivazione).

---

## A · Struttura del file

| # | Verifica | Esito |
|---|---|---|
| A1 | Esistono due pagine: `01 · Design system` e `02 · Schermate` | |
| A2 | Sono presenti 18 frame: 13 schermate e 5 stati, con denominazioni coerenti con l'inventario (`S01 · Home` … `S13 · …`) | |
| A3 | I frame rispettano le dimensioni e le safe area definite nelle specifiche | |
| A4 | Nessun frame contiene note di progetto, post-it o commenti visibili dentro l'interfaccia (vincolo E34) | |
| A5 | I livelli hanno nomi in italiano e parlanti: nessun `Frame 42`, `Rectangle 7`, `Text 3` | |

## B · Variabili e stili

| # | Verifica | Esito |
|---|---|---|
| B1 | Esistono le collezioni `Primitives` e `Semantic`, con gli alias come da `03-design-tokens.md` | |
| B2 | Nessun livello usa un colore esadecimale scritto a mano: tutti usano variabili `Semantic` | |
| B3 | Esistono tutti gli stili di testo della tabella, con i nomi in inglese indicati (`Title 3`, `Body`…) | |
| B4 | Gli spaziature usano le variabili `layout/*` e `space/*` | |
| B5 | La famiglia tipografica è una sola in tutto il file | |

## C · Componenti

| # | Verifica | Esito |
|---|---|---|
| C1 | Tutti i componenti P0 e P1 di `06-componenti.md` esistono con le varianti elencate | |
| C2 | Le varianti hanno nomi in italiano (`variante=estesa`, non `variant=extended`) | |
| C3 | Nessuna istanza è stata staccata (**detach**) senza motivo dichiarato | |
| C4 | Il testo dentro le istanze è modificabile tramite proprietà di testo, non sovrascritto | |
| C5 | Gli elementi ripetuti sono istanze, non copie: nessun duplicato di un componente | |

## D · Contenuti

| # | Verifica | Esito |
|---|---|---|
| D1 | Ogni testo corrisponde a `04-contenuti-e-microcopy.md`, compresi accenti e punteggiatura | |
| D2 | Il verbo centrale è `Cucina` ovunque: nessuna occorrenza di `usa` come pulsante (vincolo E17) | |
| D3 | Non compare mai `Ho buttato` senza il pronome (vincolo E04) | |
| D4 | Non compare `3/3 ingredienti in casa` né equivalenti (vincolo E28) | |
| D5 | Non esiste il campo Categoria (vincolo E14) | |
| D6 | I numeri sono coerenti fra le schermate (24 prodotti, 12 in scadenza, € 6,40, −38%) | |
| D7 | Nessuna schermata contiene emoji, punti esclamativi o testo segnaposto tipo «Lorem ipsum» | |

## E · Correzioni della Fase 3

| # | Verifica | Esito |
|---|---|---|
| E1 | `Annulla` e `Chiudi` stanno in app bar a sinistra, mai come testo sotto il pulsante (vincolo E15) | |
| E2 | `Salva` senza dettagli è un'azione in app bar, non una didascalia (vincolo E07) | |
| E3 | Sulla data esiste un solo comando di modifica (vincolo E13) | |
| E4 | La notifica ha un'azione principale e un rinvio, non tre azioni equivalenti (vincolo E23) | |
| E5 | La notifica contiene l'interruttore privacy (vincolo E24) | |
| E6 | La riga della Dispensa ha `Modifica` come icona, non come pulsante largo (vincolo E35) | |
| E7 | Le card ricetta sono interamente toccabili (vincolo E27) | |
| E8 | Il grafico dello spreco mostra i valori (vincolo E31) | |

## F · Prototipo

| # | Verifica | Esito |
|---|---|---|
| F1 | I sei percorsi di `05-flusso-e-prototipo.md` §3 funzionano senza vicoli ciechi | |
| F2 | Ogni schermata ha una via di ritorno al punto precedente | |
| F3 | Le tab bar portano sempre alle quattro aree principali | |
| F4 | Il prototipo parte dalla Home per impostazione predefinita, con punti di partenza alternativi per S11 e S12 | |
| F5 | Nessun hotspot invisibile o dimenticato che porti a un frame sbagliato | |

## G · Consegna

| # | Verifica | Esito |
|---|---|---|
| G1 | Il file è condivisibile in sola lettura con il gruppo di progetto e i docenti | |
| G2 | Il link al prototipo cliccabile funziona in presentazione | |
| G3 | Le questioni ancora aperte in `07-domande-aperte.md` sono riportate nella documentazione del prototipo | |
| G4 | Ogni scostamento dalle specifiche è dichiarato con la sua motivazione | |

---

## Gestione delle limitazioni

Le verifiche non realizzabili per limiti dello strumento o del prototipo sono documentate nella colonna Esito con la motivazione e, se disponibile, un'alternativa. La tracciabilità delle limitazioni consente di distinguere le funzionalità realizzate da quelle rinviate.
