# Contenuti e microtesti

Il documento definisce i testi dell’interfaccia e le regole di microcopy. La Fase 3 ha evidenziato che i difetti principali
di questo prodotto erano di **parole**, non di layout: questo file è quindi un vincolo, non un elenco
di suggerimenti.

---

## 1. Regole di scrittura

1. **Seconda persona singola**, informale ma non confidenziale. Mai «l'utente», mai «noi».
2. **Verbo prima di tutto.** I pulsanti sono verbi: «Cucina», «Salva», «Modifica». Mai «OK», «Conferma»,
   «Procedi».
3. **Mai il gergo tecnico.** Non «elemento», «record», «item». Sono «prodotti».
4. **Frasi brevi.** Massimo 12 parole per riga visibile. Se serve una seconda riga, forse serve un'altra schermata.
5. **Il verbo dell'azione centrale è «Cucina».** Sempre, in tutte le schermate. Mai «usa», «Apri», «Prepara».
6. **La quantificazione dello spreco è in euro**, non in chili e non in «punti».
7. **Nessun tono colpevolizzante.** Non «hai buttato», «hai sprecato». Sì «L'ho buttato» (dichiarazione
   dell'utente, non accusa del sistema) e «Il 70% dello spreco nasce da…» (osservazione).

---

## 2. Nomi ricorrenti (usali identici, sempre)

| Concetto | Testo | Note |
|---|---|---|
| I prodotti dell'utente | **Dispensa** | con la maiuscola quando indica la sezione, minuscola quando indica il mobile di casa |
| Luoghi | **Frigo · Freezer · Dispensa · Cantina** | in quest'ordine, sempre |
| Azione centrale | **Cucina** | verbo, mai sostantivo |
| Scadenza imminente | **SCADE OGGI / SCADE DOMANI / SCADE FRA {n} GG** | maiuscolo, è un'etichetta di stato |
| Sezione della Home | **IN SCADENZA QUESTA SETTIMANA** | |
| Sezione della Home | **COSA CUCINO STASERA** | |
| Misura | **Buttato questo mese** | |
| Azione distruttiva | **L'ho buttato** | nella Home e nella notifica: «L'ho buttata» se il prodotto è femminile |

---

## 3. Dati di esempio (usali così, non cambiarli)

I numeri sono coerenti fra le schermate: se cambi un valore in una, va cambiato ovunque.

| Prodotto | Luogo | Quantità | Scadenza | Valore |
|---|---|---|---|---|
| Mozzarella | Frigo | 1 conf. | domani (14 nov) | € 2,80 |
| Yogurt bianco | Frigo | 2 conf. | oggi (13 nov) | € 0,80 |
| Petto di pollo | Frigo | 400 g | fra 2 gg (15 nov) | € 3,40 |
| Insalata | Frigo | 1 busta | fra 3 gg (16 nov) | € 1,20 |
| Parmigiano | Frigo | 150 g | 20 nov | € 4,10 |
| Basilico | Frigo | 1 vasetto | 18 nov | € 0,90 |
| Pasta secca | Dispensa | 2 conf. | 2027 | € 1,30 |
| Passata | Dispensa | 3 conf. | 2028 | € 0,85 |
| Riso | Dispensa | 1 kg | 2027 | € 2,10 |
| Uova | Frigo | 6 | 25 nov | € 2,60 |
| Pane casereccio | Dispensa | 1 | domani | € 1,60 |

**Totali coerenti con il resto del prototipo:**

- prodotti in dispensa: **24** (Frigo 11 · Freezer 3 · Dispensa 10)
- in scadenza entro 7 giorni: **12**, di cui **3 oggi** (yogurt, mozzarella, pollo)
- spreco del mese: **€ 6,40 · 4 prodotti**, con **−38% vs ottobre**
- data di oggi nel prototipo: **mercoledì 13 novembre 2026**, ore **9:41**

---

## 4. Testi schermata per schermata

### S01 · Home

| Elemento | Testo |
|---|---|
| App bar, titolo | `Ciao Marco` |
| App bar, azione destra | `Notifiche` |
| Etichetta data | `OGGI, MERCOLEDÌ` |
| Card prioritaria, etichetta | `SCADE DOMANI` |
| Card prioritaria, titolo | `Mozzarella (1 conf.)` |
| Card prioritaria, sottotitolo | `Apri il frigo: la usi stasera?` |
| Card prioritaria, azione 1 | `Cucina ora` |
| Card prioritaria, azione 2 | `L'ho buttato` |
| Card prioritaria, nota | `Ne scadono altri 2 oggi` |
| Sezione 2, etichetta | `COSA CUCINO STASERA` |
| Card ricetta, titolo | `Pasta pomodoro e mozzarella` |
| Card ricetta, sottotitolo | `3 ricette pronte con ciò che hai` |
| Card ricetta, azione | `Vedi ricette (3)` |
| Sezione 3, etichetta | `IN SCADENZA QUESTA SETTIMANA` |
| Righe | `Yogurt (2) · oggi` · `Petto di pollo · fra 2 gg` · `Insalata · fra 3 gg` |
| Azione sezione | `Vedi tutti quelli in scadenza (12)` |
| Riquadro spreco | `Spreco questo mese` / `€ 6,40 · 4 prodotti` / `dettagli >` |
| FAB | `Aggiungi` |

