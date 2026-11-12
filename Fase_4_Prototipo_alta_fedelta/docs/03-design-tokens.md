# Design token

Il documento raccoglie i valori misurabili del sistema visivo. Le eventuali discrepanze o lacune sono da trattare come decisioni progettuali e registrare nel documento delle questioni aperte.

Due collezioni di variabili:

- **Primitives** — valori grezzi, nomi descrittivi, nessun uso diretto nei livelli.
- **Semantic** — alias verso Primitives, sono quelli che si applicano ai livelli.

---

## 1. Colori

La Fase 2 e la Fase 3 sono state condotte in scala di grigi di proposito. Ora il colore entra con
una sola responsabilità: **distinguere ciò che scade da ciò che va bene**. Il resto dell'interfaccia
resta neutro, perché l'utente guarda l'app di fretta e un'interfaccia colorata ovunque non ha gerarchia.

### 1.1 Primitives · scala neutra

| Variabile | Hex | Uso |
|---|---|---|
| `grey/0` | `#FFFFFF` | superfici, testi su scuro |
| `grey/50` | `#FAFAFA` | sfondo di pagina |
| `grey/100` | `#F4F4F5` | superfici secondarie, riempimenti |
| `grey/200` | `#E7E7E9` | bordi tenui, separatori |
| `grey/300` | `#D1D1D6` | bordi di controllo |
| `grey/400` | `#A8A8AE` | testo disabilitato, icone spente |
| `grey/500` | `#7A7A82` | testo terziario, didascalie |
| `grey/600` | `#5A5A62` | testo secondario |
| `grey/700` | `#3A3A40` | testo su superfici chiare, forte |
| `grey/900` | `#1C1C1E` | testo primario |

### 1.2 Primitives · colore di stato

Un solo colore d'accento, caldo, legato al cibo e non all'allarme. L'ambra segnala urgenza senza
spaventare: è il colore di ciò che sta per scadere.

| Variabile | Hex | Uso |
|---|---|---|
| `amber/50` | `#FEF6E7` | sfondo di avviso |
| `amber/200` | `#F6D9A0` | bordo di avviso |
| `amber/500` | `#E39A21` | accento, indicatore di scadenza |
| `amber/700` | `#9A6410` | testo su fondo ambra chiaro |
| `green/50` | `#EDF6EE` | sfondo di conferma, spreco in calo |
| `green/600` | `#3C7D45` | testo di conferma |
| `red/50` | `#FCEDEC` | sfondo di azione distruttiva |
| `red/600` | `#B3352C` | testo e icona di azione distruttiva |

### 1.3 Semantic · colori

| Variabile | Alias | Dove si usa |
|---|---|---|
| `bg/canvas` | `grey/50` | sfondo di tutte le schermate |
| `bg/surface` | `grey/0` | card, app bar, tab bar |
| `bg/surface-sunken` | `grey/100` | riquadri interni, chip inattive, immagini segnaposto |
| `bg/warning` | `amber/50` | card di prodotto in scadenza |
| `bg/success` | `green/50` | nota di spreco in calo |
| `bg/destructive` | `red/50` | sfondo di «L'ho buttato» premuto |
| `text/primary` | `grey/900` | titoli, nomi prodotto |
| `text/secondary` | `grey/600` | sottotitoli, metadati |
| `text/tertiary` | `grey/500` | didascalie, note |
| `text/on-accent` | `grey/0` | testo su pulsante pieno |
| `text/warning` | `amber/700` | etichetta «SCADE DOMANI» |
| `text/success` | `green/600` | «-38% vs ottobre» quando è negativo |
| `text/destructive` | `red/600` | «L'ho buttato» |
| `border/subtle` | `grey/200` | separatori, bordi di card |
| `border/control` | `grey/300` | bordi di campi e chip |
| `border/warning` | `amber/200` | bordo della card in scadenza |
| `icon/primary` | `grey/700` | icone attive |
| `icon/secondary` | `grey/500` | icone inattive |
| `action/primary-bg` | `grey/900` | sfondo del pulsante principale |
| `action/primary-text` | `grey/0` | testo del pulsante principale |
| `accent/urgent` | `amber/500` | pallino di scadenza, barra del grafico del mese corrente |

**Regola:** nessun livello usa un `grey/*` o `amber/*` direttamente. Solo variabili `Semantic`.
Eventuali colori aggiuntivi richiedono una decisione progettuale e una verifica di coerenza con la gerarchia visiva.

---

## 2. Tipografia

Famiglia: **Inter** (disponibile su Figma e gratuita). Se non è disponibile, `SF Pro` su iOS.
Non usare altri font.

| Stile | Peso | Dimensione | Interlinea | Tracking | Uso |
|---|---|---|---|---|---|
| `Display` | Bold | 34 | 40 | −1% | «€ 6,40» nello Spreco |
| `Title 1` | Bold | 28 | 34 | −1% | titolo di schermata («Dispensa») |
| `Title 2` | Bold | 22 | 28 | −0.5% | nome prodotto nella scheda |
| `Title 3` | Semibold | 17 | 22 | 0 | titolo di card, nome nella riga della dispensa |
| `Body` | Regular | 15 | 22 | 0 | testo corrente, campi |
| `Body Strong` | Semibold | 15 | 22 | 0 | etichette di pulsante, valori |
| `Caption` | Regular | 13 | 18 | 0 | metadati, didascalie |
| `Caption Strong` | Semibold | 13 | 18 | 0.2% | «SCADE DOMANI», etichette di sezione |
| `Micro` | Regular | 11 | 14 | 0.4% | note minime, «oggi», contatori |

