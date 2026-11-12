# FASE 2 — Prototipo a bassa fedeltà

## Gestionale della dispensa domestica con pianificatore dei pasti anti-spreco

**Caso di studio — Interazione Uomo-Macchina**
Anno accademico 2026/2027

---

### Indice

1. [Il dominio e il problema](#1)
2. [Che cosa produce la Fase 2](#2)
3. [Persona e scenari d'uso](#3)
4. [Dal bisogno al compito: task analysis](#4)
5. [Il nodo del progetto: un solo modo di registrare](#5)
6. [Requisiti](#6)
7. [Scelte di prototipazione](#7)
8. [Il flusso delle schermate](#8)
9. [I wireframe, uno per uno](#9)
10. [Tracciabilità: dal requisito alla schermata](#10)
11. [Che cosa mettiamo sotto esame nella Fase 3](#11)
12. [Limiti dichiarati e questioni aperte](#12)
13. [Appendice: i file del prototipo](#13)

---

<a name="1"></a>
## 1. Il dominio e il problema

Il progetto opera nel dominio dell'**alimentazione sostenibile** e della **gestione dello spreco di cibo in ambito domestico**.

Il problema non è la mancanza di informazioni: chi cucina butta via cibo perché **dimentica** cosa ha in dispensa e in frigorifero, e perché **non sa come combinare** gli ingredienti che già possiede. Le soluzioni esistenti affrontano il problema con elenchi e promemoria, ma sono lente e complesse da usare nel momento in cui servirebbero, cioè quando si è di fretta; e vengono abbandonate.

Il sistema che progettiamo è un **gestionale della dispensa di casa con pianificatore dei pasti anti-spreco**. L'utente:

- registra i prodotti **in modo estremamente veloce**, con un inserimento rapido basato su ricerca e suggerimenti;
- riceve **avvisi prima della scadenza**, formulati come azioni e non come promemoria;
- ottiene **ricette suggerite esclusivamente dagli ingredienti disponibili**;
- **traccia lo spreco nel tempo**.

Il percorso di progetto segue cinque fasi: analisi dei requisiti, prototipo a bassa fedeltà, valutazione euristica, prototipo ad alta fedeltà e user test. Questo documento copre la **seconda**.

Il nucleo del design ruota attorno a una singola frustrazione, **l'inserimento rapido dei cibi**: è da lì che il prodotto vince o perde, ed è la parte su cui questo prototipo concentra la maggior parte delle schermate.

---

<a name="2"></a>
## 2. Che cosa produce la Fase 2

La Fase 2 produce un **prototipo a bassa fedeltà**: wireframe e mockup iniziali che servono a rendere visibili e discutibili le prime idee di progetto, prima di investire nella grafica definitiva.

Il prototipo che presentiamo si colloca in un punto preciso del percorso. Lo dichiariamo qui, perché da questa collocazione dipendono tutte le scelte grafiche che seguono.

| Parametro | Scelta per la Fase 2 | Perché |
|---|---|---|
| **Fedeltà** | Bassa | Vogliamo scoprire i problemi di flusso e di contenuto mentre cambiarli costa poco; i dettagli visivi li affrontiamo quando la struttura è stabile |
| **Momento** | Prototipo iniziale | Siamo prima della soluzione consolidata: schermate ferme, non ancora un prototipo interattivo |
| **Scopo** | Interfaccia | Valutiamo le modalità di interazione, non il ruolo del prodotto nella vita di Marco né la fattibilità tecnica |
| **Modo d'uso** | Statico, con indicazione delle transizioni | Schermate ferme più un diagramma di flusso; la versione navigabile arriva in Fase 4 |
| **Completezza funzionale** | Orizzontale | Molte funzioni, poco approfondite: copriamo l'intero percorso senza portarne nessuna fino all'implementazione |
| **Durata** | Usa e getta | Serve a raccogliere problemi prima di investire nella grafica definitiva |

Da questa collocazione derivano due conseguenze pratiche. La prima: i wireframe sono **volutamente brutti**. Se mostrassimo un'interfaccia curata, chi la valuta nella Fase 3 commenterebbe i colori e i bordi invece dei contenuti e del flusso. Usiamo quindi solo grigi, parole al posto delle icone e riquadri tratteggiati dove andrà un'immagine. La seconda: tutto ciò che disegniamo oggi va considerato sacrificabile. Se la Fase 3 smonta una schermata, la rifacciamo senza rimpianti, ed è esattamente il motivo per cui non abbiamo investito in un prototipo più ricco.

**Nota sui wireframe digitali.** Il metodo classico prevede carta e pennarello. Noi disegniamo in digitale per due ragioni pratiche: il gruppo consegna a distanza e i file devono essere condivisibili e modificabili in modo incrementale; e la Fase 3 richiede che chi valuta legga etichette e microtesti, cosa che uno schizzo a mano libera rende faticosa. Le regole di bassa fedeltà restano però intatte: **nessun colore, nessuna icona, nessun font curato**.

**Che cosa contiene la consegna.** Sette schermate, un diagramma di flusso, otto requisiti funzionali e sei non funzionali, e una tabella di tracciabilità che lega l'uno all'altra.

---

<a name="3"></a>
## 3. Persona e scenari d'uso

Prima di disegnare una schermata serve sapere chi la usa, in quale situazione e con quale obiettivo. Fissiamo quindi una persona e tre scenari che useremo come traccia per ogni schermata.

### 3.1 Persona

> **Marco, 34 anni — "lo faccio di fretta o non lo faccio"**
>
> Sviluppatore software in una piccola agenzia di Milano. Vive con Giulia (part-time in ospedale, turni alternati) e Mattia, 4 anni. Abita in 70 m². Torna dal supermercato con tre o quattro buste e il bambino: ha le mani occupate. Cucina 4–5 sere a settimana, spesso da solo, fra le 21:30 e le 22:30, quando è già stanco.
>
> **Obiettivo:** non buttare più cibo dimenticato, e decidere cosa cucinare senza aprire il frigo dieci volte.
> **Frustrazione:** inserire dati; i gestionali che chiedono quantità e categorie per ogni pacco di pasta.
> **Convinzione:** «voglio che l'app mi dica cosa ho già e cosa posso cucinare con quello».
> **Contesto d'uso:** cucina, in piedi, una mano sola, luce scarsa, connessione a volte debole.
> **Livello tecnico:** alto, ma la sua pazienza verso le app è bassa: l'esperienza quotidiana con strumenti lenti gli ha insegnato a chiudere le app che chiedono troppo.

### 3.2 Scenari d'uso

**Scenario A — il ritorno dalla spesa (percorso critico).**
Marco entra in casa con tre buste e il bambino che gli tira la giacca. Apre l'app *prima* di mettere via la spesa, perché dopo non lo farà più. Scrive «mozz»: l'app gli propone «Mozzarella», che lui aveva già comprato in passato. Un tocco. L'app propone scadenza a sette giorni e posto «Frigo»: lui preme «Salva». Poi ripete per il latte e lo yogurt. Tre prodotti in una manciata di secondi, senza mai aprire una tendina e senza mai digitare una data. Se in questo scenario l'app chiede una quantità in grammi, Marco la chiude e non la riapre.

**Scenario B — la sera, davanti al frigo aperto.**
Sono le 21:45. Marco non ha voglia di pensare. Apre l'app sulla Home: la prima cosa che vede è che la mozzarella scade domani e che c'è una pasta con pomodoro e basilico pronta con quello che ha. Tocca «Cucina ora» e ha i passi. Non ha cercato niente, non ha scelto niente: ha solo accettato una proposta.

**Scenario C — la mozzarella dimenticata (evento esterno).**
Marco è in ufficio, alle 17. Riceve una notifica: «La mozzarella scade domani. Usala stasera: pasta con pomodoro e basilico». Non è un promemoria generico: contiene già la soluzione. La apre, tocca «Cucina stasera» e la sera ritrova la ricetta. Se invece stasera ha mangiato fuori, dalla stessa notifica registra «Ho buttato» e l'app impara che quel prodotto va ricordato prima.

---

<a name="4"></a>
## 4. Dal bisogno al compito: task analysis

Tradotto in compiti osservabili, il sistema deve supportare cinque compiti primari e due secondari. Il prototipo copre tutti e sette.

| # | Compito | Frequenza | Criticità | Dove si svolge nel prototipo |
|---|---|---|---|---|
| T1 | Registrare un prodotto appena comprato | 3–6 volte a settimana, in gruppo dopo la spesa | **Altissima** (se fallisce, tutto il resto è inutile) | Schermate 2–3 |
| T2 | Vedere cosa sta per scadere | Quotidiana, anche solo 10 secondi | Alta | Home (1), Dispensa (4) |
| T3 | Decidere cosa cucinare con ciò che c'è | Quotidiana, sera | **Alta** (è il valore distintivo) | Ricette (6) |
| T4 | Ricevere un avviso utile e agire da lì | 2–4 volte a settimana | Alta | Notifica (5) |
| T5 | Registrare che un prodotto è stato buttato | 1–2 volte a settimana | Media (alimenta la misura) | Home, notifica, Spreco (7) |
| T6 | Consultare e correggere l'elenco della dispensa | 1–2 volte a settimana | Media | Dispensa (4) |
| T7 | Vedere l'andamento dello spreco nel tempo | Mensile | Bassa ma motivante | Spreco (7) |

**Il compito critico è T1.** Su questo il progetto si gioca la partita: è l'unico compito che l'utente ripete molte volte e l'unico che, se troppo costoso, fa abbandonare l'app portandosi dietro T2–T7. Per questo le schermate 2 e 3 sono progettate insieme come un flusso unico a due passi, e per questo la schermata 3 ha un'uscita «Salta: salva senza dettagli».

---

<a name="5"></a>
## 5. Il nodo del progetto: un solo modo di registrare

La registrazione veloce è dichiarata come il cuore del sistema. In questo prototipo la modalità prevista è **una sola**: l'inserimento rapido basato su ricerca e suggerimenti.

La scelta merita di essere argomentata, perché è la decisione di progetto più esposta della Fase 2 e perché è stata fatta per sottrazione: ogni modalità in più è un modello di interazione in più da progettare, da spiegare e da verificare in Fase 3.

Il ragionamento che ci ha portato qui è questo:

- **Un solo modello da imparare.** Chi apre l'app con tre buste in mano non deve decidere *come* inserire: deve solo inserire. Ogni alternativa in più aggiunge una decisione nel momento peggiore, e una decisione presa male è un abbandono.
- **Un solo modello da verificare.** Con una via sola la Fase 3 può dire con chiarezza se funziona o no; con tre vie il risultato sarebbe tre volte più lungo e tre volte più ambiguo.
- **La ripetitività della spesa domestica.** In una casa si comprano sempre più o meno le stesse cose. È questa ripetitività che rende possibile la velocità, non la tecnologia di acquisizione.

**La velocità viene dai suggerimenti, non dal numero di modi.** Un solo campo in cui si scrivono tre lettere, una lista di prodotti già noti all'app perché già comprati, un tocco. Il risparmio di tempo non nasce dal fatto che l'utente sceglie la modalità giusta, ma dal fatto che **l'app conosce già la sua dispensa**: è la ripetitività della spesa domestica che rende possibile l'inserimento in due tocchi.

Due regole che valgono per questo flusso e che ritroverete nei wireframe:

1. **Nessun campo obbligatorio oltre al nome.** Quantità, scadenza e luogo sono precompilati con un valore plausibile e modificabili, mai richiesti. Il secondo passo è facoltativo e lo dichiara.
2. **Il default è visibile come default.** La scadenza proposta a sette giorni è marcata «predefinito»: l'utente sa che è una stima, non un dato letto da qualche parte.

Una conseguenza da mettere in conto: con una sola via, il primo utilizzo è il momento peggiore, perché non ci sono suggerimenti. Il prototipo non lo nasconde (è fra le questioni aperte del §12), ma è il prezzo che paghiamo per avere un solo modello di interazione da imparare.

---

<a name="6"></a>
## 6. Requisiti

I requisiti sono formulati in modo da poter essere verificati nella Fase 3 e nella Fase 5. Sono volutamente pochi e misurabili.

### Requisiti funzionali

| ID | Requisito | Criterio di verifica |
|---|---|---|
| RF1 | Registrare un prodotto con nome, luogo e data di scadenza | L'utente completa il compito senza aiuto |
| RF2 | Nessun campo obbligatorio oltre al nome | Il pulsante «Salva» è attivo appena c'è il nome |
| RF3 | Suggerire prodotti già registrati in passato | Almeno 1 suggerimento pertinente dopo 3 caratteri |
| RF4 | Segnalare i prodotti in scadenza entro 7 giorni | Tutti i prodotti con scadenza ≤ 7 gg compaiono in cima |
| RF5 | Proporre ricette eseguibili solo con gli ingredienti presenti | Zero ricette proposte con ingredienti mancanti |
| RF6 | Consentire l'azione direttamente dalla notifica | Tre azioni disponibili senza aprire l'app |
| RF7 | Registrare un prodotto come buttato | L'evento entra nello storico dello spreco |
| RF8 | Mostrare lo spreco in valore economico e in andamento | Il dato è leggibile in meno di 10 secondi |

### Requisiti non funzionali

| ID | Requisito | Criterio di verifica |
|---|---|---|
| RNF1 | Inserimento sotto i 10 secondi per prodotto | Cronometro in user test |
| RNF2 | Il percorso critico (registrare → salvare) entro 3 tocchi | Conteggio dei tocchi, dalla Home al salvataggio |
| RNF3 | Mobile-first, uso a una mano | Tutte le azioni principali nel terzo inferiore dello schermo |
| RNF4 | Massimo una notifica al giorno per prodotto | Conteggio in Fase 3 |
| RNF5 | Nessun suggerimento che richieda un acquisto | Revisione dei contenuti in Fase 3 |
| RNF6 | Leggibilità in cucina, in piedi, con luce scarsa | Testo corpo ≥ 10 pt, contrasto alto, target ≥ 44 px |

I requisiti RNF3 e RNF6 spiegano scelte che altrimenti sembrerebbero strane: il FAB «Aggiungi» è in basso a destra, i pulsanti principali sono larghi e in fondo allo schermo, la tab bar ha quattro sole voci.

---

<a name="7"></a>
## 7. Scelte di prototipazione

### 7.1 Convenzioni del wireframe

Per evitare che un wireframe venga letto come "quasi fatto" fissiamo una legenda, che vale anche per la Fase 3:

| Elemento | Convenzione | Motivo |
|---|---|---|
| Colori | Solo bianco, grigi, nero | Il colore è una decisione di Fase 4; introdurlo ora produrrebbe feedback estetici prematuri |
| Icone | Sostituite dalla parola (es. «Notifiche 1») | Un'icona disegnata in wireframe è già una decisione grafica; la parola mette alla prova il fatto che l'etichetta sia comprensibile |
| Immagini | Riquadro tratteggiato con la parola «foto» | Stessa ragione: l'immagine non è una decisione della Fase 2 |
| Testo di corpo | Barre grigie solo dove il contenuto non è decisivo | Il testo che conta per il flusso (etichette, avvisi) è scritto per intero e leggibile |
| Riquadri tratteggiati | Note di progetto, non elementi d'interfaccia | Servono al gruppo e alla discussione, non all'utente: vanno rimossi nella Fase 4 |
| Numeri nei cerchi | Ancoraggi alla valutazione euristica | In Fase 3 ogni numero è un punto da esaminare |

### 7.2 Dimensioni e griglia

Riferimento: 375 × 812 px (telefono di fascia media, il più diffuso fra gli utenti target). Margine laterale 16 px, gutter 8 px, raggio degli angoli 6–8 px. I wireframe sono disegnati in scala ridotta per stare in pagina: i target da 20 px sullo schermo corrispondono a circa 44 px nell'implementazione.

### 7.3 Che cosa il prototipo *non* affronta

Dichiararlo ora evita che in Fase 3 qualcuno segnali come mancanza ciò che è una scelta di perimetro:

- registrazione e onboarding dell'account;
- lista della spesa (esplicitamente rifiutata dall'utente nella Fase 1);
- modalità di acquisizione alternative all'inserimento rapido, escluse per la ragione spiegata nel §5;
- notifiche push a livello di sistema operativo (permessi, orari, frequenza);
- impostazioni, profilo, accessibilità dettagliata;
- sincronizzazione fra più dispositivi e condivisione con Giulia;
- stati di errore di rete e stato vuoto della dispensa.

Sono, per definizione di prototipo orizzontale, il lavoro delle fasi successive.

---

<a name="8"></a>
## 8. Il flusso delle schermate

Il diagramma mostra le sette schermate e il modo in cui l'utente passa dall'una all'altra. Ha una particolarità da segnalare: **la Home non è un menu**. Non elenca funzioni, ma apre su una sola azione concreta (la mozzarella che scade domani). Le altre aree sono raggiungibili dalla tab bar, ma il percorso normale dell'utente non passa mai dalla scelta di una funzione.

Il secondo punto da notare è che **c'è una sola via di inserimento**: dalla Home si arriva al passo 1 (ricerca e suggerimenti), poi al passo 2 (dettagli), poi alla Dispensa. Non ci sono diramazioni da scegliere, e questo è il motivo per cui il flusso si legge in un colpo d'occhio.

<div class="flowpage"><img src="00-flusso.png" alt="Flusso delle schermate"/></div>

*(Il diagramma è disponibile anche come file vettoriale, `00-flusso.svg`.)*

---

<a name="9"></a>
## 9. I wireframe, uno per uno

Per ogni schermata: che cosa deve fare, quali scelte di progetto contiene, da quale requisito deriva e quali problemi prevediamo che la Fase 3 solleverà. Quest'ultima parte è importante: un prototipo che non prevede i propri difetti non serve a niente.

---

<div class="screenfig"><h3>Schermata 1 — Home «Oggi»</h3><img src="01-home.png" alt="Schermata 1"/></div>

**Scopo.** Rispondere in tre secondi alla domanda «c'è qualcosa che devo fare adesso?». Non è una dashboard: è una chiamata all'azione.

**Scelte di progetto.**

- La prima card è un prodotto preciso con la data («SCADE DOMANI») e *due* azioni opposte ma entrambe utili: «Cucina ora» e «Ho buttato». L'utente può risolvere il problema in entrambi i modi, e in entrambi i casi l'app impara qualcosa.
- «Cosa cucino stasera» sta in seconda posizione, ma è la stessa informazione della card sopra: le due cose sono collegate, non parallele. Il collegamento visivo è dato dall'uso dello stesso prodotto (la mozzarella) in entrambe.
- La sezione «in scadenza questa settimana» elenca solo tre righe e termina con «Vedi tutto (12)»: la Home non prova a mostrare tutto.
- In fondo, la misura dello spreco in euro. È un dato scomodo, quindi sta in basso e in piccolo: motiva senza accusare.
- Il FAB «Aggiungi» è l'unico punto di ingresso dell'inserimento, ed è marcato con il numero 2 perché porta al passo 1.

**Deriva da:** RF4, RF8, RNF3.
**Problemi previsti (per la Fase 3).** La card prioritaria è ambigua se l'utente ha *due* prodotti in scadenza: quale mostriamo? Il numero «Notifiche 1» nell'app bar duplica l'informazione già presente nella card. Il «Vedi tutto (12)» è un link testuale, non un controllo evidente.

---

<div class="screenfig"><h3>Schermata 2 — Aggiunta rapida, passo 1</h3><img src="02-aggiunta.png" alt="Schermata 2"/></div>

**Scopo.** Far arrivare l'utente al prodotto giusto con un tocco, sfruttando il fatto che nella dispensa di casa i prodotti si ripetono.

**Scelte di progetto.**

- Un solo campo attivo. Nessuna griglia di categorie, nessun form: si scrive o si tocca un suggerimento.
- I suggerimenti sono *dalla dispensa dell'utente*, non da un catalogo: «Mozzarella» compare perché l'ha già comprata. Questo è ciò che rende possibile il tocco singolo, ed è il vero motore della velocità: **l'app impara la spesa ricorrente di quella casa**.
- Cinque righe visibili, con il luogo già indicato a destra: la lista informa anche prima di essere usata.
- «Avanti» è in fondo, largo, raggiungibile col pollice. L'etichetta sotto dice «Salta: salva senza dettagli»: il passo 2 è facoltativo, e va detto prima che l'utente lo scopra da solo.

**Deriva da:** RF1, RF2, RF3, RNF1, RNF2.
**Problemi previsti.** Chi non ha mai usato l'app non ha suggerimenti: il primo inserimento è necessariamente più lento, e la schermata non lo dichiara. «Passo 1 di 2» può spaventare chi ha fretta e ha come obiettivo dieci secondi. Facendo scorrere la lista, il pulsante in fondo resta raggiungibile?

---

<div class="screenfig"><h3>Schermata 3 — Aggiunta rapida, passo 2</h3><img src="03-aggiunta-dettagli.png" alt="Schermata 3"/></div>

**Scopo.** Arricchire il dato senza rallentare: tutto è già compilato, l'utente deve solo confermare o correggere.

**Scelte di progetto.**

- Quantità con quattro soli valori (− 1 2 +) invece di un campo numerico: «niente quantità precise» è ciò che ha chiesto l'utente.
- La scadenza è proposta a sette giorni con la dicitura «predefinito», e c'è una scorciatoia «+7 gg (stima)» per chi non vuole aprire il calendario. Il default è visibile come default, non spacciato per un dato certo.
- «Dove» è una fila di chip (Frigo / Freezer / Dispensa / Cantina), non un menu a tendina: un tocco, nessun livello nascosto.
- Il riquadro «Avviso proposto» mostra *prima di salvare* quale notifica riceverà l'utente. L'utente vede le conseguenze della propria azione mentre la compie.
- Il riquadro «Il percorso completo» rende esplicito l'obiettivo dei due tocchi, così chi valuta nella Fase 3 può verificarlo.

**Deriva da:** RF1, RF2, RF5, RNF1, RNF4.
**Problemi previsti.** Lo stesso campo «scadenza» con due controlli (calendario e scorciatoia +7) è ridondante. La fila di chip «categoria» va a capo su schermi più stretti. Il pulsante «Salva in dispensa» è l'unica azione forte, ma il passo 1 usava «Avanti»: incoerenza di etichetta da verificare.

---

<div class="screenfig"><h3>Schermata 4 — Dispensa</h3><img src="04-dispensa.png" alt="Schermata 4"/></div>

**Scopo.** Dare accesso all'elenco completo e permettere di correggere un dato sbagliato.

**Scelte di progetto.**

- Chip di filtro per luogo con il conteggio accanto («Frigo 11»), così il filtro informa anche prima di essere usato.
- La sezione «Scadono presto» è separata e ha un bordo più marcato: la priorità è strutturale, non affidata all'ordinamento alfabetico.
- Ogni riga ha l'azione «usa», che porta direttamente alle ricette con quel prodotto: è il ponte fra il compito T2 e il compito T3.
- Il resto dell'elenco è volutamente compatto (due righe per prodotto) per mostrare che la dispensa domestica è lunga: 24 prodotti in questo esempio.

**Deriva da:** RF4, RF6, T6.
**Problemi previsti.** «usa» come etichetta di un pulsante è un verbo senza oggetto: in Fase 3 va verificato se è comprensibile. L'ordinamento dentro «Scadono presto» non è dichiarato (per data o per rilevanza?). Il menu «···» per riga nasconde le azioni di modifica: costo di scoperta.

---

<div class="screenfig"><h3>Schermata 5 — Avviso di scadenza</h3><img src="05-notifica.png" alt="Schermata 5"/></div>

**Scopo.** Interrompere l'utente una volta sola, ma con una proposta già pronta.

**Scelte di progetto.**

- Il testo della notifica non dice «in scadenza» (stato) ma dice cosa fare («Usala stasera: pasta con pomodoro e basilico») e aggiunge «Tocca per la ricetta» (azione). È il punto in cui il progetto risponde direttamente alla frustrazione dell'utente.
- L'espansione del banner offre tre azioni, tutte risolutive: cucinare, spostare la scadenza (perché l'utente può sapere che il dato è sbagliato), registrare lo spreco. Non c'è «ignora»: ignorare è non toccare.
- «Nessun'altra notifica per oggi» è scritto esplicitamente: l'app promette di non disturbare più e mantiene la promessa in modo visibile.

**Deriva da:** RF6, RNF4.
**Problemi previsti.** Tre azioni su un banner di lock screen sono molte: il sistema operativo reale difficilmente le consente tutte. La notifica rivela il contenuto della dispensa su schermo bloccato: è un problema di privacy da sollevare in Fase 3. Manca un modo per dire «non mi interessa questo prodotto».

---

<div class="screenfig"><h3>Schermata 6 — Ricette con ciò che ho</h3><img src="06-ricette.png" alt="Schermata 6"/></div>

**Scopo.** Chiudere il cerchio: dal prodotto al piatto, senza chiedere niente all'utente.

**Scelte di progetto.**

- Il filtro «solo ingredienti disponibili» non è un'opzione ma una regola strutturale: le ricette non praticabili non vengono mostrate in elenco principale. La sola eccezione è la terza card, marcata come «ti manca il burro» e tenuta visivamente più leggera: serve a non far sembrare l'app miope, ma non contamina le prime due.
- La card mette in evidenza due informazioni: il tempo (10 min) e il fatto che la ricetta salvi uno spreco. Sono i due criteri con cui Marco decide davvero.
- La prima ricetta è evidenziata con bordo più spesso perché è quella che risolve la mozzarella in scadenza: la priorità della Home si propaga fino a qui.
- In fondo, una sezione separata «usano prodotti in scadenza»: un secondo punto di ingresso allo stesso bisogno.

**Deriva da:** RF5, T3.
**Problemi previsti.** «3/3 ingredienti in casa» richiede una verifica delle quantità che il prototipo non può fare (non registriamo quantità precise). Il pulsante «Apri >» in ogni card è debole come affordance. Se la dispensa è quasi vuota la schermata mostra tre ricette povere: serve uno stato vuoto, non previsto qui.

---

<div class="screenfig"><h3>Schermata 7 — Traccia lo spreco</h3><img src="07-spreco.png" alt="Schermata 7"/></div>

**Scopo.** Rendere visibile un risultato che altrimenti non si vede, senza trasformarlo in un videogioco.

**Scelte di progetto.**

- Il numero grande è in euro, non in chili né in «punti»: è l'unità in cui Marco ragiona quando trova la mozzarella scaduta.
- L'andamento è a sei mesi con barre grigie: si legge il trend, non si confronta con altri utenti.
- L'elenco «cosa ho buttato» con data e valore rende il dato verificabile e non astratto.
- La nota finale è un'osservazione («il 70% dello spreco nasce da freschi dimenticati in frigo»), non un premio: nessun badge, nessuna serie positiva, nessuna notifica di congratulazioni. Il prodotto misura, non giudica.

**Deriva da:** RF7, RF8, T5, T7.
**Problemi previsti.** Il grafico a barre senza scala numerica sull'asse Y non permette di leggere i valori. «-38% vs ottobre» è una comparazione che richiede una base di dati che al primo mese non esiste. La schermata è la più "decorativa" del flusso e rischia di attirare feedback estetici precoci.

---

<a name="10"></a>
## 10. Tracciabilità: dal requisito alla schermata

Tabella di controllo per la Fase 3: ogni requisito deve avere almeno una schermata che lo realizza, e ogni schermata deve servire almeno un requisito (altrimenti è decorazione).

| Requisito | 1 Home | 2 Agg.1 | 3 Agg.2 | 4 Dispensa | 5 Notifica | 6 Ricette | 7 Spreco |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| RF1 registrare prodotto | | ● | ● | | | | |
| RF2 nessun campo obbligatorio | | ● | ● | | | | |
| RF3 suggerimenti | | ● | | | | | |
| RF4 prodotti in scadenza | ● | | | ● | ● | ● | |
| RF5 ricette eseguibili | | | ● | | | ● | |
| RF6 azione dalla notifica | | | | ● | ● | ● | |
| RF7 registra spreco | ● | | | | ● | | ● |
| RF8 spreco leggibile | ● | | | | | | ● |
| RNF1 < 10 secondi | | ● | ● | | | | |
| RNF2 max 3 tocchi | | ● | ● | | | | |
| RNF3 uso a una mano | ● | ● | ● | ● | | | |
| RNF4 una notifica | | | ● | | ● | | |
| RNF5 niente spesa | | | | | | ● | |

Nessuna riga è vuota e nessuna colonna è vuota: tutti i requisiti hanno una schermata, tutte le schermate servono un requisito.

Le due schermate dell'aggiunta (2–3) coprono insieme cinque requisiti. Non è un eccesso: è la conseguenza del fatto che T1 è il compito critico e che su quelle due schermate si gioca l'abbandono o la sopravvivenza del prodotto.

---

<a name="11"></a>
## 11. Che cosa mettiamo sotto esame nella Fase 3

La Fase 3 è l'ispezione di usabilità del prototipo: mettiamo i wireframe sotto esame con i principi di Nielsen e produciamo un elenco di problemi da correggere prima di passare all'alta fedeltà. I numeri nei cerchi sui wireframe sono già gli ancoraggi per quel lavoro.

Le ipotesi che portiamo alla Fase 3 sono queste:

| Dove guardare | Principio | Ipotesi da verificare |
|---|---|---|
| Card prioritaria della Home (1) | Visibilità dello stato del sistema | Capisce perché *quel* prodotto è in evidenza? |
| Riquadro «Avviso proposto» (3) | Visibilità dello stato del sistema | L'anticipazione della notifica è compresa o confonde? |
| Parola «usa» nella Dispensa (4) | Corrispondenza con il mondo reale | Il verbo è comprensibile senza spiegazione? |
| «Ho buttato» come azione (1, 5) | Corrispondenza con il mondo reale | Il linguaggio è accettabile o colpevolizzante? |
| «Salta» nel passo 1 (2) | Controllo e libertà dell'utente | È trovato prima di essere cercato? |
| Etichette «Avanti» / «Salva in dispensa» (2, 3) | Coerenza e standard | La stessa azione ha nomi diversi in punti diversi? |
| Un solo modo di inserire | Modello di interazione | Il modello mentale dell'utente corrisponde a quello del progettista? |

L'ultima riga è la domanda di fondo di questo progetto: **una sola via di inserimento è più facile da imparare o è solo più povera?** La Fase 3 deve dire se la semplicità del modello compensa la mancanza di alternative quando le mani sono occupate.

Il prototipo è già predisposto per l'ispezione: i riquadri tratteggiati contengono le note del gruppo, non elementi d'interfaccia, e possono essere rimossi senza toccare il layout.

---

<a name="12"></a>
## 12. Limiti dichiarati e questioni aperte

Le questioni che non possiamo risolvere in Fase 2 e che vanno portate alla discussione o alla Fase 3.

| # | Questione aperta | Perché è aperta |
|---|---|---|
| 1 | **Una via sola basta?** Chi compra senza lista, al mercato o con le mani occupate non ha una scorciatoia | La Fase 3 deve dire se l'inserimento rapido copre i casi reali o se serve almeno una seconda via |
| 2 | **Il primo utilizzo.** Senza storico non ci sono suggerimenti e l'inserimento è lento | Non affrontato: richiede un onboarding che qui non c'è. È il punto debole dichiarato di questa scelta |
| 3 | **Le quantità.** L'utente ha chiesto di non inserire quantità precise, ma RF5 chiede di sapere se la mozzarella basta per quattro persone | Tensione reale fra RNF1 (velocità) e RF5 (correttezza). Possibile soluzione: quantità «a confezioni» con stima della porzione |
| 4 | **La stima della scadenza.** Il default «+7 giorni» è arbitrario e vale per il latte ma non per la pasta secca | Serve una tabella per categoria, oppure la rinuncia all'avviso sui prodotti a lunga conservazione |
| 5 | **Il multi-utente.** Giulia fa la spesa a turno con Marco | Il prototipo è single-user. La condivisione domestica cambia il modello dei dati, non le schermate |
| 6 | **La privacy della notifica.** Il testo rivela cosa c'è in frigo su schermo bloccato | Da risolvere in Fase 4 o con un'impostazione |
| 7 | **Il confine con la lista della spesa.** L'utente la rifiuta, ma la maggior parte delle app concorrenti la include | Scelta di progetto consapevole: va difesa con i dati dello user test |

---

<a name="13"></a>
## 13. Appendice: i file del prototipo

I wireframe non sono immagini disegnate a mano ma file SVG, così che una modifica dopo la Fase 3 si propaghi a tutte le schermate senza rifare il lavoro. Applicano le convenzioni del §7.1.

**File consegnati.**

| File | Contenuto |
|---|---|
| `00-flusso.svg` | Diagramma del flusso delle schermate |
| `01-home.svg` | Home «Oggi» |
| `02-aggiunta.svg` | Aggiunta rapida, passo 1 |
| `03-aggiunta-dettagli.svg` | Aggiunta rapida, passo 2 |
| `04-dispensa.svg` | Dispensa |
| `05-notifica.svg` | Avviso di scadenza |
| `06-ricette.svg` | Ricette con ciò che ho |
| `07-spreco.svg` | Traccia lo spreco |

**Come si modifica.** I file sono testuali: un'etichetta, una data o una riga di elenco si cambiano modificando il testo dentro il file SVG. Le parole al posto delle icone sono volute e vanno mantenute fino alla Fase 4.

**Nota per la consegna.** I riquadri tratteggiati con le «note di progetto» servono alla discussione e alla Fase 3; nella Fase 4 vanno rimossi o spostati in una scheda di commento accanto alla schermata.

---

*Fine del documento di Fase 2.*
