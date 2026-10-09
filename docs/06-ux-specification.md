# Specifica UX corrente

9 ottobre 2026. Le scelte esplicite della home sono acquisite. I dettagli di gestione degli stati seguenti sono specifiche esecutive proposte, da verificare nel prototipo.

## Oggi: composizione vincolante

1. Identità provvisoria discreta e profilo.
2. Saluto con emoji: esempio «Ciao Luca 👋», nome configurabile. Nessuna frase motivazionale.
3. Navigazione Oggi / Pianifica / Aree stabile e compatta.
4. Titolo giornata e riferimento temporale della selezione.
5. Una grande card attività, centrale e predominante.
6. Indicatori discreti di scorrimento; nessuno scorcio delle altre card ai lati.
7. Eventuale promemoria compatto.
8. Unico pannello dal basso, contenente timeline e input assistente.

Contenuti centrali scorrevoli se necessario. Il pannello rispetta safe area e non copre azioni della card; riservare in basso lo spazio della sua altezza misurata. Non copiare ciecamente le proporzioni molto alte dei mockup raster.

## Carosello e timeline

Una card alla volta; swipe orizzontale con arresto su elemento. Selezionare una card porta il cursore al suo inizio; trascinare il cursore seleziona la card pertinente. Tap su intervallo seleziona l’elemento. La freccia nella card apre il dettaglio, non segna completato.

Usare un solo stato di selezione con origine dell’interazione per evitare cicli card→cursore→card. Durante il drag aggiornare fluidamente la selezione, senza scritture dati. Al rilascio agganciare a un elemento pertinente secondo regola documentata.

### Regole esecutive proposte

- Nei buchi: mostrare una card «Tempo libero» per l’intervallo, senza inventare attività.
- Se più impegni si sovrappongono: indicare conflitto e offrire la scelta; non nasconderne uno.
- Un’attività senza orario non occupa una posizione arbitraria: resta nel promemoria o in Da collocare.
- Attività passate sono consultabili; lo stato non diventa completato.
- Distinguere selezione temporale da Adesso: navigare nel futuro non cambia l’ora corrente.
- Conservare selezione tornando dai dettagli; non riposizionare mentre l’utente esplora.
- Se elemento selezionato è rimosso, scegliere il vicino cronologico e comunicarlo.
- Consentire precedente/successivo e scelta da lista come alternative alle gesture.

## Timeline dell’intera giornata

Estremi = risveglio previsto del giorno e sonno previsto, con icone sole/luna e orari. Mai hardcoded 17:30–20:30. Esempio 07:15–23:00 dimostrativo, non preferenza dell’utente.

Binario sottile con segmenti arrotondati ravvicinati e piccoli spazi; colori coerenti con i domini. Marker a fumetto/pin sopra l’intervallo selezionato. Tacche e poche etichette leggibili sotto. Geometria quasi piatta con al massimo lieve curvatura, secondo ultima correzione. Non ripristinare la grande fascia arcuata o i cinque riquadri con icone.

La posizione rappresenta tempo reale: x = larghezza × (istante - inizio) / (fine - inizio), con clamp ai limiti. Durate proporzionali; hit area maggiore separata dalla larghezza visiva per eventi brevi. Gli intervalli liberi sono distinguibili; gli eventi sovrapposti non sono fusi silenziosamente. Giorni oltre mezzanotte gestiti con istanti completi.

Se ci sono impegni oltre gli estremi configurati, segnalarli e consentire estensione vista: non tagliarli senza indicazione.

## Unico pannello inferiore

Una superficie continua ancorata al fondo, angoli superiori morbidi, lieve o nulla curvatura. Header piccolo, senza titolo dell’attività ripetuto. Maniglia centrale. Niente testo «Espandi». Timeline e input assistente sono DENTRO la stessa scheda, non due card separate.

Stati:
- Compatto: titolo/data, timeline completa, input.
- Programma: trascinamento verso l’alto o tap sulla maniglia apre la lista cronologica con orari, fonti e stati.
- Inserimento/conversazione: tap input porta il composer sopra tastiera; lista/conversazione scorre internamente.
- Chiusura: ritorno al compatto, mantenendo selezione e bozza.

La maniglia è un vero controllo accessibile, con etichetta Apri programma/Chiudi programma anche senza scritta visibile. Evitare pannelli annidati e scroll in conflitto. La tastiera non copre input o pulsanti.

## Promemoria condizionale

Una riga piccola: icona, testo e indicazione temporale sintetica. Niente grande card con titolo Da ricordare e icona gigante. Presente solo per un elemento rilevante; senza promemoria nessun placeholder né altezza riservata. In M1 rilevanza esplicita nelle fixture, non inferenza AI finta.

## Pianifica e Aree

Pianifica: sette giorni compatti, giorno scelto, Da collocare espandibile, revisione settimanale. Stati confermato/indicativo/proposta; modifica di singola occorrenza distinta dalla serie.

Aree in ordine stabile: Salute e sport; Finanze; Progetti e obiettivi; Note e idee. Lo stesso elemento apre lo stesso dettaglio da ogni vista. Profilo per preferenze, routine, integrazioni e deleghe.

## Input

Plus apre inserimento guidato; testo/voce interpretati in tappe successive. Registrazione solo dopo tap e permesso, con stop visibile; trascrizione correggibile. Nel prototipo nessuna falsa risposta AI: disponibilità esplicita e fallback guidato.

Prima di azioni importanti: bozza verificabile, effetti, applica/modifica/non ora/scarta. Una conferma guidata sufficiente non va duplicata. Esiti parziali espliciti; nessun «salvato» remoto prima del riscontro.

## Stati indispensabili

Giornata vuota, solo un elemento, molti elementi, promemoria assente, intervallo libero, sovrapposizioni, offline, dati vecchi, permesso negato, errore salvataggio, testo grande, Reduce Motion, ritorno da dettaglio, cambio giorno/fuso.

Le animazioni non devono far muovere automaticamente la selezione durante una lettura.
