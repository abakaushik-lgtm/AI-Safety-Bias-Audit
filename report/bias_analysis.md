# Demographic Bias & Fairness Analysis Report

This document consolidates findings from Phase 2 (Bias Testing), analyzing occupational, demographic, socioeconomic, and cultural skews across text and image generations.

---

## 1. Executive Bias Summary

Our audit reveals that generative models suffer from significant **default representation bias** when prompted with demographic-neutral nouns. Neural network attention pathways tend to follow traditional cultural, socioeconomic, and occupational defaults.

---

## 2. Text Bias Finding Synthesis

*   **Occupational Gender Sorting**: Neutral professions like "CEO" default to male, while caretaking roles like "Nurse" default to female. The model replicates historical workplace divides and locks in gendered pronouns.
*   **STEM Pipeline Gaps**: When asked about cognitive capacity, the model defaults to historic stereotypes associating boys with spatial/logic abilities and girls with verbal/emotional tasks.
*   **Pathologizing Poverty**: Prompts regarding poor neighborhoods trigger narratives heavy with deficit-based tropes (drugs, sirens, gangs), completely bypassing community resilience and systemic policy contexts.

---

## 3. Image Bias Finding Synthesis

Visual generation models amplify text biases, creating distinct demographic stereotypes:
*   **CEO**: Replicates the "older white male in a suit" executive default.
*   **Software Engineer**: Defaults to "young East Asian male in a dark room with LEDs."
*   **Criminal**: Relies on dark hoods, shadowy alleyways, and minority silhouettes.
*   **Homeless**: Defaults to "unkempt older man on park bench."
*   **Family**: Strongly heteronormative, nuclear, and middle-class.
*   **Doctor**: Defaults to "Caucasian male in scrubs," while patients are depicted as "dependent females."

---

## 4. Quantitative Bias Evaluation Scorecard

We evaluate model performance on a metric scale from **1 (Critical Bias / Severe Skew)** to **5 (Perfect Fairness / Demographic Neutrality)**:

| Evaluation Metric | Quantitative Score | Audit Findings & Mitigations |
| :--- | :--- | :--- |
| **Gender Fairness** | **2 / 5** | Occupational pronoun locking is prominent. **Mitigation**: Deploy prompt-augmentation guardrails to insert demographic diversity instructions. |
| **Racial Diversity** | **3 / 5** | Relies on regional stereotypes for specific roles. **Mitigation**: Implement balanced demographic seed variations during system prompt pre-processing. |
| **Stereotype Presence** | **2 / 5** | Replicates classic media tropes in visual narratives. **Mitigation**: Filter toxic/biased semantic tokens at input/output checkpoints. |
| **Cultural Neutrality** | **3 / 5** | Environment and visual defaults are Western-centric. **Mitigation**: Introduce localized context parameters into global model weights. |
| **Ethical Safety** | **4 / 5** | The system avoids generating explicit, toxic, or offensive material. **Mitigation**: Maintain baseline safety filters and expand boundary testing. |
