# Specifiche delle schermate

Per ogni schermata: struttura dall'alto verso il basso con le misure, i componenti da usare, gli stati
da disegnare. Le misure sono in px sul frame 390 × 844.

**Convenzione di lettura.** Ogni blocco è descritto come `nome — altezza · margine sopra`.
Salvo diversa indicazione, i margini laterali sono `layout/screen-margin` = 16.

**Regola generale.** Se una misura manca, si ricava dalla scala di spaziature (`docs/03-design-tokens.md` §3)
scegliendo il valore più vicino. Se due valori sono ugualmente plausibili, è una domanda.

---

## Struttura comune

Tutte le schermate tranne S05 hanno questa impalcatura:

```
┌──────────────────────────────┐
│ Status bar          59       │  ← orologio, batteria (di sistema, disegnala)
├──────────────────────────────┤
│ App bar             56       │  ← componente AppBar
├──────────────────────────────┤
│                              │
│ Contenuto (scroll)           │
│                              │
├──────────────────────────────┤
│ Tab bar             56       │  ← componente TabBar (non in S02, S03, S08–S13)
├──────────────────────────────┤
│ Home indicator      34       │  ← barra di sistema
└──────────────────────────────┘
```

---

# S01 · Home

**Frame** `S01 · Home` · 390 × 844

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | sistema |
| 2 | App bar | 56 | titolo `Ciao Marco`, azione destra `Notifiche` con icona `bell` |
| 3 | Etichetta data | 20 · sopra 16 | `OGGI, MERCOLEDÌ`, stile `Caption Strong`, `text/tertiary` |
| 4 | Card prioritaria | 148 · sopra 8 | componente `CardPrioritaria`, variante `warning` |
| 5 | Etichetta sezione | 20 · sopra 24 | `COSA CUCINO STASERA` |
| 6 | Card ricetta | 88 · sopra 8 | componente `CardRicetta`, variante `orizzontale` |
| 7 | Etichetta sezione | 20 · sopra 24 | `IN SCADENZA QUESTA SETTIMANA` |
| 8 | Righe prodotto | 56 cad. · gap 8 | 3 × `RigaProdotto` variante `suggerimento` |
| 9 | Pulsante `Vedi ricette (3)` | 44 · sopra 4 | variante `testo`, con `chevron-right` |
| 10 | Pulsante pieno-largo | 44 · sopra 12 | `Vedi tutti quelli in scadenza (12)`, variante `secondary` |
| 10 | Riquadro spreco | 72 · sopra 16 | `RiquadroSpreco` |
| 11 | FAB | 52 | in basso a destra, sopra la tab bar, margine 16 |
| 12 | Tab bar | 56 | tab attiva: `Oggi` |
| 13 | Home indicator | 34 | sistema |

### Card prioritaria — dettaglio

- padding 16
- etichetta `SCADE DOMANI`: pillola `amber/50`, bordo `amber/200`, testo `Caption Strong` `text/warning`
- titolo prodotto: `Title 3`
- sottotitolo: `Body` `text/secondary`, massimo 1 riga
- riga azioni, gap 8:
  - `Cucina ora`: pulsante `primary` altezza 36, larghezza a contenuto + 24
  - `L'ho buttato`: pulsante `secondary` altezza 36, stesso trattamento ma bordo `border/control`
- nota `Ne scadono altri 2 oggi` + `chevron-right`: `Micro`, `text/secondary`, area toccabile 44 di altezza

### Stati da disegnare

Solo uno: `default`. Gli stati vuoti sono S11 e S12.

### Note di fedeltà

- Il FAB ha `elev/2`.
- La card prioritaria ha `elev/1` e bordo `border/warning`.
- Le righe prodotto hanno separatori `border/subtle` a 1 px, non card separate: sono una lista, non tre card.

---

# S02 · Aggiunta, passo 1

**Frame** `S02 · Aggiunta · passo 1` · 390 × 844

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | sinistra `Chiudi` (icona `x`), titolo `Aggiungi prodotto`, destra `Salva` (testo) |
| 3 | Barra avanzamento | 4 · sopra 12 | metà piena, `radius/full` |
| 4 | Etichetta passo | 18 · sopra 8 | `Passo 1 di 2`, centrata, `Caption`, `text/tertiary` |
| 5 | Campo di ricerca | 48 · sopra 16 | componente `CampoRicerca`, **attivo** (bordo `grey/900`, 2 px dentro i 48) |
| 6 | Etichetta sezione | 20 · sopra 20 | `SUGGERITI (DALLA TUA DISPENSA)` |
| 7 | Lista suggerimenti | 5 × 56 · gap 8 · sopra 8 | `RigaProdotto` variante `suggerimento` |
| 8 | Voce di creazione | 48 · sopra 8 | bordo tratteggiato, `Crea «mozzarella»` |
| 9 | Nota | 18 · sopra 12 | `Un tocco e il prodotto è scelto`, centrata |
| 10 | Pulsante principale | 52 · a 16 dal fondo sopra la safe area | `Avanti`, `primary`, largo tutto |
| 11 | Didascalia | 18 · sopra 8 | `Salva subito, senza dettagli (in alto a destra)` |

