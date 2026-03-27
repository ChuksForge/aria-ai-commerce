# Prompting Approach

## Overview

ARIA uses task-specific prompt designs tailored to different problem types.

Each prompt is built to produce **structured, reliable outputs** that can be validated and used programmatically.

---

## Design Principles

### Structured Outputs

All model responses follow predefined schemas.

This ensures:

* predictable system behaviour
* reliable downstream processing
* consistent UI rendering

---

### Task-Specific Design

Each capability uses a dedicated prompt optimized for its objective:

* Conversational understanding
* Ranking and decision-making
* Multi-item composition
* Information summarisation

---

### Controlled Creativity

Model behaviour is tuned based on task requirements:

* Higher variability for conversational responses
* Lower variability for ranking and summarisation
* Balanced creativity for outfit generation

---

### Iterative Improvement

Prompts are continuously refined based on evaluation results.

Changes are tracked and tested to ensure measurable improvements in output quality.

---

## Example Output Structure (Simplified)

```
{
  "reply": "...",
  "intent": {
    "type": "...",
    "context": "..."
  }
}
```

Structured outputs allow the system to separate:

* user-facing responses
* machine-readable intent

---

## Reasoning-Driven Tasks

For tasks that require deeper judgment (e.g. ranking or composition), the model is guided to:

* evaluate multiple factors
* apply consistent decision criteria
* produce explainable results

This improves reliability on complex queries.

---

## Reliability Safeguards

* Output validation before response delivery
* Explicit constraints in prompts
* Fallback handling for invalid responses

---

## Summary

ARIA’s prompting approach is designed to balance:

* flexibility of language models
* structure required for production systems

This enables consistent performance across a range of real-world scenarios.
