# Motore comportamentale

Requisiti acquisiti: determinismo delle decisioni, personalizzazione con feedback, ragionamento quotidiano e settimanale, proattività equilibrata. Algoritmi dettagliati e pesi qui descritti sono proposte da verificare, non formule validate.

## Pipeline

1. Acquisire dati con fonte, qualità e aggiornamento.
2. Separare vincoli duri, preferenze e inferenze.
3. Rilevare cambiamenti rilevanti e conflitti reali.
4. Chiedere ai domini alternative ammissibili.
5. Valutare alternative nel piano della giornata e della settimana.
6. Presentare motivi, conseguenze e incertezze.
7. Applicare dopo conferma o delega valida.
8. Verificare riscontro e raccogliere eventuale feedback.

## Priorità

Prima escludere alternative che violano vincoli non derogabili. Poi confrontare conseguenze delle scadenze, obiettivi espliciti, disponibilità, costo dello spostamento, tempi di trasferimento, capacità e preferenze.

Nessun peso fisso assegnato per sempre a lavoro/salute/relazioni. Nessun punteggio globale decorativo. Inizialmente preferire regole leggibili con tie-break stabile; eventuali pesi devono essere versionati, motivati e verificati con casi reali.

## Adattamento

Quando un’attività non entra più nel piano: mantenere, accorciare se il dominio lo consente, cambiare variante, spostare nella settimana, rinviare o rinunciare. Mostrare anche l’opzione di lasciare tempo libero.

Esempio sintetico: uscita ritardata → allenamento breve compatibile oppure venerdì disponibile. Non comprimere una seduta arbitrariamente: il dominio sportivo deve confermare che la variante preserva una finalità sensata.

## Proattività

Mostrare una proposta primaria alla volta quando utile. Raggruppare eventi correlati; evitare ripetizioni dopo Non ora/Scarta; canale e quiet hours da configurare. Non notificare ogni cambiamento cosmetico o ogni buco in agenda.

## Feedback

Accetta, Modifica, Non ora e Scarta hanno significati diversi. Motivo facoltativo. Ripetuti comportamenti possono suggerire una preferenza; chiedere conferma prima di trasformarla in regola. Consentire modifica e revoca.

## Autonomia: default conservativi proposti

| Azione | Regola iniziale |
|---|---|
| Preparare alternative e aggiornare viste | Automatico |
| Spostare blocco locale flessibile | Solo delega valida oppure conferma |
| Cambiare evento remoto o impegno con altre persone | Conferma |
| Cambiare routine permanente o sveglia | Conferma |
| Modificare allenamento | Variante validata + conferma salvo delega specifica |
| Spostare denaro / inviare messaggi | Fuori perimetro iniziale |

Ogni proposta conserva versione del piano, regole e input usati. Se cambia una fonte, ricalcolare prima di applicare. Risultato parziale non equivale a successo. Annullamento solo quando realmente reversibile.

## AI

L’AI interpreta testo/voce e produce intenti strutturati; validazione deterministica e controllo permessi precedono ogni azione. Non vede credenziali né esegue direttamente adattatori. Dati importati non possono modificare policy.

Senza AI o a budget esaurito: calendario, attività e inserimento guidato continuano a funzionare. M1 non include il motore AI o quello multisport; usare UI dimostrativa esplicita.

## Verifica

Stessi input/versione → stesso risultato; nessuna violazione dei vincoli; feedback non altera preferenze senza conferma; proposte tra più domini; assenza dati dichiarata; nessuna modifica dopo revoca delega.
