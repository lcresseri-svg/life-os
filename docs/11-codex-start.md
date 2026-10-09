# Avvio di sviluppo con Codex

## Ambito del primo task

Implementare M1: home interattiva iPhone con dati sintetici e persistenza locale, seguendo docs/06-ux-specification.md e docs/07-design-system.md. Nessun backend o servizio a consumo necessario per questo task. Il nome definitivo dell’app è aperto.

## Prompt da assegnare a Codex

> Leggi AGENTS.md, README.md e i documenti docs/06-ux-specification.md, docs/07-design-system.md, docs/08-architecture.md, docs/09-roadmap.md e docs/10-decisions.md. Implementa la milestone M1 di docs/09-roadmap.md in React Native + Expo + TypeScript, verificando prima toolchain e compatibilità delle dipendenze. Usa dati sintetici locali. Realizza la home con una sola card visibile, carosello sincronizzato in entrambe le direzioni con la timeline completa sveglia-sonno, pannello inferiore unico per timeline e assistente, espansione del programma e promemoria compatto condizionale. Mantieni sfondo omogeneo blu abisso/viola, saluto con emoji e card colorate senza neon. Consenti dettaglio e modifica locale di un’attività con aggiornamento coerente di tutte le viste e persistenza. Prevedi inserimento guidato; dichiara AI, voce e integrazioni non operative. Verifica logica temporale, sincronizzazione, persistenza e layout accessibile. Aggiorna README con comandi reali e istruzioni di prova su iPhone. Consegna codice, test eseguiti, limitazioni e modifiche reviewabili. Non attivare servizi a pagamento, non collegare account reali e non pubblicare sugli store.

## Sequenza pratica

1. Ispezionare repo e istruzioni; verificare Node/package manager/ambiente disponibili.
2. Scegliere Expo SDK corrente compatibile e dipendenze minime. Registrare scelta e lockfile.
3. Inizializzare progetto senza sovrascrivere docs/README/AGENTS.
4. Implementare modello minimo e fixture prima delle gesture.
5. Costruire tema, home, controller unico, pannello e modifica.
6. Implementare storage locale, fallback ed errori.
7. Eseguire verifiche della milestone.
8. Documentare avvio e limiti; commit/PR secondo workflow disponibile.

Non serve che il proprietario ricopi questa conversazione. Per dubbi minori usare giudizio e documentare; chiedere soltanto decisioni che cambiano perimetro, dati, costo o comportamento sostanziale.

## Fixture sintetica proposta

Data dimostrativa 2026-10-09, timezone Europe/Rome; risveglio 07:15, sonno 23:00.
Esempio: preparazione 07:15–08:00; lavoro 08:00–12:30; pranzo 12:30–13:30; lavoro 13:30–17:30; spazio libero 17:30–18:30; passeggiata 18:30–19:00; spazio libero 19:00–19:30; cena 19:30–21:00; tempo personale 21:00–23:00.
Promemoria opzionale «Chiama una persona · in serata», senza contatto reale.

Tutti gli esempi sono sintetici, non ricostruzioni di una vera agenda. La passeggiata di 30 minuti occupa circa 3,17% della fascia sveglia-sonno di 945 minuti; non un quinto della barra. Un’area di tocco ampia non deve falsificare la durata visiva.

Aggiungere casi: giornata vuota, promemoria assente, notte oltre mezzanotte, appuntamenti sovrapposti e molti eventi brevi. Fixture esplicitamente marcate Demo nella prima esperienza, senza sovraccaricare la home.

## Deliverable e limiti

- Codice sorgente e manifest/lockfile coerenti.
- Comandi effettivi per installazione, avvio, typecheck e test.
- Istruzioni Expo Go se compatibile; eventuali limiti del relativo ambiente.
- Prove eseguite e non eseguite dichiarate; screenshot se ottenibili.
- Nessuna dichiarazione «testato su iPhone» senza prova reale.
- README spiega che AI, Salute, Outlook, Sunny, coach e sveglie sono tappe future.

Per un prototipo visivo non serve una distribuzione App Store. La successiva development build iOS e i moduli nativi richiedono verifiche/costi separati.
