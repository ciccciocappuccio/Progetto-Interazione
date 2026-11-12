# FASE 3 — Valutazione euristica

## Gestionale della dispensa domestica con pianificatore dei pasti anti-spreco

**Caso di studio — Interazione Uomo-Macchina**
Anno accademico 2026/2027

---

### Indice

1. [Che cosa fa la Fase 3](#1)
2. [Metodo: chi valuta, con quale strumento, con quali regole](#2)
3. [Le dieci euristiche applicate a questo progetto](#3)
4. [La scala di severità](#4)
5. [Il registro dei problemi](#5)
6. [I problemi, uno per uno](#6)
7. [Che cosa dicono i numeri](#7)
8. [Il prototipo rivisto: prima e dopo](#8)
9. [Che cosa abbiamo deciso di non correggere](#9)
10. [Conclusioni e passaggio alla Fase 4](#10)
11. [Appendice: foglio di lavoro](#11)

---

<a name="1"></a>
## 1. Che cosa fa la Fase 3

La Fase 3 è la **valutazione euristica** del prototipo a bassa fedeltà prodotto nella Fase 2: un'ispezione condotta dai progettisti, senza utenti, che mette i wireframe sotto esame rispetto a un insieme riconosciuto di principi di usabilità e produce un elenco di problemi da correggere prima di investire nella grafica definitiva.

Non è un test con utenti: quello è la Fase 5, e non si può fare su un prototipo che non è ancora stato ripulito dai difetti banali. Non è nemmeno un giudizio estetico: i wireframe sono grigi per scelta, e valutarne l'aspetto sarebbe fuori tempo.

Il risultato atteso della Fase 3 è duplice:

- un **registro dei problemi** con localizzazione, principio violato, severità e correzione proposta;
- un **prototipo rivisto**, in cui i problemi correggibili senza cambiare l'impianto sono già stati corretti.

Entrambi sono in questo documento.

---

<a name="2"></a>
## 2. Metodo: chi valuta, con quale strumento, con quali regole

### 2.1 Come è stata condotta

La valutazione è stata fatta **collettivamente**, in due sessioni, secondo una procedura semplice e ripetibile:

1. **Ispezione individuale.** Ciascun membro del gruppo ha esaminato le sette schermate in sequenza, senza commenti, annotando ogni punto in cui l'interfaccia richiedeva uno sforzo non dovuto.
2. **Consolidamento.** Le annotazioni sono state raccolte in un unico elenco: le segnalazioni coincidenti sono state unite, quelle divergenti discusse.
3. **Classificazione.** Ogni problema è stato associato a un principio violato e a una severità.
4. **Correzione.** Per ogni problema è stata decisa una delle quattro azioni descritte nel §7: correzione nel wireframe, correzione di testo, rinvio, accettazione consapevole.

Il passo 1 è stato fatto individualmente di proposito: una valutazione condotta in gruppo fin dall'inizio tende a schiacciare i giudizi sul membro più loquace, e i problemi di dettaglio spariscono.

### 2.2 Su che cosa si è valutato

Le sette schermate della Fase 2, nell'ordine in cui l'utente le incontra, più il diagramma di flusso per i problemi che riguardano il passaggio da una schermata all'altra.

Un limite da dichiarare subito: **valutare un prototipo statico non permette di giudicare i tempi di risposta, le animazioni, gli stati di caricamento e il comportamento in caso di errore di rete.** Tutto ciò che dipende dal comportamento del sistema nel tempo è fuori dalla portata di questa fase e va rimandato allo user test.

### 2.3 La traccia di riferimento

Per non valutare "a naso" ci siamo dati tre domande guida, ricavate dagli scenari della Fase 2:

- **Marco con tre buste in mano riesce a registrare la spesa?** (riguarda le schermate 2 e 3)
- **Marco alle 21:45, stanco, riesce a decidere cosa cucinare senza pensare?** (riguarda la Home, la 6 e la 5)
- **Un errore — un dato sbagliato, un prodotto buttato per sbaglio — si può accorgere e correggere?** (riguarda tutte)

---

<a name="3"></a>
## 3. Le dieci euristiche applicate a questo progetto

Le euristiche di Nielsen sono principi generali, e applicarli senza tradurli produce elenchi di problemi generici. Le riportiamo qui tradotte nel linguaggio di questo prodotto, perché è così che sono state usate durante l'ispezione.

| # | Principio | Che cosa significa qui | Dove guardiamo |
|---|---|---|---|
| **H1** | Visibilità dello stato del sistema | L'utente deve sempre sapere cosa ha in dispensa, cosa sta per scadere e cosa ha appena salvato | Home, Dispensa, passo 2 dell'aggiunta |
| **H2** | Corrispondenza fra sistema e mondo reale | Le parole devono essere quelle che Marco usa in cucina, non quelle di un database | Etichette dei pulsanti, testi delle notifiche |
| **H3** | Controllo e libertà dell'utente | Deve sempre esserci una via d'uscita, e un'azione sbagliata deve potersi annullare | Ogni schermata con un salvataggio o un'azione irreversibile |
| **H4** | Coerenza e standard | La stessa azione si chiama allo stesso modo e sta nello stesso posto | Confronto fra le sette schermate |
| **H5** | Prevenzione degli errori | Meglio impedire un errore che segnalarlo dopo: niente doppi comandi sullo stesso dato | Passo 2 dell'aggiunta, notifica |
| **H6** | Riconoscere invece che ricordare | L'app deve mostrare le opzioni, non chiedere all'utente di ricordarle | Passo 1, Dispensa |
| **H7** | Flessibilità ed efficienza d'uso | Chi ha fretta deve poter saltare, chi vuole precisione deve poterla avere | Passo 1, card delle ricette |
| **H8** | Estetica e design minimalista | Ogni informazione presente deve servire a una decisione | Tutte |
| **H9** | Aiutare a riconoscere e correggere gli errori | I messaggi devono dire cosa è successo e cosa fare, e le azioni irreversibili vanno confermate | «L'ho buttato», «Salva» |
| **H10** | Aiuto e documentazione | L'app deve spiegarsi da sola; la documentazione è l'ultima risorsa | Non applicabile in modo significativo: nessuna schermata di aiuto è prototipata |

**H10 non ha prodotto problemi**, ed è un'informazione utile: significa che in questo prototipo l'utente non ha bisogno di aiuto per capire dove andare, oppure che non abbiamo prototipato le situazioni in cui ne avrebbe bisogno. La seconda ipotesi è la più probabile, e la annotiamo come limite.

---

<a name="4"></a>
## 4. La scala di severità

Abbiamo usato la scala classica a cinque livelli, adattata al fatto che stiamo valutando un wireframe e non un prodotto finito.

| Livello | Nome | Significato | Che cosa comporta |
|---|---|---|---|
| 0 | Non è un problema | Disaccordo fra valutatori, oppure scelta di progetto difendibile | Niente |
| **1** | **Cosmetico** | Fastidio, non impedisce il compito | Si corregge se resta tempo |
| **2** | **Minore** | L'utente rallenta o esita, ma arriva in fondo | Da correggere prima della Fase 4 |
| **3** | **Maggiore** | L'utente sbaglia o rinuncia in un caso importante | **Da correggere subito** |
| **4** | **Catastrofico** | L'utente non riesce a completare il compito principale, o l'errore ha conseguenze gravi | **Blocca il passaggio alla Fase 4** |

La regola che ci siamo dati: **nessun problema di severità 3 o 4 può arrivare alla Fase 4 senza una decisione esplicita.** Può essere corretto, oppure accettato con una motivazione scritta. Non può essere ignorato.

---

<a name="5"></a>
## 5. Il registro dei problemi

La valutazione ha prodotto **34 problemi**. Sono elencati per schermata, nell'ordine in cui l'utente le incontra.

| Codice | Schermata | Euristica | Severità | Problema | Esito |
|---|---|:--:|:--:|---|:--:|
| E01 | 1 Home | H1 | 3 | La card prioritaria mostra un solo prodotto anche quando ce ne sono altri in scadenza | corretto |
| E02 | 1 Home | H8 | 2 | Il contatore «Notifiche 1» duplica l'informazione della card | corretto |
| E03 | 1 Home | H7 | 2 | «Vedi tutto (12)» è testo, non un comando riconoscibile | corretto |
| E04 | 1 Home | H2 | 2 | Registro linguistico incoerente: «la usi stasera?» accanto a «Ho buttato» | corretto (testo) |
| E05 | 1 Home | H4 | 1 | La stessa azione si chiama «Cucina ora», «usa», «Cucina stasera» | rimandato |
| E06 | 1 Home | H9 | 2 | Dalla card non si può correggere una scadenza sbagliata | rimandato |
| E07 | 2 Aggiunta 1 | H3 | 3 | «Salta: salva senza dettagli» è una didascalia, non un comando | corretto (testo) |
| E08 | 2 Aggiunta 1 | H1 | 3 | Al primo utilizzo la lista dei suggerimenti è vuota e non c'è uno stato per quel caso | rimandato |
| E09 | 2 Aggiunta 1 | H5 | 2 | Non si capisce se un prodotto nuovo verrà creato o rifiutato | corretto |
| E10 | 2 Aggiunta 1 | H7 | 2 | «Passo 1 di 2» annuncia una sequenza, ma la scorciatoia è in fondo | rimandato |
| E11 | 2 Aggiunta 1 | H4 | 1 | «Avanti» e «Salva in dispensa» per la stessa azione | corretto (testo) |
| E12 | 3 Aggiunta 2 | H1 | 3 | «Avviso proposto» dice che la notifica arriverà, non quando | corretto (testo) |
| E13 | 3 Aggiunta 2 | H5 | 3 | Tre comandi concorrenti sullo stesso dato (campo data, calendario, «+7 gg») | corretto (testo) |
| E14 | 3 Aggiunta 2 | H8 | 2 | Il campo «Categoria» chiede un dato che l'intervista dichiarava inutile | corretto (testo) |
| E15 | 3 Aggiunta 2 | H3 | 3 | «Annulla» è testo grigio sotto il pulsante principale | corretto |
| E16 | 3 Aggiunta 2 | H6 | 1 | Le chip «Dove» chiedono di ricordare il posto abituale del prodotto | rimandato |
| E17 | 4 Dispensa | H2 | **4** | «usa» è un verbo senza oggetto: non dice che porta alle ricette | corretto |
| E18 | 4 Dispensa | H6 | 3 | Le azioni di modifica sono rinchiuse in un menu «···» | corretto |
| E19 | 4 Dispensa | H2 | 2 | L'ordine della sezione «Scadono presto» non è dichiarato | corretto |
| E20 | 4 Dispensa | H5 | 3 | «L'ho buttato» è irreversibile e alimenta la misura, ma non ha conferma | rimandato |
| E21 | 4 Dispensa | H2 | 1 | «Tutto 24» si legge come un identificativo, non come un conteggio | corretto (testo) |
| E22 | 4 Dispensa | H9 | 2 | Manca «Finito», distinto da «buttato» | rimandato |
| E23 | 5 Notifica | H3 | 3 | Tre azioni tutte impegnative, nessun rinvio | corretto |
| E24 | 5 Notifica | H8 | 3 | La notifica espone la dispensa su schermo bloccato | corretto |
| E25 | 5 Notifica | H2 | 2 | Titolo e corpo insieme sono troppo lunghi per un banner | corretto |
| E26 | 5 Notifica | H3 | 2 | Nessun modo di dire «questo prodotto non mi interessa» | rimandato |
| E27 | 6 Ricette | H7 | 2 | «Apri >» piccolo: la card non sembra toccabile per intero | corretto |
| E28 | 6 Ricette | H2 | 3 | «3/3 ingredienti in casa» promette un calcolo delle quantità che il sistema non fa | corretto |
| E29 | 6 Ricette | H5 | 2 | La card «ti manca il burro» è più leggera: sembra disabilitata | corretto |
| E30 | 6 Ricette | H9 | 2 | Con la dispensa quasi vuota non c'è uno stato che spieghi perché le ricette sono poche | rimandato |
| E31 | 7 Spreco | H1 | 2 | Il grafico a barre non ha scala: le altezze non comunicano valori | rimandato |
| E32 | 7 Spreco | H5 | 2 | «-38% vs ottobre» non dice su quale base è calcolato | rimandato |
| E33 | 7 Spreco | H8 | 1 | «dettagli >» duplica la navigazione della tab bar | accettato |
| E34 | Tutte | H8 | 2 | Le note di progetto tratteggiate sembrano parte dell'interfaccia | corretto |

---

<a name="6"></a>
## 6. I problemi, uno per uno

Per i problemi di severità 3 e 4 — quelli che bloccano il passaggio alla Fase 4 — riportiamo la descrizione estesa, perché sono i più utili da discutere.

### E01 · Un solo prodotto in evidenza quando ce ne sono tre

**Schermata 1 · H1 · severità 3**

La card prioritaria dichiara «SCADE DOMANI» e propone la mozzarella. Nella stessa dispensa, però, yogurt e insalata scadono rispettivamente oggi e fra tre giorni: due dei quali prima della mozzarella. L'utente che guarda solo la Home riceve un'informazione **parziale presentata come completa**, e il criterio con cui è stata scelta la mozzarella non è visibile.

*Correzione applicata:* dentro la card compare «Ne scadono altri 2 oggi», che dichiara l'esistenza degli altri e porta all'elenco completo. Non abbiamo cambiato il criterio di scelta del prodotto in evidenza — quello è un problema di modello, non di interfaccia, e lo rimandiamo.

### E07 · La via d'uscita travestita da didascalia

**Schermata 2 · H3 · severità 3**

Il passo 1 dell'aggiunta ha una scorciatoia preziosa: salvare il prodotto senza passare dal passo 2. È scritta «Salta: salva senza dettagli», in grigio, sotto il pulsante principale, nella posizione in cui di solito si mette una nota esplicativa. Chi ha fretta — cioè l'utente di questo progetto — non la trova, perché non sta cercando una nota.

*Correzione applicata:* la scorciatoia diventa un'azione esplicita in app bar, in alto a destra, con l'etichetta «Salva». La didascalia in basso resta, ma dice dove si trova il comando invece di essere il comando.

### E12 · Una promessa senza tempo

**Schermata 3 · H1 · severità 3**

Il riquadro «Avviso proposto» mostra il testo della notifica che l'utente riceverà. Manca l'informazione che rende utile il riquadro: **quando**. Con la scadenza precompilata a sette giorni e la regola «un giorno prima», l'avviso reale arriva sei giorni dopo il salvataggio; l'utente che legge «La mozzarella scade domani, usala stasera» può ragionevolmente pensare che lo riceverà subito.

*Correzione applicata:* il riquadro si chiama «Cosa riceverai» e dice «1 notifica, il giorno prima della scadenza», seguito dal testo.

### E13 · Tre comandi su un solo dato

**Schermata 3 · H5 · severità 3**

La scadenza si può cambiare in tre modi: toccando il campo data, toccando la scritta «calendario», oppure toccando la scorciatoia «+7 gg (stima)». Il terzo comando è anche ambiguo, perché il valore è già +7 e non si capisce se lo applica o lo somma. In un campo che determina *quando* arriverà la notifica, questa è una configurazione che invita all'errore silenzioso.

*Correzione applicata:* un solo comando, la scritta «cambia» dentro il campo. La stima scende a didascalia: «stima predefinita: +7 giorni».

### E15 · Un'uscita che non si vede

**Schermata 3 · H3 · severità 3**

«Annulla» è testo grigio centrato sotto il pulsante di salvataggio. In un modulo che l'utente può aver aperto per sbaglio, l'uscita deve essere visibile quanto l'ingresso. Nelle altre schermate la convenzione è chiara — l'uscita sta in alto a sinistra — e qui non è rispettata.

*Correzione applicata:* «Annulla» diventa l'azione sinistra dell'app bar, come «Chiudi» e «Indietro» nelle altre schermate.

### E17 · «usa» — il problema più grave

**Schermata 4 · H2 · severità 4**

Nella Dispensa ogni riga ha un pulsante con scritto «usa». È il ponte fra la dispensa e le ricette, cioè il passaggio che realizza la catena di valore dell'intero prodotto (registro → avviso → pasto), ed è etichettato con un verbo senza oggetto. «Usa» cosa? Il prodotto? La ricetta? L'app? Un utente che non ha mai visto il prodotto non ha modo di saperlo, e il pulsante più importante della schermata è anche quello più opaco.

È l'unico problema di severità 4 della valutazione: da solo non impedisce di completare un compito, ma rende invisibile il passaggio che dà senso al prodotto.

*Correzione applicata:* «Cucina», con la stessa forma del pulsante e il bordo marcato. La parola è un verbo con un oggetto implicito chiaro nel contesto della riga (il prodotto), e coincide con l'azione che l'utente si aspetta.

### E18 · Azioni nascoste dietro tre puntini

**Schermata 4 · H6 · severità 3**

La modifica di un prodotto — l'unico modo per correggere una scadenza sbagliata — sta dietro un menu «···» in fondo a ogni riga. È il classico caso in cui il sistema chiede all'utente di *ricordare* dove si trova un'azione invece di *mostrarla*. Su una schermata che esiste proprio per correggere i dati, l'azione principale non può essere nascosta.

*Correzione applicata:* «Modifica» visibile nella riga, accanto a «Cucina».

### E23 · Tre decisioni impegnative e nessun rinvio

**Schermata 5 · H3 · severità 3**

La notifica espansa offre tre azioni: cucinare, spostare la scadenza, registrare lo spreco. Sono tutte e tre definitive, e non esiste un modo per dire «adesso non posso decidere». È il contrario del controllo e della libertà dell'utente: la notifica interrompe, e poi chiede una scelta senza offrire una via d'uscita leggera.

*Correzione applicata:* «Cucina la ricetta» (azione principale), «Più tardi (stasera)», «L'ho buttata». La correzione della scadenza esce dal banner e diventa un rimando esplicito alla scheda prodotto: «Scadenza sbagliata? Si corregge dalla scheda prodotto».

### E24 · La dispensa di casa sullo schermo bloccato

**Schermata 5 · H8 · severità 3**

Il testo della notifica nomina il prodotto. Su un telefono appoggiato sul tavolo di cucina, o sul lock screen di un telefono che vibra in ufficio, questo espone il contenuto della dispensa a chiunque. Non è un problema di estetica, ma di quantità di informazione mostrata nel posto sbagliato.

*Correzione applicata:* un interruttore «Nascondi i dettagli sul blocco schermo» dentro la notifica espansa, che mostra solo «Hai una scadenza». Il valore predefinito dell'interruttore è una decisione che rimandiamo: nel prototipo è attivo, ma la scelta dipende dal contesto d'uso reale.

### E28 · Una promessa che il sistema non può mantenere

**Schermata 6 · H2 · severità 3**

La card della ricetta dichiara «3/3 ingredienti in casa». Il sistema, però, registra le quantità a confezioni e in modo facoltativo: non sa se in frigo c'è abbastanza mozzarella per quattro persone. La frase promette un calcolo che non viene fatto, e nel caso peggiore l'utente scopre l'inganno a metà ricetta.

*Correzione applicata:* «Nessun ingrediente da comprare». Dice la stessa cosa — non serve uscire di casa — senza impegnarsi su una quantità che non conosciamo.

---

<a name="7"></a>
## 7. Che cosa dicono i numeri

![Problemi per principio violato](g-euristiche.png)

Il principio più violato è **H2, corrispondenza fra sistema e mondo reale**, con sei problemi. È un dato che non sorprende ma che vale la pena leggere: i difetti più frequenti di questo prototipo non sono di layout, sono di **parole**. «usa», «Ho buttato», «3/3 ingredienti in casa», «Tutto 24»: quattro modi diversi di usare il linguaggio in modo approssimativo nella stessa app.

Il secondo dato interessante è che **H10, aiuto e documentazione, non ha prodotto nulla**. In un prototipo che non ha nessuna schermata di aiuto, questo può significare due cose opposte: che l'interfaccia si spiega da sé, oppure che non abbiamo mai prototipato una situazione in cui l'utente si perde. La seconda spiegazione è più probabile, e la teniamo presente per la Fase 5.

![Problemi per severità](g-severita.png)

La distribuzione per severità è quella tipica di un primo prototipo ispezionato con attenzione: molti problemi minori, **undici maggiori** e **un solo catastrofico**. Il fatto che ci sia un solo problema di severità 4 è una buona notizia relativa: l'impianto del flusso tiene, ed è stato il linguaggio a tradire il progetto nel punto più importante.

![Che fine hanno fatto i problemi](g-esito.png)

**Diciannove problemi su trentaquattro sono stati risolti** prima di chiudere questa fase: dodici ridisegnando la schermata, sette cambiando un'etichetta o un testo. Quattordici sono rimandati perché richiedono schermate che non esistono ancora (la scheda prodotto) o comportamenti che un wireframe statico non può rappresentare. Uno è accettato con motivazione.

---

<a name="8"></a>
## 8. Il prototipo rivisto: prima e dopo

Le correzioni che non richiedevano una schermata nuova sono già state applicate. Sotto, per ogni schermata modificata, il confronto affiancato: a sinistra la versione valutata, a destra quella rivista.

<div class="diff"><h3>1 · Home</h3>
<div class="pair"><figure><img src="v1-01-home.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-01-home.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E01 (avviso «ne scadono altri 2»), E02 (via il contatore), E03 («Vedi tutti…» diventa un pulsante), E04 («L'ho buttato»).</p>
</div>

<div class="diff"><h3>2 · Aggiunta rapida, passo 1</h3>
<div class="pair"><figure><img src="v1-02-aggiunta.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-02-aggiunta.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E07 («Salva» in app bar come comando), E09 (riga «Crea «mozzarella»»). <b>Rimosso:</b> la nota di progetto, che confondeva l'interfaccia (E34).</p>
</div>

<div class="diff"><h3>3 · Aggiunta rapida, passo 2</h3>
<div class="pair"><figure><img src="v1-03-aggiunta-dettagli.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-03-aggiunta-dettagli.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E12 («1 notifica, il giorno prima»), E13 (un solo comando sulla data), E14 (via la categoria), E15 («Annulla» in app bar).</p>
</div>

<div class="diff"><h3>4 · Dispensa</h3>
<div class="pair"><figure><img src="v1-04-dispensa.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-04-dispensa.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E17 («usa» → «Cucina»), E18 («Modifica» visibile), E19 (ordinamento dichiarato), E21 («Tutti (24)»).</p>
</div>

<div class="diff"><h3>5 · Notifica</h3>
<div class="pair"><figure><img src="v1-05-notifica.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-05-notifica.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E23 (rinvio «Più tardi», azione principale unica), E24 (interruttore privacy), E25 (titolo accorciato). <b>Rimosso:</b> la nota di progetto (E34).</p>
</div>

<div class="diff"><h3>6 · Ricette</h3>
<div class="pair"><figure><img src="v1-06-ricette.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-06-ricette.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E27 (card interamente toccabile), E28 («Nessun ingrediente da comprare»), E29 (le ricette con ingredienti mancanti in una sezione separata).</p>
</div>

<div class="diff"><h3>7 · Spreco</h3>
<div class="pair"><figure><img src="v1-07-spreco.png"/><figcaption>v1 — valutata</figcaption></figure><figure><img src="v2-07-spreco.png"/><figcaption>v2 — rivista</figcaption></figure></div>
<p class="note"><b>Corretto:</b> E34 (rimossa la nota tratteggiata, che sembrava parte del prodotto). I problemi E31 e E32 sul grafico restano aperti.</p>
</div>

### 8.1 Un problema che le correzioni hanno fatto emergere

Rivedendo la schermata 4 dopo aver corretto E17 ed E18, ci siamo accorti di un effetto collaterale: con «Modifica» e «Cucina» affiancati su ogni riga, la riga dei prodotti in scadenza ha ora **due comandi della stessa larghezza**, e quello meno importante (Modifica) occupa lo spazio che serviva a leggere il nome del prodotto. È un problema nuovo, introdotto dalla correzione, e lo registriamo come **E35 (H8, severità 2)**: nella prossima revisione «Modifica» va ridotta a icona o spostata nella scheda prodotto.

Lo segnaliamo perché è il modo onesto di raccontare una valutazione euristica: correggere introduce difetti nuovi, e il ciclo serve a questo.

---

<a name="9"></a>
## 9. Che cosa abbiamo deciso di non correggere

Quattordici problemi restano aperti. Non sono stati dimenticati: sono state prese tre decisioni diverse.

**Rinviati perché richiedono una schermata che non esiste (sette).** E06, E16, E20, E22, E26 riguardano la **scheda prodotto**, che nel prototipo della Fase 2 non c'è: correggere una scadenza, suggerire il luogo abituale, annullare uno spreco, dichiarare un prodotto finito, silenziare un avviso. Sono tutte azioni che appartengono a quella schermata, e la Fase 4 dovrà deciderne l'esistenza prima di poterle collocare.

**Rinviati perché dipendono dal comportamento nel tempo (quattro).** E10, E30, E31, E32 riguardano sequenze, stati vuoti e grafici: cose che un wireframe statico non può mostrare e che uno user test deve misurare.

**Rinviati perché toccano il modello, non l'interfaccia (due).** E05 (tre nomi per la stessa azione) ed E08 (primo utilizzo senza storico) non si risolvono cambiando un'etichetta o un layout: il primo richiede di decidere quale sia il verbo ufficiale del prodotto, il secondo richiede un onboarding che qui non è prototipato.

**Accettato consapevolmente (uno).** E33: «dettagli >» nella schermata Spreco duplica la navigazione della tab bar, ma serve come punto di ingresso al dettaglio del singolo mese, che non è prototipato. Toglierlo ora significherebbe togliere una porta che nella Fase 4 servirà.

### 9.1 Quattro domande che non sono problemi ma decisioni

La valutazione ha fatto emergere quattro questioni che non si possono chiudere con una correzione, e che portiamo alla discussione:

1. **Il primo utilizzo.** Tutta la velocità dell'inserimento rapido si basa sui suggerimenti, e i suggerimenti non esistono il primo giorno. Il prototipo non ha una risposta. È il punto in cui il prodotto può perdere l'utente prima di averlo.
2. **Il prodotto in evidenza.** La Home sceglie un solo prodotto. Su quale criterio — la data più vicina, la quantità, il valore economico? Il prototipo non lo dice, e l'utente non può dedurlo (E01 l'ha solo segnalato).
3. **Il verbo del prodotto.** «Cucina», «usa», «Apri»: il prodotto non ha ancora deciso come si chiama la sua azione centrale. Finché non lo decide, ogni schermata lo chiamerà in modo diverso (E05).
4. **La notifica e la privacy.** Abbiamo messo un interruttore, ma non sappiamo se il valore predefinito debba mostrare o nascondere il prodotto. Dipende da dove sta il telefono quando arriva l'avviso, e questo lo sappiamo solo osservando.

---

<a name="10"></a>
## 10. Conclusioni e passaggio alla Fase 4

### 10.1 Che cosa ha detto la valutazione

Il prototipo **regge nella struttura e cede nel linguaggio**. L'impianto del flusso — una Home che apre su un'azione, un inserimento a due passi con un'uscita breve, una notifica che propone invece di ricordare — non ha prodotto nessun problema catastrofico. Il difetto più grave (E17) non è di architettura: è una parola sbagliata su un pulsante giusto.

Le tre correzioni più importanti, in ordine di impatto:

| # | Correzione | Perché conta |
|---|---|---|
| E17 | «usa» → «Cucina» | Rende visibile il passaggio che dà senso al prodotto |
| E07 | La scorciatoia diventa un comando in app bar | Recupera la velocità che l'intervista chiedeva come requisito primo |
| E23 | Il rinvio «Più tardi» nella notifica | Trasforma un'interruzione in una scelta |

### 10.2 Che cosa passa alla Fase 4

La Fase 4 è il prototipo ad alta fedeltà. Non deve ripartire da zero: deve partire dai wireframe rivisti e affrontare le questioni che questa fase ha lasciato aperte.

**Da prototipare per la prima volta:**
- la **scheda prodotto**, che sblocca sette problemi rinviati (E06, E16, E20, E22, E26 e in parte E15);
- lo **stato vuoto** della dispensa e del primo utilizzo (E08, E30);
- il **dettaglio della ricetta**, citato nei wireframe ma mai disegnato;
- il **dettaglio del mese** nella schermata Spreco (E31, E32).

**Da decidere prima di disegnare:**
- il verbo ufficiale dell'azione centrale (E05);
- il criterio con cui la Home sceglie il prodotto in evidenza;
- il valore predefinito dell'interruttore privacy sulla notifica;
- la scala del grafico dello spreco, che richiede di sapere quali dati il sistema registra davvero.

**Da non perdere per strada:** la legenda dei wireframe del §7.1 della Fase 2. Nella Fase 4 i colori entrano legittimamente, ma le note di progetto tratteggiate no: vanno spostate accanto alla schermata, come chiede E34.

### 10.3 Una nota sul metodo

Questa valutazione ha prodotto trentaquattro problemi su sette schermate, quasi cinque per schermata. È un numero alto, e va letto nel modo giusto: un prototipo a bassa fedeltà **deve** avere molti problemi, perché è stato disegnato in fretta e di proposito. Il valore della Fase 3 non è il numero di problemi trovati, ma il fatto che nessuno di essi arrivi alla Fase 4 senza una decisione scritta.

---

<a name="11"></a>
## 11. Appendice: foglio di lavoro

Per chi volesse ripetere la valutazione — per esempio su una schermata nuova della Fase 4 — questo è il formato che abbiamo usato.

| Campo | Che cosa contiene |
|---|---|
| Codice | E01, E02… univoco e progressivo |
| Schermata | Dove si trova il problema |
| Euristica | H1…H10 |
| Severità | 0–4 |
| Problema | Una frase, in che cosa l'interfaccia costa all'utente |
| Evidenza | Che cosa, esattamente, nello schermo produce il problema |
| Correzione proposta | Che cosa si fa, o perché non si fa |
| Esito | corretto / corretto (testo) / rimandato / accettato |

**Regola di igiene.** Un problema senza *evidenza* non è un problema: è un'opinione. Se non si riesce a indicare l'elemento dello schermo che lo produce, il problema non va scritto.

---

*Fine del documento di Fase 3.*