### Stati da disegnare

1. `default` — come sopra.
2. `digitazione` — campo con cursore e testo `mozz` scritto; la lista mostra 2 risultati invece di 5.

### Note di fedeltà

- **Niente tab bar** su questa schermata: è un flusso modale.
- La tastiera **non** va disegnata (in Figma sarebbe un elemento di sistema che distrae); il frame si chiude
  con il pulsante a 16 px dal fondo.
- La voce `Crea «mozzarella»` esiste solo in stato `digitazione`. In `default` c'è il bordo tratteggiato vuoto
  con il solo testo `Crea «mozzarella»`.

---

# S03 · Aggiunta, passo 2

**Frame** `S03 · Aggiunta · passo 2` · 390 × 844

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | sinistra `Annulla` (testo), titolo `Mozzarella` |
| 3 | Barra avanzamento | 4 · sopra 12 | **piena** |
| 4 | Etichetta passo | 18 · sopra 8 | `Passo 2 di 2` |
| 5 | Etichetta + campo quantità | 20 + 48 · sopra 16 | `QUANTITÀ`; campo con `−` `1` `2` `+` e testo `confezione` a destra |
| 6 | Etichetta + campo data | 20 + 48 · sopra 20 | `SCADENZA`; campo con `14 nov 2026` e azione `cambia` a destra |
| 7 | Didascalia | 18 · sopra 6 | `stima predefinita: +7 giorni` |
| 8 | Etichetta + chip | 20 + 40 · sopra 20 | `DOVE`; chip `Frigo` attiva, `Freezer`, `Dispensa`, `Cantina` |
| 9 | Riquadro informativo | 104 · sopra 20 | `Cosa riceverai`, sfondo `bg/surface-sunken` |
| 10 | Nota | 36 | `Puoi correggere tutto anche dopo, dalla scheda del prodotto.` |
| 11 | Pulsante principale | 52 · a 16 dal fondo | `Salva in dispensa` |

### Stati da disegnare

1. `default` — come sopra.
2. `focus-data` — campo scadenza attivo: bordo `grey/900` 2 px, azione `cambia` evidenziata.

### Note di fedeltà

- Il campo data **non** ha altre scorciatoie accanto (vincolo E13).
- **Non esiste** il campo Categoria (vincolo E14).
- Le chip `Dove` hanno icona + parola: `refrigerator` Frigo, `snowflake` Freezer, `package` Dispensa,
  nessuna icona per Cantina (non ne esiste una adatta) — solo parola.
- Il riquadro `Cosa riceverai` non è un avviso tratteggiato: è un riquadro pieno, informativo.

---

# S04 · Dispensa

**Frame** `S04 · Dispensa` · 390 × 844

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | titolo `Dispensa`, sottotitolo `Ordinati per data di scadenza`, destra `Cerca` |
| 3 | Chip di filtro | 36 · sopra 12 | `Tutti (24)` attiva · `Frigo (11)` · `Freezer (3)` · `Dispensa (10)`, scroll orizzontale |
| 4 | Campo di ricerca | 48 · sopra 12 | non attivo: bordo `border/control` 1 px |
| 5 | Etichetta sezione | 20 · sopra 20 | `SCADONO PRESTO` |
| 6 | Righe in scadenza | 3 × 72 · gap 8 | `RigaProdotto` variante `estesa`, bordo `border/subtle`, stile leggermente rialzato |
| 7 | Etichetta sezione | 20 · sopra 24 | `TUTTO IL RESTO (9)` |
| 8 | Righe restanti | 6 × 64 · gap 8 | `RigaProdotto` variante `compatta` |
| 9 | Conteggio | 18 · sopra 16 | `24 prodotti in tutto`, centrato, `Caption`, `text/tertiary` |
| 10 | FAB | 52 | |
| 11 | Tab bar | 56 | tab attiva: `Dispensa` |

### RigaProdotto · variante `estesa`

- altezza 72, padding 16
- a sinistra: segnaposto immagine 40 × 40, `radius/sm`, `bg/surface-sunken`
- centro: nome `Title 3`; sotto, metadati `Caption` `text/secondary` (`1 conf. · domani`)
- a destra, gap 8: icona `pencil` 24 (area toccabile 44) + pulsante `Cucina` altezza 32

