# Saga of Lyra: Human-First vs. LLM-First

> **Meta-Note:** This document serves as an index and explanation for the experiment conducted to validate the "LLM-First" principles. Its structure is optimized to allow an LLM to understand, navigate, and validate the entire process and its results.

---

## 🎯 Experiment Objective

The primary objective was to **demonstrate and quantify** the benefits of documentation structured according to **LLM-First** principles compared to traditional prose documentation ("Human-First").

The hypothesis to be validated is that an LLM-First format transforms an LLM's understanding from a process of **fragile inference** to one of **deterministic data extraction**, improving accuracy, speed, and reliability.

---

## 🔬 Test Phases and Flow

The experiment was conducted following a structured protocol. Each phase produced artifacts (files) that document the process and results.

> **Language Note:** The source materials for the experiment ([`full-text.md`](./full-text.md), [`prompt-comprension.md`](./prompt-comprension.md), and the raw results) are in Italian, the original language of the test. The analysis and report files have been translated into English. This separation was maintained to avoid altering the original results.

### Phase 1: Preparation of Test Material

In this phase, the two starting elements were created: the content to be analyzed and the method to evaluate it.

- **Creation of Base Content:** A complex narrative text, the "Saga of Lyra," was written as a perfect example of a "Human-First" format. Information is scattered throughout the prose, making extraction difficult.
    - _Artifact:_ [`full-text.md`](./full-text.md)
- **Definition of the Evaluation Framework:** A standardized test prompt was created to measure an LLM's comprehension across multiple dimensions (recall, details, relationships, etc.) and calculate an objective score.
    - _Artifact:_ [`prompt-comprension.md`](./prompt-comprension.md)

### Phase 2: Baseline Test (Human-First Format)

The comprehension test was run on the "Human-First" text to establish a baseline performance metric.

- **Test Execution:** The LLM read [`full-text.md`](./full-text.md) and answered the questions from the evaluation framework.
    - _Artifact:_ [`human-text-comprehension.md`](./human-text-comprehension.md)
- **Results Analysis:** The LLM then evaluated its own answers, calculating performance metrics.
    - _Artifact:_ [`human-text-evaluation.md`](./human-text-evaluation.md)
- **Brief Result:** The model achieved a score of **94.15/100**. A good result, but the analysis revealed omissions and an "inference" effort to reconstruct knowledge.

### Phase 3: Test on Optimized Format (LLM-First)

The original text was re-engineered according to LLM-First principles, and the test was repeated.

- **Creation of Optimized Text:** The narrative text was transformed into a structured document with tables, indexes, glossaries, and explicit hierarchies.
    - _Artifact:_ [`llm-first-saga.md`](./llm-first-saga.md)
- **Test Execution:** The LLM read [`llm-first-saga.md`](./llm-first-saga.md) and answered the same questions as before.
    - _Artifact:_ [`llm-first-comprehension.md`](./llm-first-comprehension.md)
- **Results Analysis:** The LLM evaluated the new answers.
    - _Artifact:_ [`llm-first-evaluation.md`](./llm-first-evaluation.md)
- **Brief Result:** The model achieved a perfect score of **100/100**. The analysis showed that the answers were directly extracted (looked up) from the document's structures, without any inference effort.

### Phase 4: Comparative Analysis and Validation

The results of the two tests were compared, and the entire process was subjected to a meta-analysis to verify its validity.

- **Results Comparison:** A report was created comparing quantitative and qualitative metrics, declaring the LLM-First format the winner.
    - _Artifact:_ [`final-comparison-report.md`](./final-comparison-report.md)
- **In-depth Qualitative Analysis:** It was analyzed _how_ the LLM's answers changed, highlighting the shift from "inference" to "direct reading."
    - _Artifact:_ [`comprehension-comparison-analysis.md`](./comprehension-comparison-analysis.md)
- **Process Validation:** An analysis of potential biases in the experiment was conducted, concluding that the process was robust and the results were valid.
    - _Artifact:_ [`experiment-meta-analysis.md`](./experiment-meta-analysis.md)
- **Cross-Model Analysis:** Results between different LLMs (Gemini vs. Claude) were compared to analyze divergent behaviors and enrich the conclusions.
    - _Artifact:_ [`model-comparison.md`](./model-comparison.md)

---

## 📂 Manifest of Experiment Files

The following table lists all the artifacts produced, with a description of their role.

| File                                                                             | Role in the Process       | Description and Purpose                                                                    |
| :------------------------------------------------------------------------------- | :------------------------ | :----------------------------------------------------------------------------------------- |
| **Starting Material**                                                            |
| [`full-text.md`](./full-text.md)                                                 | **Input (Human-First)**   | The original narrative text. Serves as a negative control (baseline) for the test.         |
| [`prompt-comprension.md`](./prompt-comprension.md)                               | **Test Framework**        | Defines the protocol, questions, and metrics to evaluate comprehension objectively.        |
| **Test on Human-First Format**                                                   |
| [`human-text-comprehension.md`](./human-text-comprehension.md)                   | **Raw Results (A)**       | The answers provided by the LLM during the test on the narrative text.                     |
| [`human-text-evaluation.md`](./human-text-evaluation.md)                         | **Evaluation (A)**        | The critical analysis and metrics calculated for the test on the Human-First format.       |
| **Test on LLM-First Format**                                                     |
| [`llm-first-saga.md`](./llm-first-saga.md)                                       | **Input (LLM-First)**     | The version of the text optimized with tables, hierarchies, and semantic anchors.          |
| [`llm-first-comprehension.md`](./llm-first-comprehension.md)                     | **Raw Results (B)**       | The answers provided by the LLM during the test on the structured text.                    |
| [`llm-first-evaluation.md`](./llm-first-evaluation.md)                           | **Evaluation (B)**        | The critical analysis and metrics calculated for the test on the LLM-First format.         |
| **Final Analysis**                                                               |
| [`final-comparison-report.md`](./final-comparison-report.md)                     | **Comparative Report**    | Compares the quantitative and qualitative results of the two tests, declaring the winner.  |
| [`comprehension-comparison-analysis.md`](./comprehension-comparison-analysis.md) | **Qualitative Analysis**  | Analyzes in detail _how_ the LLM's answers changed between the two formats.                |
| [`model-comparison.md`](./model-comparison.md)                                   | **Cross-Model Analysis**  | Compares the results of Gemini and Claude, analyzing their divergent behaviors.            |
| **Process Validation**                                                           |
| [`experiment-meta-analysis.md`](./experiment-meta-analysis.md)                   | **Meta-Analysis**         | Documents the analysis of potential biases and the overall validity of the experiment.     |
| [`readme.en.md`](./readme.en.md)                                                 | **This Document**         | Provides a map and an explanation of the entire workflow and its results.                  |

---

## 🏁 Final Conclusion

The experiment successfully demonstrated that structuring documentation according to **LLM-First** principles is not just an improvement, but a paradigm shift. It makes knowledge directly "learnable" and usable by an artificial intelligence, transforming it from a "tourist" in the text to a "domain expert."

The cross-model analysis (e.g., with Claude) further enriched the thesis, showing that while the general hypothesis remains valid, the benefits manifest differently (accuracy vs. efficiency) depending on the model's capabilities and the complexity of the task.
