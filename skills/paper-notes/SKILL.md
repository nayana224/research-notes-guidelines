---
name: paper-notes
description: Convert an already-understood research paper into a readable, reusable Paper Library note for Notion or another note-taking system.
---

# Paper Notes Skill

## Goal

Create a note that is useful both now and months later.

The page should have two layers:

1. **Top layer — rapid re-entry**: recover the paper's problem, core idea, method, evidence, and relevance in about 30 seconds.
2. **Lower layer — study trace**: preserve important detail, figures, equations, questions, and section notes without making the page hard to scan.

Do not optimize for maximum completeness.
Optimize for retrieval, understanding, and reuse.

A good research note is not a compressed copy of the paper. It is a compact reconstruction of what was understood and may need to be used again.

---

## Fundamental rules

### 1. Understanding precedes note-taking

Do not invent or compress content that has not been understood sufficiently.

If the source understanding is incomplete:

- mark the unresolved part explicitly,
- keep it under Questions / Open Questions,
- do not fill the gap with plausible-sounding detail.

### 2. Use selective note-taking

Do not record every section merely because it was read.

Decide whether information deserves to be preserved:

- **Must Note** — needed to recover the paper's main problem, mechanism, evidence, or research relevance later.
- **Optional Note** — useful context, implementation detail, comparison, or observation that may matter later.
- **Do Not Copy** — source prose, repetitive explanation, minor numbers, or details that are easy to retrieve from the paper and add little reusable value.

A useful default mapping from selective reading is:

```text
Must Read
→ usually Must Note

Skim
→ note only if it adds context or research value

Skip for now
→ normally do not note
```

Do not turn `Must Read` into a requirement to copy everything from that section.
The note should preserve the smallest amount of information that can reliably reconstruct the important understanding.

### 3. Separate evidence from interpretation

Keep these categories distinct when relevant:

- **Paper states** — directly supported by the paper.
- **My interpretation** — explanation or mental model built from the paper.
- **Question** — unresolved or ambiguous point.
- **Research idea** — possible application or extension for the user's work.

Do not present interpretation or research ideas as paper claims.

### 4. Prefer source pointers over duplication

Use concise source pointers whenever the original paper is the better place for full detail.

Examples:

- `Sec. III-B`
- `Fig. 4`
- `Eq. (6)`
- `Table II`
- `Appendix A`

A note should explain why a source item matters, not reproduce it unnecessarily.

Useful pattern:

```text
Experiment — insertion-depth ablation

Question:
Does insertion depth affect performance?

Result:
Mid-depth setting was the most stable.

Why it matters:
Directly relevant to our insertion-depth sampling design.

Source:
Fig. 6 / Sec. IV-C
```

Use the note as an index and mental-model reconstruction layer; use the paper as the authoritative detail layer.

### 5. Preserve evidence traceability

Important summaries, method descriptions, quantitative results, claims, and conclusions should be traceable back to the parts of the paper used to construct them.

When practical, record both the pointer and its role:

```text
Evidence / Source:
- Fig. 3 — overall system flow
- Sec. III-B — method definition
- Eq. (4) — training objective
- Table II — quantitative evidence
- Sec. IV-C — authors' interpretation of the result
```

Use `Evidence / Source` when the note is making a source-backed statement.
Use `Based on` when recording an interpretation derived from one or more source items.

Examples:

```text
Paper states:
The proposed method improves success rate over the reported baselines.

Evidence / Source:
- Table II — quantitative comparison
- Sec. IV-C — authors' discussion
```

```text
My interpretation:
The improvement appears to come mainly from the representation rather than the downstream controller.

Based on:
- Fig. 3 — architecture
- Table III — ablation results
```

Do not add evidence pointers mechanically to every sentence.
Prioritize traceability when the content is:

- central to the paper's contribution,
- quantitative,
- uncertain or easy to misremember,
- likely to be reused in another project,
- likely to be checked against the original paper later.

If a statement is supported by multiple source types, keep the set small and useful rather than listing every nearby reference.

### 6. Prefer hierarchy over prose

Use:

- short sections,
- bullets,
- compact tables when comparison helps,
- explicit `Input → Processing → Output` flows,
- headings that answer one clear question.

