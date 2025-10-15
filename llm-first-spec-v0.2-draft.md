---
title: "LLM-First Documentation Specification"
version: "0.2-draft"
status: "Draft for Review"
author: "fra00 + GPT-5 collaborative draft"
last_updated: "2025-10-15"
license: "MIT"
---

# 🧠 LLM-First Documentation Specification  
**Version 0.2 — Draft for Review**

---

## 1. Scopo e Ambito

Questa specifica definisce linee guida, principi e criteri di conformità per la creazione di documentazione tecnica progettata per essere **leggibile, interpretabile e utilizzabile da modelli linguistici (LLM)** oltre che da lettori umani.

Lo scopo è rendere la conoscenza **azione-compatibile**, cioè utilizzabile direttamente come base di ragionamento, risposta o decisione da parte di sistemi basati su linguaggio naturale.

**Ambiti applicativi:**
- README, manuali e guide tecniche
- Documentazione API e SDK
- Knowledge base per RAG o agent framework
- Specifiche interne per modelli o robot autonomi

---

## 2. Definizioni

| Termine | Descrizione |
|----------|-------------|
| **LLM-First** | Documento scritto principalmente per la comprensione e l’uso da parte di modelli linguistici. |
| **LLM-Aware** | Documento scritto per umani ma strutturato per essere compatibile con parsing e ragionamento di un LLM. |
| **Human-First** | Documento scritto senza considerazioni specifiche per l’elaborazione automatica da parte di LLM. |
| **Anchor Term** | Termine o frase chiave ripetuta coerentemente per rinforzare la semantica di un concetto. |
| **Semantic Block** | Sezione autonoma e autosufficiente che rappresenta un’unità logica di conoscenza (es. funzione, policy, componente). |
| **Validation Set** | Insieme di prompt o domande utilizzate per verificare che un LLM comprenda correttamente il contenuto del documento. |

---

## 3. Principi Fondamentali

1. **Struttura Gerarchica Esplicita**  
   - Utilizzare intestazioni (H1–H3) descrittive e coerenti.  
   - Ogni sezione deve avere uno scopo definito (es. “Scopo”, “Esempio”, “Vincoli”).  

2. **Ridondanza Semantica Controllata**  
   - Ripetere termini chiave in sezioni correlate per migliorare la comprensione del modello.  
   - Evitare sinonimi non necessari.  

3. **Pattern Regolari e Prevedibili**  
   - Usare **tabelle** per parametri, elenchi puntati per comportamenti e sezioni esplicite per condizioni.  
   - Mantenere coerenza tra documenti dello stesso dominio.  

4. **Esplicitazione dei Vincoli d’Uso**  
   - Includere sezioni “Use / Don’t Use”, “When / Not When”, “Input / Output”.  

5. **Isolamento dei Contesti**  
   - Ogni blocco di codice o esempio deve includere il contesto e lo scopo.  
   - Evitare riferimenti impliciti o cross-reference ambigui.  

6. **Auto-descrittività**  
   - Ogni documento deve poter essere letto e compreso senza contesto esterno non dichiarato.  

---

## 4. Livelli di Conformità

| Livello | Nome | Descrizione | Tipico utilizzo |
|----------|------|-------------|----------------|
| **L1** | *Readable* | Strutturato, con titoli coerenti e sezioni brevi. | README e manuali umani. |
| **L2** | *LLM-Aware* | Strutturato + semantica coerente + sezioni esplicite per scopo e vincoli. | Documentazione tecnica o API. |
| **L3** | *LLM-First* | Progettato primariamente per essere letto da un LLM come base di ragionamento o decisione. | Corpus RAG, robotica cognitiva, agent framework. |

---

## 5. Linee Guida di Formattazione

- Usare **Markdown standard** o **HTML leggibile**.  
- Evitare sinonimi per concetti chiave.  
- Esplicitare sempre *scopo*, *condizioni*, *effetti*.  
- Ogni **concetto = una sezione**.  
- Blocchi di codice devono includere:
  - linguaggio  
  - contesto (“Esempio di utilizzo in ambiente X”)  
  - descrizione post-codice.  

### Esempio:

```markdown
### Esempio: Uso della Funzione di Normalizzazione

**Scopo:** normalizzare un vettore di dati.

**Codice:**
```python
normalize(values)
````

**Effetto:** restituisce un array di float in [0,1].

```

---

## 6. Validazione

La conformità di un documento può essere verificata tramite **LLM Validation Test**.

### 6.1 Procedura

1. Fornire il documento come contesto a un LLM.  
2. Somministrare un **Validation Set** di almeno 10 domande.  
3. Valutare:
   - **Coverage:** % di risposte corrette ≥ 80%  
   - **Consistency:** variazione ≤ 10% su tre run indipendenti.

### 6.2 Output

Se il documento raggiunge entrambi i valori soglia, è conforme al livello dichiarato.

---

## 7. Esempio di Conversione

| Stile | Estratto di esempio | Caratteristiche |
|--------|----------------------|----------------|
| **Human-First** | “Questo modulo serve a migliorare l’esperienza utente normalizzando i dati di input.” | Descrittivo, ma poco strutturato. |
| **LLM-Aware** | “Funzione `normalize(values)` — Scopo: normalizzare un vettore di input. Restituisce valori in [0,1].” | Strutturato, con termini chiave e scopo espliciti. |
| **LLM-First** | “### Funzione: normalize(values) — Scopo: normalizzare vettore di input. Input: lista di numeri. Output: lista di float in [0,1]. Use when: serve confronto normalizzato. Don’t use when: input non numerici.” | Perfettamente interpretabile da un LLM, leggibile da un umano. |

---

## 8. Versioning e Compatibilità

| Versione | Stato | Descrizione |
|-----------|--------|-------------|
| v0.1 | Manifesto | Definizione concettuale del paradigma LLM-First. |
| **v0.2** | Specifica (draft) | Formalizzazione con principi, livelli e validazione. |
| v0.3 (futura) | Formato validabile | Definizione di schema JSON/Markdown validator per testing automatico. |

---

## 9. Appendice

### 9.1 Glossario

- **DX (Documentation Experience):** qualità dell’esperienza di scrittura e fruizione di documenti per LLM e umani.  
- **Semantic Traceability:** capacità di un LLM di mantenere coerenza concettuale nel tempo usando la documentazione.

### 9.2 Riferimenti

- Repo originale: [fra00/llm-first-documentation](https://github.com/fra00/llm-first-documentation)  
- Esperimento di apprendimento contestuale eseguito con modello GPT-5, Ottobre 2025.

---

## 10. Stato del documento

**Bozza aperta alla revisione.**  
Suggerimenti su struttura, lessico, formalità e metodo di validazione sono incoraggiati.  
Obiettivo della v0.3: formalizzazione di strumenti di verifica automatica e esempi multi-dominio (robotica, API, RAG, dev-ops).
```

---
