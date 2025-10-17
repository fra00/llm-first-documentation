# Sistema di Test Comprensione LLM per Confronto Formati

## Obiettivo

Testare quanto efficacemente un LLM comprende, ritiene e processa informazioni in diversi formati di testo, attraverso verifiche pratiche (non autovalutazioni).

---

## 📋 FASE 1: LETTURA E ANALISI INIZIALE

### Prompt per l'LLM:

```
Leggi attentamente il seguente testo. Non rispondere ancora, limitati a processarlo.

[INSERIRE QUI IL TESTO DA ANALIZZARE]

Conferma di aver letto il testo scrivendo solo: "Testo processato. Pronto per la verifica."
```

**⏱️ Pausa:** Aspetta la conferma prima di procedere alla Fase 2

---

## 🧪 FASE 2: TEST DI COMPRENSIONE

### Prompt di Verifica:

```
Ora verificherò la tua comprensione del testo. Rispondi SENZA rileggere il testo originale, basandoti solo su ciò che hai compreso e memorizzato.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 1: RECALL COMPLETO
Elenca TUTTI i concetti principali presenti nel testo.
Per ogni concetto indica:
- Nome del concetto
- Descrizione breve
- Importanza nel contesto (Primaria/Secondaria/Marginale)

Formato richiesto:
1. [Concetto] - [Descrizione] - [Importanza]
2. [Concetto] - [Descrizione] - [Importanza]
...

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 2: DETTAGLI SPECIFICI
Rispondi a queste domande sui dettagli:

a) Quali dati numerici/quantitativi erano presenti? (numeri, percentuali, date, quantità)
b) Quali nomi propri/termini tecnici erano menzionati?
c) Quali esempi specifici erano forniti?
d) Quali relazioni causa-effetto erano descritte?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 3: MAPPA CONCETTUALE
Crea una mappa concettuale in formato testuale che mostri:
- Gerarchia dei concetti (principale → secondario → dettaglio)
- Relazioni tra concetti (usa →, ↔, ⊃, etc.)
- Dipendenze e collegamenti logici

Formato richiesto:
```

[CONCETTO PRINCIPALE]
├─→ [Sottoconcetto A]
│ ├─→ [Dettaglio 1]
│ └─→ [Dettaglio 2]
├─→ [Sottoconcetto B]
│ └─↔ [Relazione con A]
└─→ [Sottoconcetto C]

```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 4: DISCRIMINAZIONE CONCETTUALE
Identifica e confronta i concetti che potrebbero essere confusi:

Per ogni coppia di concetti simili, spiega:
- Differenze chiave
- Contesti d'uso diversi
- Relazioni reciproche

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 5: STRUTTURA E ORGANIZZAZIONE
a) Come era organizzato il testo? (sequenziale, gerarchico, circolare, comparativo, etc.)
b) Qual era il filo logico principale?
c) Quali sezioni/parti erano presenti?
d) Quale era l'obiettivo/scopo del testo?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 6: SINTESI STRATIFICATA
Fornisci 3 versioni di sintesi:
1. **Ultra-breve** (1 frase, max 20 parole)
2. **Breve** (1 paragrafo, 50-80 parole)
3. **Dettagliata** (strutturata per punti, completa)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## TEST 7: DOMANDE CHALLENGE
[PERSONALIZZA con 3-5 domande specifiche sul contenuto del tuo testo,
 puntando su dettagli che potrebbero essere dimenticati]

Esempio:
1. Nella sezione X, quale metodo era consigliato per Y?
2. Quanti esempi erano forniti per il concetto Z?
3. Quale termine tecnico era definito per primo?
```

---

## 📊 FASE 3: CALCOLO METRICHE

Dopo aver ricevuto le risposte, usa questo prompt per l'analisi:

