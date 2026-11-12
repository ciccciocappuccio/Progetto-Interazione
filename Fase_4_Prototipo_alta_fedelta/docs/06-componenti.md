# Inventario dei componenti

Il catalogo definisce i componenti e le varianti previsti per il sistema dell’interfaccia. Eventuali componenti aggiuntivi richiedono una motivazione progettuale e un aggiornamento coerente del catalogo.

**Priorità:** P0 = componenti necessari per la Home e il flusso essenziale. P1 = componenti per le altre schermate P0/P1.
P2 = componenti delle schermate di completamento.

---

## P0 — Base

### 1. `AppBar`

| Proprietà | Valori |
|---|---|
| `variante` | `principale` · `con-sottotitolo` · `modale` |
| `azione-sinistra` | `nessuna` · `indietro` · `chiudi` · `annulla` |
| `azione-destra` | `nessuna` · `testo` · `icona` |
| `testo-sinistra` | text |
| `testo-destra` | text |

Altezza 56. Titolo `Title 1` se variante `principale`, `Title 3` se `con-sottotitolo` con sottotitolo `Caption`.
Azione sinistra sempre a 16 dalla sinistra; azione destra sempre a 16 dalla destra.
In `modale` il titolo è centrato.

### 2. `TabBar`

| Proprietà | Valori |
|---|---|
| `attiva` | `Oggi` · `Dispensa` · `Ricette` · `Spreco` |

Altezza 56 sopra la safe area. 4 voci equidistanti. Icona 24 + etichetta `Micro` 11.
Attiva: `icon/primary` + `text/primary`. Inattiva: `icon/secondary` + `text/tertiary`.

### 3. `Button`

| Proprietà | Valori |
|---|---|
| `variante` | `primary` · `secondary` · `testo` · `destructive` |
| `dimensione` | `lg` (52) · `md` (44) · `sm` (36) · `xs` (32) |
| `larghezza` | `auto` · `piena` |
| `icona` | `nessuna` · `sinistra` · `destra` |
| `stato` | `default` · `premuto` · `disabilitato` |

- `primary`: sfondo `action/primary-bg`, testo `action/primary-text`, `radius/md`
- `secondary`: sfondo `bg/surface`, bordo `border/control` 1 px, testo `text/primary`
- `testo`: nessuno sfondo, testo `text/primary`
- `destructive`: sfondo `bg/surface`, testo `text/destructive`

### 4. `ChipFiltro`

| Proprietà | Valori |
|---|---|
| `stato` | `attiva` · `inattiva` |
| `con-conteggio` | booleano |

Altezza 36, `radius/full`, padding orizzontale 14.
Attiva: sfondo `action/primary-bg`, testo `action/primary-text`.
Inattiva: sfondo `bg/surface`, bordo `border/control`, testo `text/secondary`.

### 5. `EtichettaStato`

| Proprietà | Valori |
|---|---|
| `tipo` | `scadenza` · `tempo` · `neutra` |

Altezza 22, `radius/sm`, padding orizzontale 8, `Caption Strong` maiuscolo.
- `scadenza`: `bg/warning` + `text/warning`, bordo `border/warning` 1 px
- `tempo`: `bg/surface-sunken` + `text/secondary` (con icona `clock`)
- `neutra`: `bg/surface-sunken` + `text/secondary`

### 6. `CardPrioritaria`

Altezza 148, padding 16, `radius/md`, `elev/1`, sfondo `bg/surface`, bordo `border/warning` 1 px.
Contiene: `EtichettaStato` `scadenza`, titolo `Title 3`, sottotitolo, riga con `Button primary sm` +
`Button secondary sm`, e un collegamento testo con `chevron-right`.

| Proprietà | Valori |
|---|---|
| `con-altri` | booleano (mostra «Ne scadono altri n oggi») |

### 7. `RigaProdotto`

| Proprietà | Valori |
|---|---|
| `variante` | `estesa` (72) · `compatta` (64) · `suggerimento` (56) |
| `con-azione-cucina` | booleano |

Contenuto: segnaposto immagine 40 × 40 `radius/sm` · nome · metadati · a destra icona `pencil` e,
se `con-azione-cucina`, `Button primary xs`.
- `estesa`: nome `Title 3`, metadati `Caption`, sfondo `bg/surface`, `radius/md`
- `compatta`: nome `Body Strong`, solo icona `pencil`, separatore sotto
- `suggerimento`: senza immagine, a destra il luogo in `Caption`, `chevron-right` assente

### 8. `RiquadroSpreco`

Altezza 72, padding 16, `radius/md`, sfondo `bg/surface-sunken`.
Due righe: `Spreco questo mese` (`Caption`) + `€ 6,40 · 4 prodotti` (`Body Strong`), a destra `dettagli >`.

### 9. `Fab`

52 × 52, `radius/full`, sfondo `action/primary-bg`, icona `plus` 24 bianca, `elev/2`.
Etichetta `Aggiungi` sotto, `Micro`, `text/secondary`.

---

## P1 — Schermate interne

### 10. `CampoRicerca`

