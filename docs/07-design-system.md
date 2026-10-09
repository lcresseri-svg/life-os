# Design system e riferimento visivo della home

## Direzione acquisita

Immersive Editorial UI / Cinematic Wellness / Soft Glassmorphism. Futuristico ma umano; profondità, fluidità e semplicità. L’ultima home concordata è descritta qui e in UX; gli studi precedenti sono superati nei punti corretti.

### Specifica visiva finale

- Sfondo OMOGENEO blu abisso, blu notte e viola scuro. Nessuna macchia verde, rosa o turchese diffusa dietro tutta la pagina.
- Card con colori più ricchi dello sfondo: verde/teal, blu, viola, corallo e accenti ambra. Sfumature morbide, non slavato e non effetto LED.
- Eliminare bordi neon, riflessi gialli bruciati e glow perimetrali marcati.
- Grande card selezionata; nessuna anteprima delle altre ai lati.
- Serif editoriale per saluto/titoli; sans leggibile per dati e controlli.
- Nessuna fotografia per ora; valutazione delle immagini rinviata.
- Nessuna frase motivazionale. Saluto con emoji.
- Timeline e chat in un solo pannello inferiore compatto, quasi piatto.
- Promemoria riga piccola e facoltativa.

## Token iniziali proposti, da tarare sul dispositivo

| Ruolo | Valore candidato |
|---|---|
| background.base | #071329 |
| background.deep | #080E24 |
| background.violet | #17153A |
| surface.base | #142442 |
| surface.raised | #1B2C4C |
| text.primary | #F3F5FC |
| text.secondary | #B7C6E7 |
| accent.blue | #4989DE |
| accent.teal | #20B39F |
| accent.green | #39C895 |
| accent.coral | #E68188 |
| accent.violet | #9873C9 |
| accent.amber | #EDBB68 |

Questi codici non sono estratti esatti dai pixel né verificati per contrasto. Misurare ogni coppia testo/superficie reale, inclusi gradienti. Verde e rosso/corallo distinguono ambiti, non indicano automaticamente bene/male. Errore/conferma hanno simboli e testo oltre al colore.

Spaziatura base proposta 4/8/12/16/24/32. Margini laterali 16–24 pt secondo viewport. Card principale raggio 28–36 pt; controlli 16–24; pannello raggio superiore 24–32. Tap target almeno 44×44 pt anche se icona piccola.

## Tipografia

Titoli serif editoriali simili alla direzione Canela/New York; sans per funzionalità. Non includere font proprietari senza licenza. Scegliere una serif distribuibile con licenza adeguata e fallback; registrare fonte/licenza prima di aggiungere file.

Scala proposta: saluto 32–40 pt; titolo card 28–36; sezioni 22–26; corpo 16–17; metadati 13–15. Supportare Dynamic Type, andare a capo e ridurre vuoti prima di troncare testo.

## Componenti da costruire

GreetingHeader, MainNavigation, ActivityCard, ActivityPager, ContextReminderRow, DayTimeline, TimelineSegment, SelectionPin, DayBottomSheet, DayScheduleList, AssistantComposer, DetailView, StatusLabel, EmptyState.

Nomi tecnici proposti; non giustificano micro-astrazioni inutili. Stili e token centralizzati. Nome app/displayName in configurazione unica modificabile, senza scegliere ora bundle identifier definitivo.

## Motion

Swipe e trascinamento seguono il dito; transizioni brevi e morbide, spring moderato. Apertura del pannello mantiene continuità. Niente parallasse obbligatoria o gradienti continuamente animati che consumano batteria. Reduce Motion elimina spostamenti non necessari; accessibilità resta equivalente.

## Riferimenti e limiti

IMG_1716 è il riferimento originario di struttura. Il ritaglio condiviso della barra ha chiarito: unico binario con segmenti arrotondati, tacche sotto e pin a fumetto sopra. Le revisioni successive chiedono meno curvatura, giornata intera e unificazione con la chat.

I raster di conversazione NON sono incorporati in questa consegna GitHub: non usare link effimeri come asset e non presumere di trovarli nel repository. Questa specifica conserva le scelte eseguibili. Gli screenshot generati contengono proporzioni e orari illustrativi, non coordinate o modelli temporali autorevoli.

Non pubblicare la reference di terzi né introdurla nel bundle come asset dell’app. Quando si aggiunge un mockup approvato disponibile, conservarlo in docs/design/references con origine e stato; la specifica testuale più recente prevale su errori del raster.

## QA visiva

Verificare un iPhone piccolo e uno grande, safe area, tastiera, testo ingrandito, contrasto, colori senza dipendenza esclusiva, riduzione trasparenza e movimento. Non imporre che tutta la schermata entri senza scroll se compromette leggibilità.