### S02 · Aggiunta, passo 1

| Elemento | Testo |
|---|---|
| App bar, titolo | `Aggiungi prodotto` |
| App bar, sinistra | `Chiudi` |
| App bar, destra | `Salva` |
| Avanzamento | `Passo 1 di 2` |
| Campo | `Cerca o scrivi: «mozzarella»` |
| Etichetta sezione | `SUGGERITI (DALLA TUA DISPENSA)` |
| Voci | `Mozzarella` · `Mozzarella di bufala` · `Latte intero` · `Pasta secca` · `Parmigiano` |
| Voce di creazione | `Crea «mozzarella»` |
| Nota | `Un tocco e il prodotto è scelto` |
| Pulsante | `Avanti` |
| Didascalia | `Salva subito, senza dettagli (in alto a destra)` |

### S03 · Aggiunta, passo 2

| Elemento | Testo |
|---|---|
| App bar, titolo | `Mozzarella` |
| App bar, sinistra | `Annulla` |
| Avanzamento | `Passo 2 di 2` |
| Etichetta | `QUANTITÀ` |
| Controllo | `−` `1` `2` `+` e accanto `confezione` |
| Etichetta | `SCADENZA` |
| Campo | `14 nov 2026` con azione `cambia` |
| Didascalia | `stima predefinita: +7 giorni` |
| Etichetta | `DOVE` |
| Chip | `Frigo` (attiva) · `Freezer` · `Dispensa` · `Cantina` |
| Riquadro | `Cosa riceverai` |
| Testo riquadro | `1 notifica, il giorno prima della scadenza:` |
| Esempio notifica | `«La mozzarella scade domani, usala stasera»` |
| Nota | `Puoi correggere tutto anche dopo, dalla scheda del prodotto.` |
| Pulsante | `Salva in dispensa` |

### S04 · Dispensa

| Elemento | Testo |
|---|---|
| App bar, titolo | `Dispensa` |
| App bar, sottotitolo | `Ordinati per data di scadenza` |
| App bar, destra | `Cerca` |
| Chip | `Tutti (24)` attiva · `Frigo (11)` · `Freezer (3)` · `Dispensa (10)` |
| Campo ricerca | `Cerca nella dispensa` |
| Azione campo | `filtri` |
| Sezione | `SCADONO PRESTO` |
| Azioni riga | `Modifica` (icona matita) · `Cucina` (pulsante) |
| Sezione | `TUTTO IL RESTO (9)` |
| Azione riga | `Modifica` (icona matita) |
| Conteggio finale | `24 prodotti in tutto` |
| FAB | `Aggiungi` |

### S05 · Notifica

| Elemento | Testo |
|---|---|
| Intestazione | `Dispensa` · `ora` |
| Titolo | `Mozzarella: scade domani` |
| Corpo | `Stasera: pasta con pomodoro e basilico. Tocca per la ricetta.` |
| Azione 1 (principale) | `Cucina la ricetta` |
| Azione 2 | `Più tardi (stasera)` |
| Azione 3 | `L'ho buttata` |
| Nota | `Scadenza sbagliata? Si corregge dalla scheda prodotto.` |
| Promessa | `Nessun'altra notifica per oggi` |
| Interruttore | `Nascondi i dettagli sul blocco schermo` |
| Spiegazione interruttore | `Mostra solo «Hai una scadenza»` |
| Stato interruttore | `attivo` |

### S06 · Ricette

| Elemento | Testo |
|---|---|
| App bar, titolo | `Cosa posso cucinare` |
| App bar, sottotitolo | `Solo con ciò che hai in casa` |
| Sezione | `2 RICETTE POSSIBILI ORA` |
| Ricetta 1 | `Pasta pomodoro e mozzarella` · `Pronta · usa 1 prodotto in scadenza` · `10 min` · `salva spreco` · `Nessun ingrediente da comprare` |
| Ricetta 2 | `Frittata con basilico` · `Pronta · usa 1 prodotto in scadenza` · `15 min` · `salva spreco` · `Nessun ingrediente da comprare` |
| Sezione | `CON 1 INGREDIENTE DA COMPRARE` |
| Ricetta 3 | `Risotto al parmigiano` · `ti manca: burro — 25 min` |
| Sezione | `USANO PRODOTTI IN SCADENZA` |
| Ricetta 4 | `Mozzarella in carrozza` · `usa mozzarella + pane` |

**Attenzione:** «usa mozzarella + pane» è l'unico punto in cui la parola «usa» sopravvive, perché qui
non è un pulsante ma una descrizione degli ingredienti. Non va cambiata, ma non deve diventare un pulsante.

### S07 · Spreco