```
Ora confronta le tue risposte con il testo originale che ti fornisco nuovamente:

[REINSERIRE IL TESTO ORIGINALE]

Analizza le tue performance e calcola queste metriche:

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## METRICHE DI COMPRENSIONE

### 1. RECALL ACCURACY (0-100%)
- Concetti principali identificati correttamente: X/Y = Z%
- Concetti omessi: [lista]
- Concetti inventati/errati: [lista]

### 2. RETENTION DETTAGLI (0-100%)
- Dati numerici corretti: X/Y = Z%
- Nomi/termini tecnici corretti: X/Y = Z%
- Esempi richiamati: X/Y = Z%

### 3. QUALITÀ MAPPA CONCETTUALE (1-10)
Valuta:
- Gerarchia corretta (0-3 punti)
- Relazioni accurate (0-3 punti)
- Completezza (0-2 punti)
- Chiarezza struttura (0-2 punti)
**TOTALE: X/10**

### 4. DISCRIMINAZIONE CONCETTUALE (0-100%)
- Distinzioni corrette tra concetti simili: X/Y = Z%
- Confusioni/sovrapposizioni: [lista]

### 5. COMPRENSIONE STRUTTURALE (1-10)
- Identificazione organizzazione: [Corretta/Parziale/Errata]
- Comprensione filo logico: [Corretta/Parziale/Errata]
- Identificazione scopo: [Corretta/Parziale/Errata]
**TOTALE: X/10**

### 6. ACCURATEZZA SINTESI (1-10)
Per ogni livello di sintesi valuta:
- Cattura essenza: Sì/No
- Omissioni critiche: Sì/No
- Informazioni errate: Sì/No
**TOTALE: X/10**

### 7. CHALLENGE QUESTIONS (0-100%)
- Risposte corrette: X/Y = Z%
- Dettagli specifici dimenticati: [lista]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 📈 SCORE GLOBALE

**Formula:**
Score = (Recall×25% + Retention×20% + MappaConcettuale×15% +
         Discriminazione×15% + Struttura×10% + Sintesi×10% + Challenge×5%)

**SCORE FINALE: XX/100**

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 🔍 ANALISI CRITICA

### Punti di Forza del Formato:
- [Cosa ha facilitato la comprensione]
- [Elementi che hanno aiutato il recall]
- [Strutture che hanno chiarito le relazioni]

### Punti Deboli del Formato:
- [Cosa ha causato perdite di informazione]
- [Elementi che hanno generato confusione]
- [Strutture che hanno ostacolato la comprensione]

### Informazioni Perse/Dimenticate:
- [Lista dettagliata di ciò che non è stato richiamato correttamente]

### Pattern di Errore:
- [Tipologie di errori ricorrenti]
- [Sezioni problematiche]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 🔄 WORKFLOW COMPARATIVO

### Per confrontare due formati:

1. **Sessione A**
   - Esegui Fase 1+2+3 con Testo in Formato A
   - Salva tutte le metriche
2. **Sessione B** (nuova conversazione o dopo reset)

   - Esegui Fase 1+2+3 con STESSO contenuto in Formato B
   - Salva tutte le metriche

3. **Confronto**

   ```
   Formato A vs Formato B:

   | Metrica | Formato A | Formato B | Delta | Vincitore |
   |---------|-----------|-----------|-------|-----------|
   | Recall | 85% | 92% | +7% | B |
   | Retention | 78% | 81% | +3% | B |
   | Mappa Concettuale | 7/10 | 8/10 | +1 | B |
   | Discriminazione | 88% | 85% | -3% | A |
   | Struttura | 8/10 | 9/10 | +1 | B |
   | Sintesi | 7/10 | 8/10 | +1 | B |
   | Challenge | 80% | 90% | +10% | B |
   | **SCORE GLOBALE** | **82/100** | **88/100** | **+6** | **B** |

   **VINCITORE: Formato B** (+6 punti)
   ```

4. **Conclusioni**
   - Quale formato ha permesso migliore comprensione?
   - Quali elementi specifici del formato hanno fatto la differenza?
   - Best practices identificate per formattazione LLM-friendly

---

## 💡 SUGGERIMENTI D'USO

### Variabili da Testare:

- ✅ Uso di markdown vs plain text
- ✅ Struttura gerarchica vs lineare
- ✅ Presenza di separatori visivi
- ✅ Lunghezza paragrafi
- ✅ Uso di liste vs prosa
- ✅ Presenza di sommari/indici
- ✅ Uso di enfasi (bold, italic)
- ✅ Densità informativa
- ✅ Uso di esempi e analogie
- ✅ Presenza di meta-informazioni (contesto, obiettivi)

### Note Importanti:

- Usa SEMPRE lo stesso contenuto informativo nei due formati
- Cambia SOLO la struttura/formattazione
- Esegui i test in sessioni separate per evitare bias
- Puoi personalizzare le Challenge Questions per il tuo contenuto specifico
- Più lungo è il testo, più evidenti saranno le differenze tra formati

---

## 🎯 OUTPUT FINALE CONSIGLIATO

Al termine dei test su entrambi i formati, crea un documento di sintesi:

```markdown
# Report Comparativo Formato A vs B

## Contenuto Testato

[Breve descrizione del testo usato]

## Risultati

[Tabella comparativa]

## Analisi

### Formato A

- Punti di forza: ...
- Punti deboli: ...

### Formato B

- Punti di forza: ...
- Punti deboli: ...

## Best Practices Identificate

1. ...
2. ...
3. ...

## Raccomandazioni

Per testi simili, utilizzare Formato [A/B] perché...
```

---

**Pronto all'uso!** Sostituisci i segnaposto con il tuo contenuto e inizia i test.
