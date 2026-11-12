# Flusso e prototipo navigabile

Specifica delle transizioni, degli overlay e dei percorsi di verifica del prototipo navigabile.

---

## 1. Mappa delle transizioni

Formato: `da → elemento → a` · tipo di animazione · note.

### Dalla Home (S01)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S01 | FAB `Aggiungi` | S02 | Smart Animate · slide up · 250 ms |
| S01 | Card prioritaria, `Cucina ora` | S09 (dettaglio ricetta «Pasta pomodoro e mozzarella») | Dissolve · 200 ms |
| S01 | Card prioritaria, `L'ho buttato` | S01 | Smart Animate · mostra conferma in linea (toast), 2000 ms |
| S01 | Card prioritaria, `Ne scadono altri 2 oggi` | S04 | Slide left · 250 ms |
| S01 | Card ricetta, `Vedi ricette (3)` | S06 | Slide left · 250 ms |
| S01 | Qualsiasi riga prodotto | S08 | Slide left · 250 ms |
| S01 | `Vedi tutti quelli in scadenza (12)` | S04 | Slide left · 250 ms |
| S01 | Riquadro spreco | S07 | Slide left · 250 ms |
| S01 | Tab `Dispensa` | S04 | Instant |
| S01 | Tab `Ricette` | S06 | Instant |
| S01 | Tab `Spreco` | S07 | Instant |

### Dall'aggiunta (S02, S03)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S02 | `Chiudi` | S01 | Slide down · 250 ms |
| S02 | `Salva` (in app bar) | S01 | Dissolve · 200 ms + toast `Mozzarella salvata` |
| S02 | Un suggerimento | S03 | Slide left · 250 ms |
| S02 | `Crea «mozzarella»` | S03 | Slide left · 250 ms |
| S02 | `Avanti` | S03 | Slide left · 250 ms |
| S03 | `Annulla` | S02 | Slide right · 250 ms |
| S03 | `Salva in dispensa` | S01 | Dissolve · 200 ms + toast `Mozzarella salvata in Frigo` |
| S03 | `cambia` (data) | — | Apri overlay calendario (facoltativo, P2) |

### Dalla Dispensa (S04)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S04 | FAB `Aggiungi` | S02 | Slide up · 250 ms |
| S04 | Riga, `Cucina` | S06 | Slide left · 250 ms |
| S04 | Riga, icona `pencil` | S08 | Slide left · 250 ms |
| S04 | Riga (tocco sul nome) | S08 | Slide left · 250 ms |
| S04 | `Cerca` (app bar) | — | Attiva il campo di ricerca (stato) |
| S04 | Chip `Frigo (11)` | S04 | Stato `filtro-attivo` |
| S04 | Tab `Oggi` | S01 | Instant |
| S04 | Tab `Ricette` | S06 | Instant |
| S04 | Tab `Spreco` | S07 | Instant |

### Dalla notifica (S05)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S05 | Banner compresso (tocco) | S05 stato `espansa` | Smart Animate · 250 ms |
| S05 | `Cucina la ricetta` | S09 | Dissolve · 200 ms (la notifica si chiude) |
| S05 | `Più tardi (stasera)` | S01 | Dissolve · 200 ms |
| S05 | `L'ho buttata` | S01 | Dissolve · 200 ms + toast `Registrato` |

### Dalle ricette (S06, S09)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S06 | Card grande | S09 | Slide left · 250 ms |
| S06 | Card parziale | S09 | Slide left · 250 ms |
| S06 | Riga | S09 | Slide left · 250 ms |
| S09 | `Indietro` | S06 | Slide right · 250 ms |
| S09 | `Ho cucinato: scala dalla dispensa` | S04 | Dissolve · 200 ms + toast |
| S06 | Tab `Oggi` | S01 | Instant |
| S06 | Tab `Dispensa` | S04 | Instant |
| S06 | Tab `Spreco` | S07 | Instant |

### Dallo spreco (S07, S10)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S07 | `Mese >` | S10 | Slide left · 250 ms |
| S07 | Una riga spreco | S10 | Slide left · 250 ms |
| S10 | `Indietro` | S07 | Slide right · 250 ms |
| S07 | Tab `Oggi` | S01 | Instant |
| S07 | Tab `Dispensa` | S04 | Instant |
| S07 | Tab `Ricette` | S06 | Instant |

