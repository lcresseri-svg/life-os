# Life OS — nome di lavoro

Sistema operativo personale per organizzare tempo, impegni, salute, sport, finanze, progetti e idee in una sola esperienza quotidiana.

**Il nome finale dell’app è da scegliere.** Il repository resta `life-os`; branding, display name e identificatori di distribuzione non sono definitivi.

## Stato al 9 ottobre 2026

Repository di **specifiche e progettazione**, pronto per il passaggio a Codex. Nessuna app implementata, nessun servizio collegato e nessuna integrazione verificata sul dispositivo in questa consegna.

La prima tappa proposta è un prototipo iPhone navigabile con dati sintetici. Non equivale al prodotto completo richiesto: il coach multisport, le integrazioni e il motore comportamentale restano nel percorso.

## Leggere in questo ordine

1. [Istruzioni per Codex](AGENTS.md)
2. [Visione e perimetro](docs/01-product-vision.md)
3. [Mappa funzionale](docs/02-functional-map.md)
4. [Modello concettuale](docs/03-domain-model.md)
5. [Motore comportamentale](docs/04-behavior-engine.md)
6. [Percorsi quotidiani e settimanali](docs/05-user-journeys.md)
7. [UX e interazioni](docs/06-ux-specification.md)
8. [Design system e riferimento home](docs/07-design-system.md)
9. [Architettura e integrazioni](docs/08-architecture.md)
10. [Roadmap e verifiche](docs/09-roadmap.md)
11. [Registro decisioni](docs/10-decisions.md)
12. [Avvio operativo per Codex](docs/11-codex-start.md)
13. [Rischi e questioni aperte](docs/12-open-questions.md)

## Home corrente

Saluto con emoji → navigazione Oggi/Pianifica/Aree → una grande card attività alla volta → eventuale promemoria compatto → unico pannello inferiore con timeline completa della giornata e input assistente.

Card e cursore temporale sono sincronizzati in entrambe le direzioni. Il pannello si espande per mostrare il programma. Sfondo uniforme blu abisso/viola scuro; colori più ricchi nelle card, senza effetto LED. Fotografie rinviate.

## Prossima consegna

Seguire [il brief di avvio](docs/11-codex-start.md). Stack di partenza proposto: React Native, Expo, TypeScript. Validare le versioni compatibili prima di installare dipendenze.

## Manutenzione

Le specifiche del 9 ottobre prevalgono sulle precedenti bozze per gli aspetti UI aggiornati. Le decisioni approvate non vanno riaperte a ogni task. Proposte tecniche e requisiti sono distinti. Ogni modifica sostanziale aggiorna documento pertinente e registro decisioni.

Repository pubblico: utilizzare solo dati sintetici. Non caricare calendari, esportazioni sanitarie, transazioni, credenziali o conversazioni personali.

Nessuna licenza software è stata scelta dal proprietario.