**Regole.**
- Mai sotto 11 px. In cucina, in piedi, con luce scarsa, sotto gli 11 non si legge.
- Le etichette di sezione (`Caption Strong`) sono **maiuscole** e hanno 0.2% di tracking.
- Nessun corsivo: non esiste in questo prodotto.
- I numeri grandi (euro, date) usano cifre tabulari se il font le offre.

---

## 3. Spaziature

Scala a 4 con nomi: `space/0` = 0, `space/1` = 4, `space/2` = 8, `space/3` = 12, `space/4` = 16,
`space/5` = 20, `space/6` = 24, `space/8` = 32, `space/10` = 40, `space/12` = 48.

Valori d'uso ricorrenti (sono alias, creali come variabili `layout/*`):

| Variabile | Valore | Dove |
|---|---|---|
| `layout/screen-margin` | 16 | margine laterale su tutte le schermate |
| `layout/card-padding` | 16 | padding interno delle card |
| `layout/card-gap` | 12 | distanza fra card in una lista |
| `layout/section-gap` | 24 | distanza fra sezioni |
| `layout/appbar-height` | 56 | altezza dell'app bar (sotto la status bar) |
| `layout/tabbar-height` | 56 | altezza della tab bar (sotto la safe area) |
| `layout/fab-size` | 52 | diametro del FAB |
| `layout/touch-target` | 44 | dimensione minima di qualsiasi area toccabile |

### 3.1 Altezze standard dei controlli

Una regola unica, per non ritrovare ogni volta lo stesso errore:

| Tipo | Altezza | Dove |
|---|---|---|
| Campi (ricerca, quantità, data, testo) | **48** | sempre, attivo o inattivo che sia. Il bordo 2 px dell'attivo sta *dentro* i 48. |
| Pulsanti che chiudono un modulo (Salva, Avanti, Aggiungi) | **52** | in fondo a una schermata, a 16 dal fondo |
| Pulsanti che agiscono nel contenuto (Cucina, Sposta la scadenza) | **44** | dentro card, righe, banner |
| Pulsanti dentro card e righe (Cucina ora, L'ho buttato) | **36** | card prioritaria, righe estese |
| Pulsanti mini (Modifica icona, azioni in riga) | **32** | dove c'è già un'icona a lato |

---

## 4. Raggi

| Variabile | Valore | Uso |
|---|---|---|
| `radius/sm` | 8 | chip, campi, pulsanti piccoli |
| `radius/md` | 12 | card, pulsanti principali |
| `radius/lg` | 20 | banner di notifica, sheet |
| `radius/full` | 999 | FAB, pallini, interruttori, chip a pillola |

---

## 5. Elevazioni

Solo due, e sono leggere: il prodotto è piatto, la profondità serve a separare i piani, non a decorare.

| Variabile | Valore | Uso |
|---|---|---|
| `elev/1` | `0 1 2 rgba(28,28,30,0.06)` | card, app bar al scroll |
| `elev/2` | `0 8 24 rgba(28,28,30,0.12)` | FAB, banner di notifica, sheet |

---

## 6. Icone

Set: **Lucide** (gratuito, coerente, disponibile come plugin Figma). Spessore tratto 1.5 px, griglia 24 px,
colore sempre da `icon/primary` o `icon/secondary`.

Icone effettivamente necessarie (non aggiungerne altre):

| Icona Lucide | Dove |
|---|---|
| `plus` | FAB |
| `chevron-right` | righe navigabili, card ricetta |
| `chevron-left` | app bar, indietro |
| `x` | app bar, chiudi |
| `search` | app bar Dispensa |
| `bell` | tab Notifiche in app bar Home |
| `pencil` | «Modifica» nella riga della Dispensa (E35) |
| `utensils` | tab Ricette, pulsante «Cucina» |
| `refrigerator` | luogo Frigo |
| `snowflake` | luogo Freezer |
| `package` | luogo Dispensa |
| `trash-2` | tab Spreco, «L'ho buttato» |
| `clock` | tempo di preparazione |
| `calendar` | campo scadenza |
| `eye-off` | interruttore privacy notifica |
| `check` | conferma |
| `users` | meta della ricetta (S09: «2 persone») |
| `home` | tab Oggi |
| `more-horizontal` | solo dove indispensabile |

Le quattro icone della tab bar sono queste, in questo ordine:
`home` → Oggi · `package` → Dispensa · `utensils` → Ricette · `trash-2` → Spreco.

I nomi dei luoghi (`Frigo`, `Freezer`, `Dispensa`, `Cantina`) hanno sempre l'**icona e la parola insieme**:
l'icona da sola non è comprensibile per «Cantina», quindi la parola resta.