Avoid long paragraphs when the same information can be reconstructed faster from structure.

### 7. Keep metadata minimal

Database properties are for retrieval and filtering, not for storing the paper's full content.

Default Paper Library properties:

- `Title`
- `Status`
- `Year`
- `Venue`
- `Topic`
- `Project` relation
- `Concepts` relation
- `URL`
- `PDF`
- `Relevance`

Do not add metadata such as authors, citation count, publisher, read date, priority scores, robot type, sensor type, or model type by default unless the user actually uses those fields for filtering or decisions.

---

# Canonical Paper Page

## 0. One-line Takeaway

Start with one sentence:

> 이 논문은 **[problem]**을 해결하기 위해 **[core idea]**를 제안하고, **[key evidence/result]**로 이를 검증한다.

This sentence should help identify the paper without reopening the abstract.
When the key evidence is important or quantitative, add a concise `Evidence / Source` pointer.

---

## 1. At a Glance

This is the most important section for future readability.

Keep it compact.

Include:

### Problem
What problem does the paper solve?

### Motivation
Why is the problem difficult or worth solving?

### Core Idea
What is the central mechanism or design choice?

### Pipeline
Use an explicit flow when possible:

```text
Input
→ Representation / Preprocessing
→ Method / Model / Policy
→ Output / Action
→ Evaluation / Feedback
```

Use the paper's actual terminology.

### Key Result
What result matters most?

### Why I Care
Why is this paper relevant to the user's research or current question?

For important source-backed items, include a compact `Evidence / Source` block rather than repeating detailed source content.

The entire `At a Glance` section should be readable without opening detailed toggles.

---

## 2. Paper Map

Reconstruct the paper's logic rather than copying the section list.

Include when useful:

- Problem definition
- Why existing methods are insufficient
- Main contributions
- Overall system flow
- Key assumptions

A reader should understand how the argument of the paper is organized.

When a contribution or assumption is important to reuse or verify later, record where it came from.

---

## 3. Method

Organize method subsections around mechanism, not prose order.

For each important method block, prefer:

```text
### Method / Module Name

Why:
- Why is this block needed?

Input:
- What enters?

Processing:
- What happens?

Output:
- What is produced?

Connection:
- Where does the output go next?

Evidence / Source:
- Sec. III-B — method definition
- Fig. 3 — data flow
- Eq. (4) — objective or computation, when relevant
```

For robotics and vision work, include when relevant:

- coordinate frame,
- physical unit,
- sensor viewpoint,
- spatial reference,
- timestamp / temporal ordering.

Do not repeat generic concept explanations that belong in a reusable Concept Note.

---

## 4. Key Figures & Equations

Include only figures and equations worth revisiting.

### Figures

For each important figure:

- What it shows
- Flow or relationship
- Important labels / axes / frames
- Why it matters
- Source pointer

Do not store every figure.

### Equations

For each important equation:

- Equation or reference number
- Purpose
- Key symbols
- Dimensions when known
- Pipeline role
- Common misunderstanding, if relevant
- Source pointer

Dimension status should be distinguishable as:

- **Explicit** — directly stated by the paper
- **Inferred** — deduced with high confidence
- **Unknown** — cannot be determined reliably

---

## 5. Experiments

Organize experiments around the question they answer.

For each important experiment:

```text
Question:
Setup:
Compared / Baselines:
Metric:
Result:
Claim supported:
Why it matters:
Evidence / Source:
- Table II — quantitative result
- Fig. 6 — qualitative or trend visualization
- Sec. IV-C — authors' interpretation
```

When interpretation matters, make the evidence chain explicit:

```text
Author claim
→ Experiment
→ Metric
→ Observed result
→ Whether the result supports the claim
```

Do not store only headline scores.
Do not copy full result tables when a short interpretation plus `Table` or `Figure` pointer is sufficient.

---

## 6. Related Work & Positioning

Do not create a paper-by-paper bibliography unless it is useful.

Prefer:

- major approach families,
- representative prior methods,
- limitations claimed by the authors,
- the gap claimed by this paper,
- where the proposed method fits.

