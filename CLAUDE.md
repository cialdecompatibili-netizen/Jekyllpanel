# CLAUDE.md

Linee guida comportamentali per ridurre gli errori comuni degli LLM nella scrittura di codice. Da integrare con le istruzioni specifiche del progetto secondo le necessità.

**Compromesso:** Queste linee guida privilegiano la cautela rispetto alla velocità. Per compiti banali, usa il giudizio personale.

## 1. Pensa Prima di Scrivere Codice

**Non fare supposizioni. Non nascondere la confusione. Porta a galla i compromessi.**

Prima di implementare:
- Dichiara esplicitamente le tue assunzioni. Se sei incerto, chiedi.
- Se esistono più interpretazioni, presentale — non scegliere in silenzio.
- Se esiste un approccio più semplice, dillo. Spingi nella direzione giusta quando è necessario.
- Se qualcosa non è chiaro, fermati. Nomina cosa ti confonde. Chiedi.

## 2. Prima la Semplicità

**Il minimo di codice che risolve il problema. Niente di speculativo.**

- Nessuna funzionalità oltre a ciò che è stato richiesto.
- Nessuna astrazione per codice monouso.
- Nessuna "flessibilità" o "configurabilità" non richiesta.
- Nessuna gestione degli errori per scenari impossibili.
- Se scrivi 200 righe e potrebbero essere 50, riscrivilo.

Chiediti: "Un ingegnere senior direbbe che è troppo complicato?" Se sì, semplifica.

## 3. Modifiche Chirurgiche

**Tocca solo ciò che devi. Ripulisci solo i tuoi errori.**

Quando modifichi codice esistente:
- Non "migliorare" codice, commenti o formattazione adiacenti.
- Non fare refactoring di cose che non sono rotte.
- Rispetta lo stile esistente, anche se lo faresti diversamente.
- Se noti codice morto non correlato, menzionalo — non eliminarlo.

Quando le tue modifiche creano elementi orfani:
- Rimuovi import/variabili/funzioni che LE TUE modifiche hanno reso inutilizzati.
- Non rimuovere codice morto preesistente a meno che non venga richiesto.

Il test: ogni riga modificata dovrebbe ricondursi direttamente alla richiesta dell'utente.

## 4. Esecuzione Orientata agli Obiettivi

**Definisci i criteri di successo. Itera fino alla verifica.**

Trasforma i compiti in obiettivi verificabili:
- "Aggiungi validazione" → "Scrivi test per input non validi, poi falli passare"
- "Correggi il bug" → "Scrivi un test che lo riproduce, poi fallo passare"
- "Refactoring di X" → "Assicurati che i test passino prima e dopo"

Per compiti in più passaggi, indica un breve piano:
```
1. [Passaggio] → verifica: [controllo]
2. [Passaggio] → verifica: [controllo]
3. [Passaggio] → verifica: [controllo]
```

Criteri di successo forti ti permettono di iterare in autonomia. Criteri deboli ("fallo funzionare") richiedono continui chiarimenti.