### Scheda prodotto (S08)

| Da | Elemento | A | Animazione |
|---|---|---|---|
| S08 | `Indietro` | S04 | Slide right · 250 ms |
| S08 | `Modifica` | S08 stato `modifica` | Smart Animate · i campi prendono il bordo attivo |
| S08 | `Fine` | S08 stato `lettura` | Smart Animate |
| S08 | `Cucina con questo prodotto` | S09 | Slide left · 250 ms |
| S08 | `Sposta la scadenza` | — | Overlay calendario |
| S08 | `Segna come finito` | S04 | Dissolve · 200 ms + toast `Segnato come finito` |
| S08 | `Non ricordarmelo` | S04 | Dissolve · 200 ms + toast `Non ti avviserò più per questo prodotto` |

### Stati speciali

| Da | Elemento | A | Note |
|---|---|---|---|
| qualsiasi | — | S11 (Dispensa vuota) | Resta nel file, **nessun hotspot**. Raggiungibile solo con un secondo punto di partenza del prototipo per la demo. Collegare un hotspot nascosto violerebbe la verifica F5. |
| qualsiasi | — | S12 (Primo utilizzo) | **Secondo punto di partenza** del prototipo (`Present → Start point`), dichiarato. |
| S05 · banner espanso | `Nascondi i dettagli sul blocco schermo` (spunta) | S13 | Slide left · 250 ms |
| S13 | `Indietro` | S05 | Slide right · 250 ms |

**Suggerimento pratico.** Per gli stati vuoti e il primo utilizzo conviene creare un **secondo punto di
partenza** del prototipo (`Present → Start point`), così durante lo user test puoi decidere da dove far
partire il partecipante. Il punto di partenza principale è sempre S01 · Home.

---

## 2. Comportamenti che non sono collegamenti

Da impostare come **overlay** o come **stato dello stesso frame**:

| Comportamento | Come |
|---|---|
| Toast di conferma (salvataggio, spreco, «finito») | Overlay in basso, larghezza 100% − 32, `radius/md`, sfondo `grey/900`, testo bianco, durata 2000 ms, chiusura automatica |
| Tastiera | Non prototipata |
| Calendario | Overlay `sheet` dal basso, altezza 400 |
| Conferma di azione distruttiva | Overlay `dialog` centrato, 300 × 160, due pulsanti |

---

## 3. Percorsi di verifica

I sei percorsi seguenti costituiscono scenari di verifica per la navigazione e per la successiva valutazione con utenti nella Fase 5.

| # | Percorso | Passi attesi | Esito |
|---|---|---|---|
| **P1** | Registrare un prodotto dalla Home | Home → FAB → scrivi «mozz» → tocco suggerimento → Salva | 4 tocchi, nessun campo obbligatorio oltre al nome |
| **P2** | Registrare senza dettagli | Home → FAB → tocco suggerimento → `Salva` in app bar | 3 tocchi |
| **P3** | Capire cosa scade oggi | Home → lettura card prioritaria → `Ne scadono altri 2 oggi` → Dispensa | L'utente vede che ci sono 3 prodotti, non 1 |
| **P4** | Decidere cosa cucinare | Home → `Vedi ricette (3)` → card → dettaglio ricetta | Nessuna ricetta richiede spesa |
| **P5** | Agire dalla notifica | Notifica → banner espanso → `Cucina la ricetta` | L'utente arriva alla ricetta in 2 tocchi |
| **P6** | Correggere un dato sbagliato | Dispensa → icona `pencil` → `Modifica` → cambia scadenza → `Fine` | L'azione è visibile senza menu nascosti |

---

## 4. Limiti del prototipo

Il prototipo rappresenta interfaccia e interazioni, senza implementare le seguenti funzioni:

- nessun dato reale, nessuna connessione a API o database;
- nessuna animazione oltre a quelle indicate: eventuali animazioni aggiuntive richiedono una decisione progettuale;
- nessun suono, nessuna vibrazione simulata;
- nessuna gestione dell'errore (rete assente, salvataggio fallito): è fuori perimetro dalla Fase 2 §7.3;
- nessuna modalità scura: solo tema chiaro in questa fase.