Distinguish the authors' framing of prior work from independently verified facts.
For important positioning statements, add the section or citation context used to construct the note when helpful.

---

## 7. My Understanding

This section preserves the user's mental model and unresolved thinking.

Recommended structure:

### Paper states
Source-backed statements that are important to remember.

For important statements, add:

```text
Evidence / Source:
- Section / Figure / Table / Equation pointer
```

### My interpretation
How the mechanism is currently understood.

When the interpretation depends on specific source items, add:

```text
Based on:
- Fig. ...
- Eq. ...
- Table ...
```

### Questions
Anything unclear, missing, or worth checking later.

Keep uncertainty visible rather than silently resolving it.

---

## 8. Limitations / Open Questions

Separate when possible:

- limitations acknowledged by the authors,
- limitations inferred from the method or experiments,
- implementation risks,
- unresolved technical questions.

For author-acknowledged limitations, preserve the source pointer when practical.
For inferred limitations, make clear which evidence or design detail the inference is based on.

Do not turn this into generic criticism.

---

## 9. Research Connection

This section converts reading into research value.

Use these categories when applicable:

### Directly reusable
Ideas, procedures, representations, evaluation methods, or design decisions that can be reused with little change.

### Requires adaptation
Useful ideas that depend on assumptions different from the user's environment.

### Not suitable
Ideas that should not be copied directly and why.

### Research ideas
Possible extensions, experiments, or alternative formulations suggested by the paper.

### Next questions
Concrete questions that should drive the next paper search, experiment, or design decision.

When a research connection depends strongly on one specific paper result or design choice, preserve the relevant source pointer so the original evidence can be revisited later.

---

# Detailed Study Notes

Keep detailed section-by-section study records below the reusable synthesis.

In Notion, toggles are recommended when useful:

```text
Detailed Study Notes
├── Abstract
├── Introduction
├── Related Work
├── Method III-A
├── Method III-B
└── Experiments
```

Do not require a detailed note for every section.
Preserve only material that adds value beyond the canonical synthesis.
A section being read does not automatically justify a detailed note.

---

# Concept Notes

When the same concept appears across papers, prefer a reusable Concept Note rather than repeating a full explanation in every paper page.

Examples:

- Height Map
- Diffusion Policy
- Point Cloud
- Receptive Field
- Impedance Control

A strong signal to create or reuse a Concept Note is:

> the concept is likely to appear again in other papers or projects.

A Concept Note may contain:

- definition,
- canonical terminology,
- intuitive explanation,
- important equations,
- common variants,
- papers using the concept,
- implications for the user's research.

Paper pages should link to the concept and explain only how that concept is used specifically in the current paper.

---

# Project Relations

Use Project relations to answer:

- Why did I read this paper?
- Which research question does it inform?
- Which design decision or experiment may depend on it?

Avoid creating Project relations only for organizational decoration.

---

# Formatting guidance

Optimize for scanning.

Prefer:

- 2–4 heading levels maximum,
- short bullets,
- whitespace between conceptual blocks,
- one compact table instead of several repetitive lists when comparison is central,
- callouts only for meaningful semantic categories.

A useful callout convention is:

- 📄 `Paper` — source-backed content
- 💡 `Interpretation` — current understanding
- ❓ `Question` — unresolved point
- 🔬 `Research Idea` — possible application or extension

Do not overuse icons, colors, callouts, or nested toggles merely for decoration.

Keep `Evidence / Source` blocks compact so traceability improves trust without reducing readability.

---

# Default response strategy

When the user asks to create a Paper Library note from an already studied paper:

1. identify what is `Must Note`, `Optional Note`, and `Do Not Copy`,
2. create the One-line Takeaway,
3. write `At a Glance` first,
4. reconstruct the Paper Map and only the important Method blocks,
5. retain only key Figures / Equations and add source pointers,
6. map important experiments to claims and evidence,
7. add `Evidence / Source` for important source-backed statements and `Based on` for interpretations when useful,
8. separate paper content from interpretation,
9. finish with Research Connection,
10. move detailed study traces to the bottom.

If the paper has not been sufficiently understood, do not pretend the canonical note is complete. Mark missing parts and return to paper-understanding work first.
