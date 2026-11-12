# Decisioni aperte e ipotesi progettuali

Il registro distingue le scelte già adottate come ipotesi di lavoro dalle questioni che richiedono una verifica con le persone partecipanti alla Fase 5. Le indicazioni provvisorie consentono di mantenere coerenza tra le specifiche; non costituiscono risultati di ricerca già confermati.

---

## Q1 · Verbo dell'azione centrale — da confermare

La Fase 3 ha rilevato l'uso non uniforme di «usa», «Apri», «Cucina ora» e «Cucina stasera» (E05). La specifica adotta **«Cucina»** come formulazione principale.

- Alternative considerate: `Prepara`, `Cucina ora`, `Cosa cucino`.
- Rilevanza: l'etichetta compare in più schermate e nella notifica.
- Ipotesi di lavoro: mantenere `Cucina`; validare la comprensione durante i test.

## Q2 · Criterio del prodotto in evidenza nella Home — da definire

La Home presenta un prodotto nella card prioritaria. I wireframe non stabiliscono il criterio di selezione.

- Ipotesi di lavoro: scegliere la data di scadenza più vicina; a parità, il valore economico più alto.
- Impatto: il testo relativo agli altri prodotti in scadenza dipende dal criterio e dall'intervallo temporale adottato.
- Verifica: osservare se la gerarchia risulta comprensibile e pertinente.

## Q3 · Tema scuro — fuori perimetro della Fase 4

L'uso serale in cucina rende plausibile una modalità scura, che non rientra però nel prototipo corrente.

- Specifica attuale: tema chiaro; variabili predisposte senza realizzare una variante scura.
- Verifica prevista: rilevare nella Fase 5 le preferenze e le abitudini relative alla modalità scura.

## Q4 · Impostazione iniziale della privacy delle notifiche — ipotesi da validare

L'interruttore `Nascondi i dettagli sul blocco schermo` è previsto attivo per impostazione predefinita, considerando che il telefono può essere visibile ad altre persone in cucina.

- Possibile criticità: il testo generico `Hai una scadenza` è meno informativo di `Mozzarella: scade domani`.
- Contesto: la Fase 1 ha rilevato il bisogno di sapere quale prodotto sta per scadere.

## Q5 · Rappresentazione dei valori nel grafico dello spreco — specificata, da verificare

La Fase 3 ha rilevato che un grafico a barre senza valori non comunica con chiarezza (E31). La specifica corrente prevede valori sempre visibili e mette in evidenza il mese corrente con `accent/urgent`.

Restano da validare l'opportunità di una linea di riferimento (per esempio la media mensile) e la leggibilità dei valori in tutte le dimensioni previste.

## Q6 · Quantità nel flusso di aggiunta — da verificare con utenti

Il controllo quantità (`− 1 2 +` e `confezione`) deriva dalla Fase 2. La Fase 1 segnalava scarso interesse per quantità precise; la Fase 3 ha inoltre rilevato che le ricette potrebbero aver bisogno di dosi.

- Questione: la quantità è necessaria al pianificatore dei pasti o è un dato accessorio?
- Se non necessaria, il controllo può essere rimosso e la schermata S03 semplificata.
- Se necessaria, il modello potrebbe riferirsi alle porzioni anziché alle confezioni.
- Verifica: includere il controllo nella valutazione e considerarlo candidato a revisione.

## Q7 · Immagini dei prodotti — decisione provvisoria

I wireframe presentano segnaposto grigi. Le alternative considerate per l'alta fedeltà sono fotografie di prodotti, icone per categoria o contenuti senza immagine.

- Specifica attuale: segnaposto neutri con icona `image`.
- Motivo: scelta indipendente da risorse fotografiche esterne e coerente con il livello di prototipazione.
- Un'eventuale adozione di fotografie richiede una decisione sul repertorio e sulle relative risorse.

## Q8 · Gesture — fuori perimetro

Non sono previste pressione prolungata, swipe o trascinamento. Le azioni restano accessibili tramite controlli visibili, a favore della scopribilità.

## Q9 · Notifica di riepilogo settimanale — da verificare nella Fase 5

S13 include la voce `Riepilogo settimanale`, non documentata nelle fasi precedenti e ispirata a modelli ricorrenti nelle applicazioni concorrenti.

- Rischio: possibile incoerenza con la promessa di al massimo una notifica al giorno per prodotto e con le evidenze della Fase 1 sulle notifiche frequenti.
- Stato: l'interruttore è previsto disattivato; utilità e coerenza della funzione richiedono validazione.

## Q10 · Destinazione del pulsante «Notifiche» nella Home — da definire

La Home presenta un pulsante `Notifiche` con icona `bell`; la tab bar non include un'area Notifiche e il flusso non ne specifica la destinazione.

- Rischio: il controllo potrebbe risultare privo di destinazione.
- Stato: il collegamento non è definito nelle specifiche e richiede una decisione prima della validazione del flusso.

## Q11 · Numero di barre nel grafico mensile (S10) — decisione provvisoria

`GraficoBarre` prevede 4, 6 o 12 barre. S10 è specificata con quattro barre, una per ciascun prodotto buttato nel mese; S07 ne presenta sei.

- Rischio: un numero variabile di prodotti può modificare larghezza e distribuzione delle barre.
- Requisito: il componente deve mantenere una griglia leggibile al variare dei dati rappresentati.

## Q12 · Testo «usala stasera» nell'esempio di notifica — da validare

Il riquadro `Cosa riceverai` di S03 include la frase descrittiva `La mozzarella scade domani, usala stasera`.

- La frase non è un controllo interattivo; tuttavia può essere interpretata come un comando.
- Verifica prevista: accertare nella Fase 5 la lettura spontanea del testo e riformularlo se necessario.

## Q13 · Etichetta «Oggi» nella tab bar — da validare

La tab attiva in S01 è denominata `Oggi`; le altre voci identificano aree (`Dispensa`, `Ricette`, `Spreco`). La differenza di categoria semantica può incidere sulla comprensione della navigazione.

## Q14 · Interpretazione dell'esempio di notifica in S03 — da validare

La stessa frase esemplificativa compare nel riquadro `Cosa riceverai`. La Fase 5 verificherà che venga riconosciuta come esempio informativo e non come azione disponibile nella schermata.