| Elemento | Testo |
|---|---|
| App bar, titolo | `Spreco` |
| App bar, sottotitolo | `Novembre 2026` |
| App bar, destra | `Mese >` |
| Riquadro | `Buttato questo mese` / `€ 6,40` / `4 prodotti · -38% vs ottobre` |
| Sezione | `ANDAMENTO (6 MESI)` |
| Mesi | `giu` `lug` `ago` `set` `ott` `nov` |
| Sezione | `COSA HO BUTTATO` |
| Righe | `Mozzarella · 2 nov · € 2,80` · `Pane · 31 ott · € 1,60` · `Insalata · 28 ott · € 1,20` · `Yogurt · 24 ott · € 0,80` |
| Nota finale | `Il 70% dello spreco nasce da freschi dimenticati in frigo, non da porzioni troppo grandi.` |

### S08 · Scheda prodotto (nuova)

| Elemento | Testo |
|---|---|
| App bar, sinistra | `Indietro` |
| App bar, destra | `Modifica` |
| Titolo | `Mozzarella` |
| Stato | `SCADE DOMANI` |
| Campi | `Quantità` · `1 confezione` / `Scadenza` · `14 nov 2026` / `Dove` · `Frigo` |
| Azione 1 | `Cucina con questo prodotto` |
| Azione 2 | `Sposta la scadenza` |
| Azione 3 | `Segna come finito` |
| Azione 4 | `Non ricordarmelo` (distruttiva, in fondo) |
| Nota | `«Non ricordarmelo» toglie l'avviso ma non cancella il prodotto.` |

### S09 · Dettaglio ricetta (nuova)

| Elemento | Testo |
|---|---|
| App bar, sinistra | `Indietro` |
| Titolo | `Pasta pomodoro e mozzarella` |
| Meta | `10 min · 2 persone` |
| Etichetta | `INGREDIENTI CHE HAI` |
| Lista | `Pasta secca` · `Passata` · `Mozzarella` · `Basilico` |
| Etichetta | `PROCEDIMENTO` |
| Passi | `1. Metti l'acqua per la pasta.` / `2. Scalda la passata con il basilico.` / `3. Scola la pasta e unisci la mozzarella a fuoco spento.` |
| Pulsante | `Ho cucinato: scala dalla dispensa` |

### S10 · Spreco, dettaglio mese (nuova)

| Elemento | Testo |
|---|---|
| App bar, titolo | `Novembre 2026` |
| Valore | `€ 6,40` |
| Confronto | `Ottobre: € 10,30` |
| Sezione | `COSA HO BUTTATO` |
| Nota | `Il confronto compare solo dal secondo mese di utilizzo.` |

### S11 · Dispensa vuota (nuova)

| Elemento | Testo |
|---|---|
| Titolo | `La dispensa è vuota` |
| Testo | `Aggiungi il primo prodotto: bastano due tocchi.` |
| Pulsante | `Aggiungi un prodotto` |
| Nota | `Le ricette compariranno appena ci sarà qualcosa da cucinare.` |

### S12 · Primo utilizzo (nuova)

| Elemento | Testo |
|---|---|
| Titolo | `Benvenuto in Dispensa` |
| Testo | `Registra quello che compri e ti diciamo cosa cucinare prima che scada.` |
| Passo 1 | `Scrivi il nome del prodotto` |
| Passo 2 | `Tocca il suggerimento` |
| Passo 3 | `Salva: scadenza e posto sono già compilati` |
| Pulsante | `Aggiungi il primo prodotto` |
| Nota | `I suggerimenti compariranno dal secondo prodotto.` |

### S13 · Impostazioni notifiche (nuova)

| Elemento | Testo |
|---|---|
| App bar, titolo | `Notifiche` |
| App bar, sinistra | `Indietro` |
| Voce 1 | `Avvisi di scadenza` · `Un giorno prima, uno per prodotto` |
| Voce 2 | `Nascondi i dettagli sul blocco schermo` · `Mostra solo «Hai una scadenza»` |
| Voce 3 | `Riepilogo settimanale` · `La domenica, cosa scade nei prossimi 7 giorni` |
| Voce 4 | `Orario degli avvisi` · `18:00` |
| Nota finale | `Al massimo una notifica al giorno per prodotto.` |

---

## 5. Cosa non scrivere mai

| Non scrivere | Scrivi |
|---|---|
| `usa` (come pulsante) | `Cucina` |
| `Apri` (come azione) | `Cucina` o `Vedi` |
| `Ho buttato` | `L'ho buttato` |
| `3/3 ingredienti in casa` | `Nessun ingrediente da comprare` |
| `In scadenza` (come testo di notifica) | `{Prodotto}: scade domani` + cosa fare |
| `OK`, `Conferma`, `Procedi` | `Salva`, `Avanti`, `Fine` |
| `Nessun risultato trovato` | `Non c'è ancora niente qui` + cosa fare |
| `Errore` | Che cosa è successo + che cosa fare |
| Punti esclamativi | — |
| Emoji | — |
