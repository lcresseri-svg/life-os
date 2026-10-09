# Modello concettuale e contratti dati

Specifica proposta per implementazione, non schema database già esistente.

| Entità | Significato | Campi/relazioni essenziali |
|---|---|---|
| Event | Appuntamento a tempo, anche esterno | start/end oppure allDayDate, timezone, fonte, ricorrenza |
| Task | Azione da compiere | stato, scadenza opzionale, durata stimata, flessibilità, progetto |
| ScheduledBlock | Collocazione di un’attività | taskId, start/end, indicativo/confermato, versione |
| Intention | Desiderio entro un periodo senza data precisa | periodo, dominio, priorità esplicita opzionale |
| Project | Risultato finito | attività, note, obiettivi |
| Goal | Risultato con criterio di progresso | metrica/criterio, orizzonte, programmi/progetti |
| Habit/Routine | Comportamento ripetuto/regola di frequenza | finestre, frequenza, eccezioni, versione |
| Preference | Indicazione desiderata | fonte, ambito, validità, conferma |
| Constraint | Limite duro o derogabile | ambito, durata, autorità, derogabilità |
| ContextObservation | Fatto o stima contestuale | fonte, timestamp, qualità, validUntil |
| Note | Contenuto autonomo | testo, collegamenti, classificazione opzionale |
| SportSessionPlan | Allenamento prescritto | sport, obiettivo, struttura, versione |
| RecordedWorkout | Allenamento realmente registrato | fonte, misure, tempi, qualità |
| Proposal | Alternativa prima dell’applicazione | azioni, motivi, impatti, baseVersion, permessi |
| Feedback | Risposta a proposta/interazione | accetta/modifica/non ora/scarta, motivo opzionale |
| Delegation | Permesso operativo esplicito | azioni, limiti, scadenza, revoca |
| DayPlan | Vista aggregata del giorno | data locale, timezone, wake/sleep, riferimenti agli elementi |

## Invarianti

- Scadenza di Task diversa da ora di esecuzione; un Task può avere più blocchi.
- Un Evento sincronizzato non è duplicato come Task automaticamente.
- Sessione pianificata diversa dall’eseguito; associazione esplicita.
- Passato non significa completato.
- Preferenza osservata non diventa vincolo senza conferma.
- Eventi all-day non usano la mezzanotte UTC come rappresentazione implicita.
- ID interni stabili; mapping esterno composto da provider/account/container/externalId.
- Metadati comuni: id, version, createdAt, updatedAt, origin, privacyClass, syncState.
- L’UI non usa indice del carosello come identità persistente.

## Tempo

Memorizzare istanti e timezone quando necessari; preservare date locali per all-day e intenzioni. Intervalli [inizio, fine), fine successiva all’inizio. Gestire attraversamento mezzanotte e ora legale; non assumere giorni sempre di 24 ore.

Wake/sleep sono dati giornalieri configurabili, distinti da orari effettivamente osservati. Se mancanti, dichiarare una finestra dimostrativa o chiedere configurazione; non presentarla come abitudine appresa.

## Stato UI condiviso

selectedItemId, selectedInstant, displayDay e selectionSource (card/timeline/schedule) appartengono al controller della giornata. Stato di navigazione separato dai dati persistenti. now è distinto da selectedInstant.

Card, timeline e schedule derivano dallo stesso DayPlan. Le scritture passano dal caso d’uso, non da componenti isolati.

## Fonti

Outlook autorevole sugli eventi remoti; To Do sulle attività remote; Sunny sui dati finanziari; Salute sui campioni originali. Life OS possiede estensioni locali, intenzioni, note, routine, proposte e piano. Analisi derivate versionate e distinguibili dalle misure.

M1: implementare solo Task, ScheduledBlock, DayPlan, promemoria e stato di selezione necessari alla demo; non costruire database vuoti per tutte le entità future.
