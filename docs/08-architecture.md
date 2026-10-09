# Architettura preliminare

## Scelta di partenza

React Native + Expo + TypeScript è lo stack proposto per M1, coerente con il percorso discusso. Non è una prova già conclusa di HealthKit, AlarmKit, prestazioni o distribuzione. Scegliere versioni compatibili attuali all’avvio, registrarle nel lockfile. Niente numero SDK inventato in questa specifica.

Expo Go per prototipo UI quando tutte le dipendenze sono supportate; development build per moduli nativi personalizzati. Build cloud come candidato per sviluppo da Windows. Il percorso iOS e gli eventuali costi Apple devono essere verificati prima delle integrazioni.

## Strati

| Strato | Responsabilità |
|---|---|
| Presentazione | Componenti, navigazione, gesture, accessibilità |
| Applicazione | Selezione giornata, modifica attività, proposte, orchestrazione |
| Dominio | Entità, invarianti, tempo, regole deterministiche |
| Adattatori | Persistenza locale, Microsoft, Sunny, HealthKit, AI, notifiche |
| Backend minimo futuro | Segreti server, quote AI, sync dati autorizzati |

Dipendenze verso contratti di dominio; componenti non chiamano Graph direttamente. Nessun microservizio o backend reale per M1. Persistenza locale versionata per fixture modificabili; migrazioni esplicite.

## Organizzazione proposta

- app/ oppure entry equivalente: routing sottile.
- src/ui/: componenti condivisi, tema e accessibilità.
- src/features/today/: schermata e interazioni della giornata.
- src/features/planning/, areas/, capture/: feature successive.
- src/domain/: entità e funzioni pure.
- src/application/: casi d’uso/controller.
- src/adapters/: storage e connettori.
- src/fixtures/: soli dati sintetici.
- tests/: test dei comportamenti.
- docs/: specifiche e decisioni.

Creare solo le cartelle necessarie; struttura proposta, non scaffold già presente.

## Integrazioni future

| Fonte | Contratto | Verifica necessaria |
|---|---|---|
| Outlook | Leggere/scrivere eventi, ricorrenze, eccezioni | OAuth, scope minimi, consenso tenant, conflitti |
| Microsoft To Do | Attività e stato, non duplicare eventi | Identità, liste, delta/aggiornamento e mapping |
| Salute/Watch | Leggere campioni autorizzati e workout | Device/iOS, bridge, qualità dati, permessi revocabili |
| AlarmKit | Sveglie affidabili nell’esperienza richiesta | Versione iOS, supporto nativo e autorizzazione |
| Sunny | Sintesi e scadenze in lettura iniziale | Schema/autenticazione/API reali; nessuna API inventata |
| AI/voce | Intenti strutturati/trascrizione | Provider, privacy, latenza, quote/costi |
| Tragitti | Stime viaggio | Provider, posizione, costo, timestamp e attendibilità |

Non presumere accesso ai vecchi piani ChatGPT. Importazione dei programmi richiede scelta/configurazione esplicita.

## Sincronizzazione proposta

Cache locale + coda operazioni con idempotencyKey, expectedVersion, target e stato. Scrittura remota confermata solo dopo riscontro. Retry controllato; non duplicare record. Conflitti visibili, niente last-write-wins silenzioso su impegni importanti. Non chiamare completata un’operazione ancora in coda.

Separare eliminazione locale da cancellazione nella fonte. Ricorrenze e cancellazioni sono casi espliciti. Revoca permesso sospende il relativo adattatore.

## Dati e privacy

Cloud consentito per sync; dati sanitari dettagliati locali; contesto AI minimo. Proposta: anche derivati sanitari locali finché classificati diversamente. Non inviare descrizioni aziendali all’AI senza ambito autorizzato. Token in storage protetto, chiavi segrete mai nel bundle.

Cancellazione/export/conservazione vanno specificati per classe. Notifiche schermata bloccata con contenuti minimi. Nessun dato reale nelle fixture o nei log pubblici.

## Costi e limiti

Massimo operativo desiderato 5 EUR/mese, idealmente zero. Quote Apple/build a pagamento separate e non autorizzate. Abbonamento ChatGPT non implica API gratuite. Usare contatore server, limiti richieste e fallback; gli alert cloud non sono un tetto rigido di spesa.

Firebase resta un candidato, non una scelta obbligatoria né un progetto Sunny da riutilizzare senza analisi.

## Fonti tecniche da ricontrollare all’implementazione

- [Expo development builds](https://docs.expo.dev/develop/development-builds/introduction/)
- [Expo build setup](https://docs.expo.dev/build/setup/)
- [Expo ambiente iOS](https://docs.expo.dev/get-started/set-up-your-environment/)
- [Apple AlarmKit](https://developer.apple.com/videos/play/wwdc2025/230/)
- [Apple HealthKit permissions](https://developer.apple.com/documentation/healthkit/authorizing-access-to-health-data)
- [Apple account](https://developer.apple.com/help/account/basics/about-your-developer-account/)
- [Graph calendar](https://learn.microsoft.com/en-us/graph/outlook-calendar-concept-overview)
- [Graph To Do](https://learn.microsoft.com/en-us/graph/api/resources/todo-overview)
- [Graph permissions](https://learn.microsoft.com/en-us/graph/permissions-reference)
- [Microsoft consent](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-user-consent)
- [Firebase pricing](https://firebase.google.com/docs/projects/billing/firebase-pricing-plans)

Ricerca precedente dell’8–9 ottobre 2026: documentale, non test empirico. La scelta finale richiede prove.
