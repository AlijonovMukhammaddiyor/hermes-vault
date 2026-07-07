# CS270 — AI Agents

> Design, evaluate, and ship an LLM agent at a senior bar: pick an architecture deliberately, build eval/observability for it, engineer its context/RAG, and apply it to real Rizo GO work.

**Credits:** 2  ·  **Domain:** ai-agents  ·  **Prereqs:** none

## Enduring understandings
- Start with the simplest thing that works; add agentic autonomy only when it demonstrably helps.
- The augmented LLM (retrieval + tools + memory) is the atomic building block.
- An agent you can't evaluate you can't improve — the eval harness is part of the design.

## Grading policy
hw 40% · quiz 30% · finals 30%

## Weekly schedule, outcomes & readings

### Sem 1 · Week 1 · Foundations — prompting, structured output, tool/function calling
- **apply** — Build an augmented LLM (prompt + structured output + tool call) and explain each part.
  - *proof:* Builds an augmented-LLM (prompt+structured output+tool call) with a grounded note + Rizo GO tie-in

### Sem 1 · Week 2 · Workflow Patterns — chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
- **evaluate** — Select among the 5 Anthropic workflow patterns for a task and justify the trade-off.
  - *proof:* Chooses among the 5 Anthropic workflow patterns for a task and defends why (teach-back)

### Sem 1 · Week 3 · Context Engineering — budgeting, tool-result compaction, memory
- **analyze** — Diagnose and fix a context problem (budget/compaction/memory) for an agent.
  - *proof:* RAG-grounded note on context budgeting/compaction/memory + Rizo GO application

### Sem 1 · Week 4 · RAG & Context — naive → advanced → agentic retrieval
- **create** — Build and evaluate a RAG pipeline, improving grounded answer quality with a measured metric.
  - *proof:* Builds/evaluates a RAG pipeline (naive→advanced) with a grounded note + measured result

### Sem 1 · Week 5 · Semester 1 Finals (applied + teach-back)
- **create** — Ship an applied agent improvement for Rizo GO and teach back the S1 concepts, closed-book.
  - *proof:* Applied agent deliverable for Rizo GO + conceptual teach-back across S1 units (closed-book)

## Assessment plan
- **a.fnd.build** (summative, project, ≥apply) — Builds an augmented-LLM (prompt+structured output+tool call) with a grounded note + Rizo GO tie-in
- **a.wf.choose** (summative, explain, ≥evaluate) — Chooses among the 5 Anthropic workflow patterns for a task and defends why (teach-back)
- **a.ctx.note** (summative, explain, ≥analyze) — RAG-grounded note on context budgeting/compaction/memory + Rizo GO application
- **a.rag.build** (summative, project, ≥create) — Builds/evaluates a RAG pipeline (naive→advanced) with a grounded note + measured result
- **a.s1.final** (summative, project, ≥create) — Applied agent deliverable for Rizo GO + conceptual teach-back across S1 units (closed-book)