| Proprietà | Valori |
|---|---|
| `stato` | `inattivo` · `attivo` · `compilato` |
| `con-azione` | booleano |

Altezza 48 (52 se attivo), `radius/md`. Icona `search` 20 a sinistra.
Inattivo: bordo `border/control` 1 px. Attivo: bordo `grey/900` 2 px.
Azione a destra in `Caption` (`filtri`, `cambia`).

### 11. `CampoQuantita`

Altezza 48. `−` 40 × 40, valore 40 × 40 al centro (`Body Strong`), `2` 40 × 40, `+` 40 × 40,
tutti `radius/sm` bordo `border/control`; il valore selezionato ha sfondo `bg/surface-sunken`.
Testo `confezione` a destra in `Body` `text/secondary`.

### 12. `CampoData`

Altezza 52, `radius/md`, bordo `border/control`, icona `calendar` a sinistra se c'è spazio,
valore `Body Strong` e azione `cambia` a destra in `Caption Strong`.

### 13. `ChipLuogo`

Come `ChipFiltro` ma con icona opzionale a sinistra (`refrigerator`, `snowflake`, `package`).
Altezza 40.

### 14. `CardRicetta`

| Proprietà | Valori |
|---|---|
| `variante` | `orizzontale` (88) · `grande` (128) · `parziale` (72) · `riga` (64) |
| `con-tag-spreco` | booleano |

- `orizzontale`: altezza 88, padding 12, `radius/md`, `elev/1`. SegnapostoImmagine 40 × 40 a sinistra; a destra titolo `Title 3` su 1 riga, sottotitolo `Caption` su 1 riga; `chevron-right` 24 a 16 dalla destra. **Tutta toccabile** (E27).
- `grande`: immagine 72 × 72, titolo `Title 3`, meta, tag, nota, `chevron-right`. Tutta toccabile.
- `parziale`: bordo tratteggiato `border/control`, senza immagine, testo non grassetto.
- `riga`: come la compatta, con `chevron-right`.

### 15. `BannerNotifica`

| Proprietà | Valori |
|---|---|
| `stato` | `compressa` (116) · `espansa` (232) |

Intestazione con icona app 20, `Dispensa`, `ora`.
Nella variante `espansa`: titolo `Cosa vuoi fare?`, tre `Button` a larghezza piena (44) e nota.

### 16. `Interruttore`

44 × 26, `radius/full`. Attivo: `action/primary-bg` con pallino a destra. Spento: `border/control` con pallino a sinistra.
Con etichetta (`Body Strong`) e descrizione (`Caption`) facoltative a sinistra.

### 17. `RigaSpreco`

Altezza 56. Segnaposto 32 × 32, nome `Body Strong`, a destra `2 nov · € 2,80` in `Caption`.

### 18. `GraficoBarre`

| Proprietà | Valori |
|---|---|
| `numero-barre` | 6 · 12 |
| `con-valori` | booleano |

Barre larghe 28, gap 24, `radius/sm` 4 sopra, etichette mese sotto.
Con `con-valori`: valore in `Micro` sopra ogni barra.

### 19. `RiquadroInformativo`

Sfondo `bg/surface-sunken`, `radius/md`, padding 16.
Titolo `Body Strong` + testo `Body`/`Caption`. Usato per «Cosa riceverai» e per le note in fondo alle schermate.

### 20. `RigaImpostazione`

Altezza 72. Titolo `Body Strong`, descrizione `Caption`, controllo a destra (interruttore o valore + `chevron-right`).

---

## P2 — Completamento

### 21. `SegnapostoImmagine`

| Proprietà | Valori |
|---|---|
| `dimensione` | `sm` (32) · `md` (40) · `lg` (72) · `xl` (200) |

Rettangolo `bg/surface-sunken` con `radius/sm`, icona `image` al centro in `icon/secondary`.

### 22. `StatoVuoto`

Illustrazione (cerchio `bg/surface-sunken` + icona) + titolo `Title 2` + testo + `Button`.
Usato in S11.

### 23. `PassoNumerato`

Cerchio 28 `bg/surface-sunken` con numero `Caption Strong` + testo `Body`.

| Variante | Altezza | Descrizione |
|---|---|---|
| `inline` | 64 | solo cerchio e testo, usato in S09 |
| `card` | 56 | riquadro pieno `bg/surface`, `radius/md`, usato in S12 |

### 24. `RigaIngrediente`

Altezza 44. Nome `Body`, a destra icona `check` in `text/success`.

---

## Criteri di realizzazione

1. I componenti sono raccolti nella pagina `01 · Design system`, in una griglia con etichette.
2. Le varianti adottano i nomi in italiano indicati, per esempio `variante=estesa`.
3. I contenuti variabili nelle istanze sono gestiti tramite proprietà di testo.
4. L'Auto layout utilizza le variabili `layout/*`. Il posizionamento assoluto è riservato a FAB, banner di notifica e pulsanti fissi in basso.
5. I componenti orizzontali adottano il vincolo di larghezza `fill container`.
6. I livelli hanno nomi in italiano e descrittivi, come `Titolo`, `Sottotitolo` e `Azione`.
