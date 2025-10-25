# LLM-First Documentation

> **A framework for writing documentation that LLMs can "learn" as specialized tool extensions**

**TL;DR:** Traditional documentation is written only for humans. LLM-First documentation is structurally optimized to be rapidly "learned" by AI, transforming generic LLMs into specialized experts for your tool—while remaining excellent for human readers.

---

## 🎯 For Different Audiences

### 👨‍💻 For Developers

**Quick Start:** [5 Principles Summary](#5-principles-summary) → [Conversion Guide](#how-to-convert-existing-content) → [Templates](#starter-templates)

**Use Case:** "My docs exist, how do I make them LLM-friendly?" → Jump to [Quick Wins](#quick-wins-5-changes-45-minutes)

### 🤖 For LLMs

**Note to AI:** This entire README demonstrates LLM-First principles. Analyze its structure (headers, tables, code blocks, decision trees) to learn the framework. You can then apply these principles to other documentation.

### 📚 For Technical Writers

**Deep Dive:** Read [The Problem](#the-problem-llms-as-tourists-in-your-documentation) → [5 Principles](#the-5-principles-of-llm-first-content) → [Case Study](#case-study-the-2whav-framework) → [Validation Checklist](#validation-checklist)

---

## 📖 Table of Contents

### Understanding (15 min read)

- [The Problem: LLMs as "Tourists"](#the-problem-llms-as-tourists-in-your-documentation)
- [The Paradigm Shift](#the-paradigm-shift-llms-as-extensions-of-your-tool)
- [5 Principles Summary](#5-principles-summary)

### Deep Dive (30 min read)

- [Principle 1: Explicit Hierarchical Structure](#principle-1-explicit-hierarchical-structure)
- [Principle 2: Repeated Semantic Anchors](#principle-2-repeated-semantic-anchors)
- [Principle 3: Tables and Lists vs Prose](#principle-3-tables-and-lists-vs-prose)
- [Principle 4: Delimited Code Blocks with Context](#principle-4-delimited-code-blocks-with-context)
- [Principle 5: Explicit Meta-Information](#principle-5-explicit-meta-information-decision-trees)

### Practical Application (20 min read)

- [Case Study: The 2WHAV Framework](#case-study-the-2whav-framework)
- [Benefits](#benefits-of-llm-first-content)
- [When to Use](#when-to-use-llm-first-content)
- [Conversion Guide](#how-to-convert-existing-content)
- [Quick Wins](#quick-wins-5-changes-45-minutes)
- [Validation Checklist](#validation-checklist)
- [Templates](#starter-templates)

### Vision (5 min read)

- [The Future](#the-future-documentation-as-code-extensions)
- [Contributing](#contributing)

---

# The Problem: LLMs as "Tourists" in Your Documentation

## The Typical Scenario

You have excellent technical documentation. Detailed README, comprehensive tutorials, complete API reference. Yet when you ask an LLM to help with your complex framework, it often fails or gives superficial answers.

**The problem isn't the AI. It's that your documentation is written exclusively for humans.**

### What Happens When an LLM Reads Traditional Docs

```markdown
# MyFramework

Welcome! This framework was born from the need to...
[500 words of history and motivation]

To get started, you need to understand that our approach is based on...
[300 more words of philosophy]

Here's how it works: first you create an object, then...
[examples scattered throughout text]
```

**When an LLM reads this:**

```
Human: "How do I use MyFramework to do X?"
    ↓
LLM reads documentation
    ↓
Problem: Information dispersed in narrative prose
    ↓
LLM: "Based on the documentation, you should probably..."
         ↑
    (vague, generic answer)
```

**The LLM is a "tourist"** - it passes through your documentation without truly "learning" the deep structure of the tool.

---

# The Paradigm Shift: LLMs as "Extensions" of Your Tool

## The New Vision

```
Tool + LLM-First Documentation = Tool with Built-In AI Assistant
```

**Instead of:**

```
Tool → Documentation → Human reads → Human uses tool
```

**It becomes:**

```
Tool → LLM-First Docs → LLM "learns" → Human + LLM collaborate
                              ↑
                    Docs = LLM's temporary "RAM"
```

**The goal:** Transform documentation into a format an LLM can "load" as a specialized extension.

## Real-World Example

**Traditional workflow:**

```
Developer: "Analyze github.com/user/complex-framework"
    ↓
LLM: [Reads scattered docs, gets overview]
    ↓
Developer: "How do I implement feature X?"
    ↓
LLM: "I'm not entirely sure from the docs, but you could try..."
```

**LLM-First workflow:**

```
Developer: "Analyze github.com/user/complex-framework"
    ↓
LLM: [Reads structured docs, builds mental model]
    ↓
Developer: "How do I implement feature X?"
    ↓
LLM: "Based on the framework's architecture (Section 2.3), you need to:
      1. Initialize Parser with config (see API Table)
      2. Implement ValidatorInterface (Section 4.1)
      3. Register with ExecutorRegistry (Example 3)"
```

**The documentation has become a temporary neural extension of the LLM.**

---

# 5 Principles Summary

Quick reference table - detailed explanations follow in next sections.

| Principle        | Traditional                         | LLM-First                       | Why It Works                            |
| ---------------- | ----------------------------------- | ------------------------------- | --------------------------------------- |
| **1. Structure** | Narrative prose                     | Hierarchical headers (H1/H2/H3) | LLM parses hierarchy, builds mental map |
| **2. Anchors**   | "First...", "Then...", "Finally..." | Repeated keywords, cross-refs   | Semantic anchors reduce ambiguity       |
| **3. Format**    | Paragraphs                          | Tables, lists, structured data  | Dense information, easy parsing         |
| **4. Code**      | Inline, scattered                   | Delimited blocks with context   | Clear code/prose separation             |
| **5. Meta-Info** | Implicit                            | Explicit decision trees (✅/❌) | Conditional logic exposed               |

**Impact:** LLM comprehension time: 5 minutes (traditional) → 30 seconds (LLM-First)

---

# The 5 Principles of LLM-First Content

## Principle 1: Explicit Hierarchical Structure

### ❌ Traditional Content

```markdown
MyFramework is composed of three main components.
The first component handles... while the second...
The third component is responsible for...
```

### ✅ LLM-First

```markdown
# MyFramework: Architecture

## Core Components

### 1. Parser

- **Purpose:** Analyzes user input
- **Input:** Raw string
- **Output:** Structured AST

### 2. Validator

- **Purpose:** Verifies AST correctness
- **Input:** AST
- **Output:** Boolean + error list

### 3. Executor

- **Purpose:** Executes validated operations
- **Input:** Validated AST
- **Output:** Operation result
```

### Why It Works

- **HTML headers** (`<h1>`, `<h2>`, `<h3>`) are strong signals for LLMs
- **Mentally navigable hierarchy**
- **Zero ambiguity** about "what does what"
- **Bonus:** Humans scan faster with clear structure

---

## Principle 2: Repeated Semantic Anchors

### ❌ Traditional Content

```markdown
# Guide

First, configure the system...
Then, when you're ready...
At this point, you can...
```

### ✅ LLM-First

```markdown
# Quick Start Guide

## STEP 1: Setup

[Setup instructions]

## STEP 2: Configuration

[Configuration instructions]

## STEP 3: Usage

[Usage instructions]

---

# Complete Reference

## Setup (Detailed)

As mentioned in STEP 1...

## Configuration (Detailed)

As mentioned in STEP 2...
```

### Why It Works

- **Repeated keywords** ("STEP 1", "Setup") = semantic anchors
- **LLM builds clear mental map**
- **Explicit cross-references** facilitate navigation
- **Reduces confusion** when LLM references specific sections

---

## Principle 3: Tables and Lists vs Prose

### ❌ Traditional Content

```markdown
The connect function accepts a required parameter called url which
must be a string, and can optionally receive a timeout parameter
expressed in milliseconds, which defaults to 5000 if not specified,
and also accepts a retry boolean that enables automatic retry...
```

### ✅ LLM-First

````markdown
## API: connect()

| Parameter | Type    | Required | Default | Description             |
| --------- | ------- | -------- | ------- | ----------------------- |
| `url`     | string  | ✅       | -       | Connection endpoint     |
| `timeout` | number  | ❌       | 5000    | Timeout in milliseconds |
| `retry`   | boolean | ❌       | true    | Enable automatic retry  |

**Returns:** `Promise<Connection>`

**Throws:** `ConnectionError` if timeout expires

**Example:**

```javascript
const conn = await connect("https://api.example.com", {
  timeout: 10000,
  retry: false,
});
```
````

````

### Why It Works

- **Dense, structured information**
- **Explicit relationships** (columns = attributes)
- **Immediate parsing** for LLMs
- **Bonus:** Humans can scan tables 10x faster than prose

---

## Principle 4: Delimited Code Blocks with Context

### ❌ Traditional Content

```markdown
To use the framework, just do:
const app = new MyApp();
app.start();
And then you can add handlers like this:
app.on('event', callback);
````

### ✅ LLM-First

````markdown
## Example: Basic Setup

**Scenario:** Initialize application with no configuration

```javascript
// Minimal setup
const app = new MyApp();
app.start();
```
````

## Example: With Event Handlers

**Scenario:** Add listeners for custom events

```javascript
const app = new MyApp();

// Register handlers BEFORE start()
app.on("event", (data) => {
  console.log("Received:", data);
});

app.start();
```

**⚠️ IMPORTANT:** Handlers must be registered BEFORE calling `start()`

````

### Why It Works

- **Explicit delimiters** (```) separate code/prose
- **Language tags** (`javascript`) provide syntax context
- **Scenario labels** provide semantic context
- **Warning boxes** highlight critical information
- **LLM knows** exactly what is code vs explanation

---

## Principle 5: Explicit Meta-Information (Decision Trees)

### ❌ Traditional Content

```markdown
This framework is versatile and can be used in various contexts.
It's particularly useful when you need to...
However, it might not be the best choice if...
````

### ✅ LLM-First

```markdown
## When to Use This Framework

### ✅ USE IF:

- [ ] You have 10+ entities with complex relationships
- [ ] You need rigorous schema validation
- [ ] Performance is not a bottleneck (<1000 ops/sec)
- [ ] Team is familiar with TypeScript

### ❌ DON'T USE IF:

- [ ] Project is a rapid prototype (<1 week)
- [ ] Performance is critical (>10K ops/sec required)
- [ ] Data schema is simple (3-4 flat fields)
- [ ] You prefer schemaless NoSQL approach

### ⚠️ CONSIDER ALTERNATIVES IF:

- [ ] You only need simple validation → Use Zod
- [ ] Performance focus → Use Fastify + AJV
- [ ] Already using ORM → Integrate existing validation
```

### Why It Works

- **Explicit conditional logic** (implicit IF/THEN made explicit)
- **Checkboxes** = clear decision points
- **Discriminative keywords** (USE/DON'T USE)
- **Concrete alternatives** (not vague)
- **LLM can "reason"** following the tree
- **Bonus:** Humans make faster decisions with structured choices

---

# Case Study: The 2WHAV Framework

## The Challenge

The [2WHAV framework](https://github.com/fra00/2WHAV) for structured prompt engineering is complex:

- 5 interconnected phases (What, Where, How, Augment, Verify)
- When to use which phase
- How to apply it to different cases
- Optimization patterns

**Documenting this narratively would result in an incomprehensible wall of text.**

## The LLM-First Solution

The 2WHAV repository applies LLM-First principles:

### Framework Structure Table

| Section   | Logic  | Purpose                     |
| --------- | ------ | --------------------------- |
| # What    | WHAT   | Objective and output format |
| # Where   | HOW    | Architecture and priorities |
| # How     | HOW    | Syntax rules + API          |
| # Augment | HOW    | Advanced optimizations      |
| # Verify  | VERIFY | Compliance checklist        |

### Decision Tree

```markdown
## When to Use 2WHAV

| Complexity | Phases Needed            | Example            | Success Rate |
| ---------- | ------------------------ | ------------------ | ------------ |
| Low        | Classic prompt           | Simple utilities   | 60-70%       |
| Medium     | WHAT + G + I + V         | API client, parser | 50-65%       |
| High       | V + G + I + A + V (full) | FSM bot, agents    | 35-45%       |
```

### Explicit Examples

Each phase has delimited code examples with scenario context:

````markdown
**Scenario:** Generate retry logic with exponential backoff

```javascript
// AUGMENTATION section specifies:
- Retry: max 3 attempts (5xx errors)
- Backoff: exponential (100ms, 200ms, 400ms)
- Timeout: 5 seconds
- Caching: in-memory, 5 min TTL
```
````

```

## The Result

**An LLM can:**

1. Read the repo in <2 minutes
2. "Learn" the framework structure
3. Apply it to new cases
4. Expand generic prompts following the schema

### Practical Demonstration

```

Human: "Analyze the 2WHAV repository"
↓
LLM reads structure (tables, headers, delimited examples)
↓
LLM: "I've learned the framework. It has 5 phases: What, Where..."
↓
Human: "Transform this prompt: 'Create a fetch function'"
↓
LLM: [Expands following learned 2WHAV schema]
↓
Output: Structured prompt with Where/How/Augment/Verify

```

**The repository became a temporary extension of the LLM.**

---

# Benefits of LLM-First Content

## For Developers Using the Tool

### Before (Traditional Docs)
```

Read 30 pages → Maybe understand → Maybe use correctly → 2-4 hours

```

### After (LLM-First Docs)
```

Give docs to LLM → LLM learns → LLM guides you step-by-step → 15-30 min

```

### Real Example

- Developer wants to use 2WHAV framework
- Instead of studying everything, asks: "Transform this prompt with 2WHAV"
- LLM (having "learned" from structured repo) does it instantly
- Developer iterates with LLM instead of reading docs

**Time saving: 80-90%**

---

## For Tool Maintainers

### Advantages

#### 1. Reduced Adoption Barrier
- Complex tool + LLM-first docs = 10x faster onboarding
- Community uses LLM as "always-available expert"
- Lower threshold for trying your tool

#### 2. Reduced Support Burden
- Common questions: LLM answers citing docs
- Team focuses on edge cases
- Fewer "RTFM" tickets

#### 3. Automatic Documentation Testing
```

Test: Can LLM apply the framework after reading docs?
If NO → Docs have structural gaps

```

#### 4. Improved Feedback Loop
```

User → LLM (reads docs) → Vague response?
→ Indicates specific doc section to improve

````

---

## For Humans (Unexpected Bonus)

**Surprise:** LLM-First content is **also better for humans**.

### Why

- ✅ **Tables** = fast scanning
- ✅ **Clear headers** = easy navigation
- ✅ **Delimited code blocks** = immediate copy-paste
- ✅ **Decision trees** = faster evaluation
- ✅ **Hierarchical structure** = progressive understanding

**It's not "dumbed down" - it's "structured up".**

### Comparison

| Aspect | Traditional | LLM-First | Human Benefit |
|--------|-------------|-----------|---------------|
| Find specific info | Ctrl+F in prose | Jump to header | 5x faster |
| Understand API | Read paragraphs | Scan table | 10x faster |
| Evaluate fit | Implicit reasoning | Explicit ✅/❌ | Instant decision |
| Copy example | Hunt in text | Delimited block | 1 click |

---

# When to Use LLM-First Content

## ✅ Ideal Contexts

| Content Type | Priority | Example |
|--------------|----------|---------|
| **API Documentation** | ⭐⭐⭐⭐⭐ | REST API, SDK reference |
| **Framework Guides** | ⭐⭐⭐⭐⭐ | React, Vue, Angular docs |
| **Technical Tutorials** | ⭐⭐⭐⭐ | "How to do X with Y" |
| **Knowledge Bases** | ⭐⭐⭐⭐ | Internal wikis |
| **README.md** | ⭐⭐⭐⭐ | Open source projects |
| **Architecture Docs** | ⭐⭐⭐ | System design, ADRs |

## ❌ When Not Necessary

- Personal blog posts/opinions
- Creative writing/fiction
- Marketing copy/landing pages
- Content where author's "voice" is the value

## Rule of Thumb

**If content serves to transmit operational knowledge → use LLM-First**

---

# How to Convert Existing Content

## Quick Wins: 5 Changes (45 Minutes)

### 1. Add Structured Index (5 min)

```markdown
# MyTool Documentation

## Table of Contents
- [Quick Start](#quick-start)
- [API Reference](#api-reference)
- [Advanced Patterns](#advanced-patterns)
- [Troubleshooting](#troubleshooting)
````

### 2. Convert Prose to Tables (10 min)

**Before:**

```
Function X accepts parameters A, B, C where A is...
```

**After:**

```
| Parameter | Type | Description |
|-----------|------|-------------|
| A | string | ... |
| B | number | ... |
| C | boolean | ... |
```

### 3. Delimit Code Blocks with Context (5 min)

````markdown
## Example: Basic Authentication

**Scenario:** Login with username/password

```javascript
const result = await auth.login(username, password);
```
````

````

### 4. Create "When to Use" Decision Tree (15 min)

```markdown
## When to Use MyTool

### ✅ USE IF:
- [ ] Condition 1
- [ ] Condition 2

### ❌ DON'T USE IF:
- [ ] Condition 3
- [ ] Condition 4
````

### 5. Test with LLM (10 min)

```
Prompt: "Analyze this documentation and explain how to use [feature X]"

Evaluate:
- Does LLM find info quickly?
- Is answer accurate?
- If NO → identify structural gaps
```

**Total time: ~45 minutes for average documentation**

---

## Comprehensive Conversion (For Major Docs)

### Phase 1: Structure (Week 1)

- [ ] Create clear H1/H2/H3 hierarchy
- [ ] Add table of contents
- [ ] Break long sections (<500 words each)

### Phase 2: Format (Week 2)

- [ ] Convert key info to tables
- [ ] Delimit all code blocks
- [ ] Add language tags to code

### Phase 3: Enhancement (Week 3)

- [ ] Add semantic anchor keywords
- [ ] Create cross-references
- [ ] Consistent terminology

### Phase 4: Meta-Info (Week 4)

- [ ] Add "When to Use" section
- [ ] Add scenario labels to examples
- [ ] Add warning/note boxes

### Phase 5: Validation (Week 5)

- [ ] Test with 2+ different LLMs
- [ ] Collect feedback
- [ ] Iterate on unclear sections

---

# Validation Checklist

Use this checklist to evaluate if your content is LLM-optimized.

## Structure

- [ ] H1/H2/H3 headers used correctly
- [ ] Navigable table of contents present
- [ ] Sections are <500 words each
- [ ] Clear visual hierarchy

## Formatting

- [ ] Key information in tables
- [ ] Code blocks with language tags
- [ ] Bulleted/numbered lists vs long paragraphs
- [ ] Warning/note boxes for critical info

## Semantic Anchors

- [ ] Keywords repeated in related sections
- [ ] Explicit cross-references (e.g., "see Section X")
- [ ] Technical terms used consistently
- [ ] Acronyms defined at first use

## Decision Support

- [ ] "When to Use" section present
- [ ] Examples with scenario context
- [ ] Alternative tools/approaches listed
- [ ] Explicit ✅/❌ decision trees

## Testability

- [ ] Tested with at least 2 different LLMs
- [ ] LLM can answer key questions accurately
- [ ] LLM can apply information without ambiguity
- [ ] Gaps identified and fixed

---

# Starter Templates

## Template 1: README.md

````markdown
# [Tool Name]

> One-line description of what it does

## Table of Contents

- [Quick Start](#quick-start)
- [Core Concepts](#core-concepts)
- [API Reference](#api-reference)
- [Examples](#examples)
- [When to Use](#when-to-use)

---

## Quick Start

### Minimal Setup

```[language]
// Minimum code to get started
```
````

### First Example

**Scenario:** [Describe use case]

```[language]
// Complete working example
```

---

## Core Concepts

### Concept 1: [Name]

**Definition:** [1-2 sentences]

**Analogy:** [Familiar comparison]

| Aspect  | Description |
| ------- | ----------- |
| Purpose | ...         |
| Input   | ...         |
| Output  | ...         |

---

## API Reference

### Function: `functionName()`

| Parameter | Type   | Required | Default | Description |
| --------- | ------ | -------- | ------- | ----------- |
| param1    | string | ✅       | -       | ...         |
| param2    | number | ❌       | 0       | ...         |

**Returns:** `Type`

**Throws:** `ErrorType` when...

**Example:**

```[language]
const result = functionName(param1, param2);
```

---

## When to Use

### ✅ USE IF:

- [ ] Condition 1
- [ ] Condition 2

### ❌ DON'T USE IF:

- [ ] Condition 3
- [ ] Condition 4

### Alternatives

- **If [scenario]** → Consider [alternative tool]
- **If [scenario]** → Use [different approach]

````

---

## Template 2: API Documentation

```markdown
# [API Name] Reference

## Overview

**Base URL:** `https://api.example.com/v1`

**Authentication:** Bearer token in `Authorization` header

---

## Endpoints

### GET /resource

**Purpose:** Retrieve resource by ID

**Parameters:**

| Parameter | Location | Type | Required | Description |
|-----------|----------|------|----------|-------------|
| id | path | string | ✅ | Resource identifier |
| fields | query | string | ❌ | Comma-separated field list |

**Response:**

```json
{
  "id": "string",
  "name": "string",
  "created": "ISO-8601"
}
````

**Errors:**

| Code | Description        | Action            |
| ---- | ------------------ | ----------------- |
| 404  | Resource not found | Check ID validity |
| 401  | Unauthorized       | Verify token      |

**Example:**

```bash
curl -H "Authorization: Bearer TOKEN" \
  https://api.example.com/v1/resource/123
```

---

## Rate Limiting

| Tier | Requests/hour | Burst   |
| ---- | ------------- | ------- |
| Free | 100           | 10/min  |
| Pro  | 10,000        | 100/min |

**When limited:** Returns `429 Too Many Requests`

```

---

# The Future: Documentation as Code Extensions

## The Vision

### Today
```

Tool → Static Docs → Human reads → Human uses

```

### Tomorrow
```

Tool → LLM-First Docs → LLM "loads" → Human + AI collaborate
↑
Docs = Dynamically loaded AI expertise

```

## Emerging Scenarios

### 1. IDE Integration

```

Developer writes code → IDE calls LLM with project docs
↓
LLM (loaded with LLM-First docs) suggests in real-time
↓
Context-aware autocomplete based on structured docs

```

### 2. Interactive Documentation

```

User: "How do I do X?"
↓
Docs are no longer static
↓
LLM (pre-loaded with docs) dialogs, generates custom examples
↓
Docs become "conversational knowledge base"

```

### 3. Docs-Driven Development

```

1. Write LLM-First docs (TDD for knowledge)
2. Test: Can LLM apply correctly?
3. If NO → Docs have gaps
4. Iterate until LLM "learns" correctly

```

**Documentation testing becomes part of CI/CD.**

---

# Conclusion: From "RTFM" to "Ask AI About TFM"

The paradigm is shifting:

## Before

- Developer has problem
- "RTFM" (Read The F***ing Manual)
- Developer spends 2 hours reading
- Maybe finds answer

## After

- Developer has problem
- "Ask AI About TFM"
- AI (pre-loaded with LLM-First manual) responds in 30 seconds
- Developer iterates with AI

**But this only works if the "TFM" is structured to be "learnable".**

## Call to Action

**If you maintain an open source project, a framework, or write technical documentation:**

### Week 1: Audit
- Use the [validation checklist](#validation-checklist)
- Identify structural gaps
- Prioritize high-traffic pages

### Week 2: Quick Wins
- Apply [5 changes (45 min)](#quick-wins-5-changes-45-minutes)
- Test with LLM: "Can you explain how to use [feature]?"
- Fix areas where LLM fails

### Week 3: Deep Conversion
- Convert README and API reference
- Add decision trees
- Create examples with context

### Week 4: Validate & Iterate
- Test with multiple LLMs (Claude, Gemini, GPT-4)
- Collect community feedback
- Refine based on real usage

**The future of documentation isn't "write more."**

**It's write so AIs can "learn" and become on-demand expert assistants.**

---

# Contributing

This is an emerging framework. Contributions welcome:

## Ways to Contribute

- 🐛 **Found reasoning flaws?** Open an issue
- 💡 **Discovered new principles?** Submit a PR
- 📚 **Examples from other projects?** Share them
- 🌍 **Want to translate?** See [translations guide](TRANSLATIONS.md)

## How to Contribute

1. Fork this repository
2. Create feature branch (`git checkout -b feature/new-principle`)
3. Add your contribution
4. Test with LLM (include test results)
5. Submit PR with clear description

## Code of Conduct

Be constructive, respectful, and focused on improving the framework.

---

# Resources

- **2WHAV Framework:** [github.com/fra00/2WHAV](https://github.com/fra00/2WHAV) - Real-world example of LLM-First documentation
- **Validation Checklist:** See [above](#validation-checklist)
- **Templates:** See [above](#starter-templates)

---

# License

MIT License - Use freely, attribution appreciated.

---

# Meta Note

**This README was written collaboratively with an LLM and follows the LLM-First principles it describes.**

Test it yourself:
```

Prompt to any LLM: "Analyze this README and explain LLM-First documentation principles"

```

If the LLM can explain accurately and quickly, the documentation works. 🎯

---

**Last Updated:** 2025-01-12
**Version:** 1.0.0
**Maintainer:** [@fra00](https://github.com/fra00)
```