### RigaProdotto · variante `compatta`

- altezza 64, stesso schema, ma il pulsante `Cucina` **non c'è**: solo icona `pencil`
- il nome è `Body Strong`, non `Title 3`

### Stati da disegnare

1. `default` — come sopra.
2. `filtro-attivo` — chip `Frigo (11)` attiva, la lista mostra solo 11 prodotti (bastano 5 righe visibili).

### Note di fedeltà

- La variante `estesa` è per i prodotti in scadenza; la `compatta` per il resto. La differenza di altezza
  è voluta e segnala la priorità (vincolo E19, ordinamento dichiarato nell'app bar).
- **Nessun menu «···»**: le azioni sono visibili (vincolo E18).
- `Modifica` è un'icona, non un pulsante largo (vincolo E35).

---

# S05 · Notifica

**Frame** `S05 · Notifica` · 390 × 844

Questa schermata **non** ha app bar né tab bar: è il blocco schermo del telefono.

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Sfondo | 844 | `grey/900` al 60% sopra un'immagine sfocata, oppure tinta unita `#3A3A40` |
| 2 | Status bar | 59 | testo bianco |
| 3 | Banner notifica | 116 · sopra 60 | `radius/lg`, `elev/2`, sfondo `bg/surface` |
| 4 | Spazio | 24 | |
| 5 | Banner espanso | 232 | stesso componente, variante `espansa` |
| 6 | Etichetta | 18 · sopra 12 | `Nessun'altra notifica per oggi`, centrata, bianco 70% |
| 7 | Riquadro interruttore | 80 · sopra 12 | su `bg/surface`, `radius/md` |
| 8 | Home indicator | 34 | bianco |

### Banner notifica · variante `compressa`

- padding 16
- riga superiore 20: icona app 20 × 20 `radius/sm` + `Dispensa` (`Caption Strong`) + `ora` a destra (`Micro`)
- titolo `Title 3`: `Mozzarella: scade domani`
- corpo `Body` `text/secondary`, 2 righe massimo

### Banner notifica · variante `espansa`

- riga superiore 20 come nella variante compressa (icona app 20 × 20 + `Dispensa` + `ora`)
- titolo `Cosa vuoi fare?` `Body Strong`, sopra 8
- tre righe azione, altezza 44, gap 8:
  - `Cucina la ricetta` — `primary` pieno
  - `Più tardi (stasera)` — `secondary`
  - `L'ho buttata` — `secondary` con testo `text/destructive`
- nota `Scadenza sbagliata? Si corregge dalla scheda prodotto.` `Micro` `text/tertiary`

### Stati da disegnare

1. `compressa` — solo il banner piccolo, con il banner espanso assente: è lo stato in cui l'utente arriva.
2. `espansa` — entrambi i banner, è lo stato dopo il tocco.

### Note di fedeltà

- L'interruttore `Nascondi i dettagli sul blocco schermo` è dentro il banner espanso, non in una schermata
  separata: è una scelta dell'utente presa nel momento in cui ha il problema (vincolo E24).
- Non disegnare altre notifiche sullo sfondo: la promessa è «nessun'altra notifica per oggi».

---

# S06 · Ricette

**Frame** `S06 · Ricette` · 390 × 844

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | titolo `Cosa posso cucinare`, sottotitolo `Solo con ciò che hai in casa` |
| 3 | Etichetta sezione | 20 · sopra 16 | `2 RICETTE POSSIBILI ORA` |
| 4 | Card ricetta grande | 2 × 128 · gap 12 | `CardRicetta` variante `grande` |
| 5 | Etichetta sezione | 20 · sopra 24 | `CON 1 INGREDIENTE DA COMPRARE` |
| 6 | Card ricetta tratteggiata | 72 · sopra 8 | `CardRicetta` variante `parziale` |
| 7 | Etichetta sezione | 20 · sopra 24 | `USANO PRODOTTI IN SCADENZA` |
| 8 | Riga ricetta | 64 · sopra 8 | `CardRicetta` variante `riga` |
| 9 | Tab bar | 56 | tab attiva: `Ricette` |

### CardRicetta · variante `grande`

- padding 16, `radius/md`, `elev/1`
- immagine segnaposto 72 × 72 a sinistra, `radius/sm`
- a destra, larghezza 100% − 88:
  - titolo `Title 3`
  - riga meta: `Pronta · usa 1 prodotto in scadenza` (`Caption`, `text/secondary`), 1 riga
  - riga tag: `10 min` (con icona `clock`) + `salva spreco` — pillole `bg/surface-sunken`, altezza 22
  - nota `Nessun ingrediente da comprare` (`Caption`, `text/secondary`)
- `chevron-right` a destra, allineato al centro verticale
- **tutta la card è toccabile** (vincolo E27)

### Note di fedeltà

- La variante `parziale` ha sfondo trasparente, bordo tratteggiato `border/control`, testo non in grassetto:
  deve sembrare **un'altra categoria**, non una card disabilitata (vincolo E29).
- La scritta `usa 1 prodotto in scadenza` resta con «usa» perché è una frase descrittiva, non un pulsante.

---

# S07 · Spreco

**Frame** `S07 · Spreco` · 390 × 844

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | titolo `Spreco`, sottotitolo `Novembre 2026`, destra `Mese >` |
| 3 | Riquadro valore | 108 · sopra 16 | `radius/md`, `bg/surface`, `elev/1` |
| 4 | Etichetta + grafico | 20 + 160 · sopra 24 | `ANDAMENTO (6 MESI)` |
| 5 | Etichetta sezione | 20 · sopra 24 | `COSA HO BUTTATO` |
| 6 | Righe spreco | 4 × 56 · gap 8 | `RigaSpreco` |
| 7 | Nota finale | 76 · sopra 16 | sfondo `bg/surface-sunken`, `radius/md` |
| 8 | Tab bar | 56 | tab attiva: `Spreco` |

### Grafico

- 6 barre verticali, larghezza 28, gap 24, altezze proporzionali
- i mesi passati: `grey/300`; il mese corrente: `accent/urgent`
- etichette mesi sotto le barre, `Micro`, `text/tertiary`
- **aggiungi le etichette dei valori sopra ogni barra** (`€ 10,30`, `€ 7,20`, `€ 8,40`, `€ 5,40`, `€ 6,60`, `€ 6,40`):
  la Fase 3 ha rilevato che senza scala il grafico non comunica nulla (vincolo E31)

### Note di fedeltà

- Nessun badge, nessun premio, nessuna serie positiva. Il prodotto misura, non giudica.
- Il confronto `-38% vs ottobre` usa `text/success` solo perché il segno è negativo (spreco in calo).

---

# S08 · Scheda prodotto (nuova)

**Frame** `S08 · Scheda prodotto` · 390 × 844

Non ha wireframe di riferimento: nasce dalla Fase 3 per sbloccare sette problemi rinviati.

### Struttura

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | sinistra `Indietro`, destra `Modifica` |
| 3 | Intestazione | 120 · sopra 16 | nome `Title 1`, etichetta `SCADE DOMANI`, immagine segnaposto 64 × 64 a destra |
| 4 | Blocco dati | 3 × 56 · gap 8 · sopra 24 | righe chiave/valore: `Quantità · 1 confezione`, `Scadenza · 14 nov 2026`, `Dove · Frigo` |
| 5 | Pulsante principale | 52 · sopra 24 | `Cucina con questo prodotto` |
| 6 | Pulsante secondario | 44 · sopra 8 | `Sposta la scadenza` |
| 7 | Pulsante secondario | 44 · sopra 8 | `Segna come finito` |
| 8 | Pulsante distruttivo | 44 · sopra 8 | `Non ricordarmelo`, testo `text/destructive` |
| 9 | Nota | 36 · sopra 8 | `«Non ricordarmelo» toglie l'avviso ma non cancella il prodotto.` |

### Note di fedeltà

- Questa schermata è la destinazione dei rinvii E06, E16, E20, E22, E26. Le quattro azioni in fondo
  corrispondono a quei quattro problemi.
- `Modifica` in app bar trasforma i campi in modificabili (stato 2).

### Stati da disegnare

1. `lettura` — come sopra.
2. `modifica` — i tre campi hanno bordo `grey/900`, l'app bar a destra mostra `Fine`.

---

# S09 · Dettaglio ricetta (nuova)

**Frame** `S09 · Dettaglio ricetta` · 390 × 844

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | sinistra `Indietro` |
| 3 | Immagine di copertina | 200 · sotto app bar | segnaposto `bg/surface-sunken` |
| 4 | Titolo | 34 · sopra 20 | `Title 1` |
| 5 | Meta | 20 · sopra 8 | `10 min · 2 persone` con icone `clock` e `users` |
| 6 | Etichetta sezione | 20 · sopra 24 | `INGREDIENTI CHE HAI` |
| 7 | Righe ingrediente | 4 × 44 · gap 4 | nome + segno di spunta `check` a destra, `text/success` |
| 8 | Etichetta sezione | 20 · sopra 24 | `PROCEDIMENTO` |
| 9 | Passi | 3 × 64 · gap 12 | numero in cerchio `bg/surface-sunken` + testo `Body` |
| 10 | Pulsante fisso in basso | 52 · a 16 dal fondo | `Ho cucinato: scala dalla dispensa`, `primary` |

---

# S10 · Spreco, dettaglio mese (nuova)

**Frame** `S10 · Spreco · dettaglio mese` · 390 × 844

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | sinistra `Indietro`, titolo `Novembre 2026` |
| 3 | Valore grande | 80 · sopra 16 | `€ 6,40` `Display` |
| 4 | Confronto | 24 | `Ottobre: € 10,30` `Body` `text/secondary` |
| 5 | Grafico mensile | 180 · sopra 24 | barre dei singoli sprechi del mese |
| 6 | Etichetta sezione | 20 · sopra 24 | `COSA HO BUTTATO` |
| 7 | Righe | 4 × 56 · gap 8 | `RigaSpreco` |
| 8 | Nota | 36 · sopra 16 | `Il confronto compare solo dal secondo mese di utilizzo.` |

---

# S11 · Dispensa vuota (nuova)

**Frame** `S11 · Dispensa vuota` · 390 × 844

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | titolo `Dispensa` |
| 3 | Illustrazione | 160 · sopra 80 | segnaposto: cerchio `bg/surface-sunken` 120 con icona `package` 48 |
| 4 | Titolo | 34 · sopra 24 | `La dispensa è vuota`, centrato |
| 5 | Testo | 44 · sopra 8 | `Aggiungi il primo prodotto: bastano due tocchi.` centrato, `Body` |
| 6 | Pulsante | 52 · sopra 24 | `Aggiungi un prodotto` |
| 7 | Nota | 36 · sopra 12 | `Le ricette compariranno appena ci sarà qualcosa da cucinare.` |
| 8 | Tab bar | 56 | tab attiva: `Dispensa` |

**Regola:** nessuna schermata del prodotto usa il testo «Nessun risultato». Gli stati vuoti spiegano
**perché** sono vuoti e **cosa fare**.

---

# S12 · Primo utilizzo (nuova)

**Frame** `S12 · Primo utilizzo` · 390 × 844

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | Illustrazione | 200 · sopra 40 | segnaposto |
| 3 | Titolo | 68 · sopra 32 | `Benvenuto in Dispensa` su due righe |
| 4 | Testo | 66 · sopra 12 | `Registra quello che compri e ti diciamo cosa cucinare prima che scada.` |
| 5 | Passi | 3 × 56 · gap 8 · sopra 32 | numero + testo, sfondo `bg/surface`, `radius/md` |
| 6 | Pulsante | 52 · a 16 dal fondo sopra la safe area | `Aggiungi il primo prodotto` |
| 7 | Nota | 36 · sopra 8 | `I suggerimenti compariranno dal secondo prodotto.` |

**Nota delicata:** questo passo 7 dichiara il limite più grande del prodotto (senza storico i suggerimenti
non ci sono). È una scelta: meglio dirlo che farlo scoprire.

---

# S13 · Impostazioni notifiche (nuova)

**Frame** `S13 · Impostazioni notifiche` · 390 × 844

| # | Blocco | Misura | Note |
|---|---|---|---|
| 1 | Status bar | 59 | |
| 2 | App bar | 56 | sinistra `Indietro`, titolo `Notifiche` |
| 3 | Gruppo voci | 4 × 72 · gap 1 | sfondo `bg/surface`, separatori `border/subtle` |
| 4 | Nota finale | 36 · sopra 16 | `Al massimo una notifica al giorno per prodotto.` |

### Voci

| Voce | Tipo | Secondaria |
|---|---|---|
| `Avvisi di scadenza` | interruttore (attivo) | `Un giorno prima, uno per prodotto` |
| `Nascondi i dettagli sul blocco schermo` | interruttore (attivo) | `Mostra solo «Hai una scadenza»` |
| `Riepilogo settimanale` | interruttore (spento) | `La domenica, cosa scade nei prossimi 7 giorni` |
| `Orario degli avvisi` | valore con `chevron-right` | `18:00` |

---

## Riepilogo: quante schermate per priorità

| Priorità | Schermate | Numero |
|---|---|---|
| P0 | S01, S02, S03, S04 | 4 |
| P1 | S05, S06, S07, S08, S09, S11 | 6 |
| P2 | S10, S12, S13 | 3 |

Se il tempo non basta per tutte e 13, si fermano a P1 e il prototipo resta usabile per uno user test.
