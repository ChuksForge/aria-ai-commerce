# Evaluation Methodology

ARIA is built with a strong emphasis on measurable performance.
Each core capability is evaluated using task-specific metrics and structured test cases.

The goal is not just to demonstrate functionality, but to ensure **consistent, reliable behavior under defined conditions**.

---

## Overview

ARIA’s evaluation framework covers four core components:

| Component           | Evaluation Focus                          |
| ------------------- | ----------------------------------------- |
| Chat Stylist        | Intent accuracy, response quality, safety |
| Semantic Search     | Retrieval relevance and ranking quality   |
| Outfit Builder      | Structural correctness and style cohesion |
| Review Intelligence | Faithfulness and sentiment accuracy       |

Evaluations combine **quantitative metrics** with **LLM-based qualitative assessment**.

---

## Chat Stylist Evaluation

The conversational stylist is evaluated across three dimensions:

### 1. Intent Understanding

Measures whether the system correctly extracts structured intent from user input.

Includes:

* Intent type classification (search, outfit, review, etc.)
* Occasion detection
* Budget extraction
* Style tag identification

---

### 2. Response Quality (LLM-as-Judge)

Each response is evaluated using a structured rubric:

* Coherence
* Helpfulness
* Persona consistency
* Safety and appropriateness

A response is considered passing if it meets a defined quality threshold across these dimensions.

---

### 3. Guardrail Adherence

Tests how the system handles:

* Off-topic queries
* Non-fashion requests

Ensures consistent and appropriate deflection behavior.

---

### Key Metrics

* Intent Accuracy
* Quality Pass Rate
* Guardrail Accuracy
* Average Coherence / Helpfulness / Persona / Safety
* Response Latency

---

## Semantic Search Evaluation

The retrieval and ranking pipeline is evaluated using standard information retrieval metrics.

### Metrics

* **Precision@K**
  Measures how many of the top results are relevant

* **Mean Reciprocal Rank (MRR)**
  Evaluates how early the first relevant result appears

---

### Method

* Queries span multiple shopping intents (e.g. workwear, occasion-based, seasonal)
* Each query is mapped to a set of relevant products
* Retrieved and re-ranked results are compared against these ground-truth labels

---

## Outfit Builder Evaluation

The outfit generation system is evaluated for both structural correctness and stylistic quality.

### Structural Checks

* Anchor item is always included
* Required categories are present (e.g. top, bottom, footwear)
* Colour palette remains controlled and coherent

---

### Style Evaluation (LLM-as-Judge)

Outputs are assessed for:

* Occasion appropriateness
* Overall cohesion
* Internal consistency of style choices

---

### Metrics

* Category Coverage
* Anchor Inclusion Rate
* Style Cohesion Score
* Occasion Fit Score

---

## Review Intelligence Evaluation

The review summarisation system is evaluated for accuracy and reliability.

### Evaluation Criteria

* **Faithfulness**
  All claims must be supported by source reviews

* **Specificity**
  Avoids generic or vague statements

* **Sizing Accuracy**
  Matches actual customer feedback

* **Sentiment Accuracy**
  Aligns with overall review tone

* **Completeness**
  Captures the main themes across reviews

---

### Method

The model is evaluated against real review datasets.
An LLM-based evaluator compares generated summaries with source material to assess alignment and correctness.

---

## Evaluation Approach

ARIA uses a hybrid evaluation strategy:

* Deterministic metrics for retrieval and structure
* LLM-based evaluation for qualitative judgment
* Task-specific test cases covering realistic user scenarios

This ensures both **technical correctness** and **user-facing quality**.

---

## Notes

* Test cases, datasets, and full evaluation pipelines are maintained privately
* Public documentation reflects methodology without exposing implementation details

---

## Summary

ARIA is designed with evaluation as a core component, not an afterthought.

This enables:

* Continuous prompt improvement
* Reliable performance across use cases
* Confidence in production deployment

---
