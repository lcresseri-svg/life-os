# Roadmap, backlog e criteri di accettazione

## Distinzione essenziale

M1 è un prototipo tecnico/UX. Il primo prodotto richiesto comprende integrazioni, input AI e coach completo per quattro sport. Non rinominare M1 «MVP completo» né ridurre il perimetro finale senza decisione dell’utente.

| Tappa | Risultato | Dipendenze |
|---|---|---|
| M0 — attuale | Documentazione corrente nel repository | Nessun codice di prodotto |
| M1 | Home interattiva, dati sintetici persistiti localmente | Toolchain e dipendenze compatibili |
| M2 | Pianifica, attività, note/progetti e modello locale coerente | Esito M1 |
| M3 | Verifiche native e connettori, prima base integrata | Device/iOS, account, costi e permessi |
| M4 | Coordinamento giorno/settimana e interpretazione AI | Regole, quote, conferme e sync |
| M5 | Coach quattro sport e carico complessivo, Sunny in lettura | Specifiche scientifiche e contratto Sunny |
| M6 | Pilota personale integrato | Accessibilità, affidabilità, budget e osservabilità |

M3 può includere prove limitate precoci per ridurre rischio senza introdurre tutte le integrazioni in M1. M4 e M5 richiedono progettazione specifica; non inventare formule o capacità.

Successive evoluzioni: operazioni quotidiane Sunny fase B, iPad/desktop, deleghe avanzate, personalizzazione più sofisticata. Modalità vacanza: requisito acquisito, collocazione e dettagli aperti.

## M1: backlog operativo

| ID | Consegna | Accettazione |
|---|---|---|
| M1-01 | Setup Expo/TS, tema, branding provvisorio | Avvio documentato e typecheck eseguito |
| M1-02 | Dominio e fixture | Giorno pieno/vuoto, passaggio mezzanotte, sovrapposizione |
| M1-03 | Home e card singola | Nessuna card laterale; resize e testo grande utilizzabili |
| M1-04 | Timeline completa | Risveglio/sonno dinamici; posizione/durata corrette |
| M1-05 | Selezione condivisa | Swipe ↔ cursore ↔ schedule senza loop o scritture |
| M1-06 | Pannello unico | Timeline/chat stessa superficie; espansione schedule; tastiera |
| M1-07 | Promemoria | Riga compatta quando rilevante; nessun vuoto quando assente |
| M1-08 | Dettaglio e modifica locale | Cambio orario aggiorna tutte le viste; persiste al riavvio |
| M1-09 | Input guidato e demo trasparente | Crea Task localmente; AI/voce non simulate come operative |
| M1-10 | QA e consegna | Test, comandi, limiti, screenshot e istruzioni iPhone |

Pianifica/Aree possono iniziare come schermate navigabili minime con stato esplicito; non fingere che connettori e coach esistano.

## Verifiche significative M1

- Mappatura posizione↔tempo agli estremi e al centro; scala proporzionale.
- Risveglio/sonno oltre mezzanotte; orari incoerenti rifiutati; casi ora legale.
- Selezione card muove cursore; drag seleziona elemento corretto; intervallo libero e sovrapposto.
- Navigazione nel tempo non modifica eventi.
- Modifica orario/durata rispetta invarianti e aggiorna card/timeline/lista.
- Storage versionato, ripartenza coerente; errore salvataggio visibile.
- Drag pannello diverso da drag timeline e swipe card.
- Safe area, tastiera, Reduce Motion, testi grandi e VoiceOver.
- Nessun costo/servizio/permesso esterno attivato all’apertura demo.

## Criteri prodotto integrato

Outlook/To Do convergono senza duplicazioni; azioni autorizzate e tracciabili; offline esplicito; dati sanitari non esportati implicitamente; quattro sport programmati e analizzati con validazione; sveglie provate sul telefono; costi misurati entro il budget; feedback controllabile.

Non promettere date di completamento prima delle prove tecniche e della specifica del coach.
