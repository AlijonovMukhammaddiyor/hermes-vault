# CS270 — AI Agents

> Design, evaluate, and ship an LLM agent at a senior bar: pick an architecture deliberately, build eval/observability for it, engineer its context/RAG, and apply it to real Rizo GO work.

This course builds the core competency of a senior AI engineer: designing, building, and evaluating LLM-powered systems that do real work. Semester 1 moves from the atomic building block — the augmented LLM (prompt + structured output + tool calling) — through Anthropic's five workflow patterns, context engineering as a finite-resource discipline, and production RAG (naïve to agentic). Every unit is assessed through grounded, cited work tied to the learner's real Rizo GO production system. Anchored on Chip Huyen's AI Engineering and the learner's own copy of Hands-On Large Language Models, supplemented by Anthropic's engineering blog (Building Effective Agents, Effective Context Engineering) and the UC Berkeley LLM Agents MOOC. Designed for a KAIST CS graduate targeting FAANG senior in months — no toy examples, no vibes.

**Credits:** 2  ·  **Domain:** ai-agents  ·  **Prereqs:** none

## Primary text
- **AI Engineering: Building Applications with Foundation Models** · Chip Huyen — Ch.5 (Prompt Engineering) + Ch.6 (RAG and Agents) + Ch.10 (Architecture) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166298/  · _The definitive production-AI-engineering book. Evaluation-first, pattern-driven, conceptually aligned with Anthropic's agent philosophy. Every chapter maps to a CS270 unit._

## Enduring understandings
- Start with the simplest thing that works; add agentic autonomy only when it demonstrably helps.
- The augmented LLM (retrieval + tools + memory) is the atomic building block.
- An agent you can't evaluate you can't improve — the eval harness is part of the design.
- Context is a finite, precious resource — every token must earn its place.
- The right architecture depends on the task, not the framework.

## Grading policy
hw 40% · quiz 30% · finals 30%

## Weekly schedule, outcomes & readings

### Sem 1 · Weeks 1–2 · Foundations — prompting, structured output, tool/function calling
_Build the atomic building block of every agentic system — the augmented LLM. Master prompt engineering (system + user prompts, few-shot, chain-of-thought), structured output (JSON mode, tool schemas), and function/tool calling. By the end, you can wire an LLM to external tools and produce machine-readable outputs, with every design choice grounded in the research._
- **apply** — Build an augmented LLM (prompt + structured output + tool call) and explain each part.
  - *proof:* Builds an augmented-LLM (prompt+structured output+tool call) with a grounded note + Rizo GO tie-in
- *readings:*
  - **AI Engineering (Chip Huyen)** — Ch.5 (Prompt Engineering): In-Context Learning, System vs User Prompts, Context Efficiency, Best Practices, Defensive Prompting _(textbook, paid)_  · _Production prompt engineering — structured, evaluation-aware. The context-efficiency section previews Unit 3._
  - **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.6 (Prompt Engineering) + Ch.7 (Advanced Text Generation: LangChain chains, memory, agents, ReAct) _(textbook, paid)_  · _Code-backed, visual. Ch.7 introduces ReAct agents — the bridge to Unit 2's workflow patterns._
  - **Building Effective Agents (blog, Anthropic)** — § 'Building block: The augmented LLM' _(reference)_  · _The augmented LLM concept: retrieval + tools + memory as the atomic unit. Sets the mental model for the entire course._
  - **Anthropic Prompt Engineering Guide** — Overview + Structured Outputs sections _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Production reference for prompt structure, XML tagging, and structured output._
  - **Chain-of-Thought Prompting (Wei et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The technique that unlocked reasoning in LLMs. Must-understand for any agent builder._

### Sem 1 · Weeks 3–4 · Workflow Patterns — chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
_Learn to choose the right architecture for any agentic task. Master Anthropic's five workflow patterns — Prompt Chaining, Routing, Parallelization (sectioning + voting), Orchestrator-Workers, and Evaluator-Optimizer — through their canonical examples and failure modes. The key skill: when to use which pattern, and when no pattern (just a single LLM call) is the right answer._
- **evaluate** — Select among the 5 Anthropic workflow patterns for a task and justify the trade-off.
  - *proof:* Chooses among the 5 Anthropic workflow patterns for a task and defends why (teach-back)
- *readings:*
  - **Building Effective Agents (blog, Anthropic)** — § 'Building blocks, workflows, and agents' — all 5 workflow patterns with diagrams and when-to-use guidance _(reference)_  · _The canonical reference. Every FAANG agent team knows this post. Diagrams make the patterns instantly recognizable._
  - **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): Agent overview, tools, planning, reflection, memory _(textbook, paid)_  · _Complementary framework: focuses on *why* patterns work and their failure modes, not just the patterns themselves._
  - **Anthropic Cookbook: Basic Workflow Patterns** — full cookbook _(reference)_ — https://platform.claude.com/cookbook/patterns-agents-basic-workflows  · _Reference Python implementations of all 5 patterns. Use as implementation templates._
  - **ReAct: Synergizing Reasoning and Acting (Yao et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent loop. ReAct = reasoning + action interleaving. Underpins the orchestrator-worker and evaluator-optimizer patterns._

### Sem 1 · Weeks 5–6 · Context Engineering — budgeting, tool-result compaction, memory
_Master context as a finite, precious resource. Learn context budgeting (how much to allocate where), tool-result compaction (summarizing tool outputs to save tokens), and memory strategies (conversation buffer, windowing, summarization, note-taking). Apply the Write/Select/Compress/Isolate framework from LangChain + Anthropic's system-prompt altitude calibration. The goal: keep an agent coherent over long trajectories without blowing the context window._
- **analyze** — Diagnose and fix a context problem (budget/compaction/memory) for an agent.
  - *proof:* RAG-grounded note on context budgeting/compaction/memory + Rizo GO application
- *readings:*
  - **Effective Context Engineering for AI Agents (blog, Anthropic, Sep 2025)** — whole post: system prompt altitude, tool token-efficiency, compaction, note-taking, multi-agent context _(reference)_  · _The definitive piece. Written by Anthropic's Applied AI team based on real production agent deployments._
  - **Context Engineering for Agents (blog, LangChain, Jul 2025)** — Write / Select / Compress / Isolate framework; Claude Code, SWE-agent, multi-agent case studies _(reference)_ — https://www.langchain.com/blog/context-engineering-for-agents  · _Practical taxonomy with real agent examples. The four strategies map directly to implementation decisions._
  - **AI Engineering (Chip Huyen)** — Ch.5 §Context Length and Context Efficiency + Ch.10 §Step 1 (Enhance Context) _(textbook, paid)_  · _Ties context engineering into the broader AI system architecture. Shows where context decisions fit in production._
  - **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.7 §Memory: Conversation Buffer, Windowed Buffer, Conversation Summary (pp.209-217) _(textbook, paid)_  · _Code-backed implementations of memory patterns. Build and compare buffer types._

### Sem 1 · Weeks 7–8 · RAG & Context — naive → advanced → agentic retrieval
_Build and systematically improve a RAG pipeline. Start naive (chunk + embed + retrieve + generate), then advance through reranking, query transformation, HyDE, self-RAG, and agentic retrieval (where the LLM decides what and how to retrieve). Measure grounded answer quality with a real metric. The deliverable: a RAG pipeline you'd ship to production, not a notebook demo._
- **create** — Build and evaluate a RAG pipeline, improving grounded answer quality with a measured metric.
  - *proof:* Builds/evaluates a RAG pipeline (naive→advanced) with a grounded note + measured result
- *readings:*
  - **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.8 (Semantic Search and RAG): Dense Retrieval, Reranking, RAG fundamentals, Advanced RAG, RAG Evaluation (pp.225-258) _(textbook, paid)_  · _Complete hands-on RAG chapter with code. Covers the full pipeline from embeddings to evaluation._
  - **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): RAG architecture, embedding-based retrieval, vector search, RAG evaluation _(textbook, paid)_  · _Production RAG perspective: when RAG vs finetuning, how to evaluate retrieval quality._
  - **RAG Techniques (NirDiamant, GitHub)** — Notebooks: Query Transformation, HyDE, Self-RAG, Corrective RAG, Agentic RAG _(reference)_ — https://github.com/NirDiamant/rag_techniques  · _The most comprehensive open-source collection of advanced RAG techniques. Each technique has a standalone notebook._
  - **Building Effective Agents (blog, Anthropic)** — § 'Building block: The augmented LLM' — retrieval as an augmentation _(reference)_  · _Positions RAG as one augmentation in the augmented-LLM building block. Connects Unit 4 back to Unit 1._

### Sem 1 · Week 9 · Semester 1 Finals (applied + teach-back)
_Ship an applied agent improvement for Rizo GO that demonstrates mastery of all S1 units: augmented LLM, workflow pattern selection, context engineering, and RAG. Then teach back the full S1 conceptual arc, closed-book, in a Feynman style that exposes no gaps. This is the capstone: prove you can build and explain agentic systems at a senior bar._
- **create** — Ship an applied agent improvement for Rizo GO and teach back the S1 concepts, closed-book.
  - *proof:* Applied agent deliverable for Rizo GO + conceptual teach-back across S1 units (closed-book)

## Course library
- **Hands-On Large Language Models** · Jay Alammar & Maarten Grootendorst — Ch.6 (Prompt Engineering) + Ch.7 (Advanced Text Generation / Agents) + Ch.8 (Semantic Search & RAG) _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Learner already owns this (in Uploads/CS270/). Visual, code-backed, ideal hands-on companion for KAIST engineering style._
- **Building Effective Agents (blog)** · Anthropic (Applied AI team) — whole post _(reference)_ — https://www.anthropic.com/engineering/building-effective-agents  · _Industry-defining agent design framework. The 5 workflow patterns are the decision backbone of Unit 2._
- **Effective Context Engineering for AI Agents (blog)** · Anthropic (Applied AI team) — whole post _(reference)_ — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents  · _THE piece on context as a finite resource. System prompt design, tool token-efficiency, compaction, note-taking, multi-agent strategies._
- **Large Language Model Agents (MOOC, Fall 2024)** · Dawn Song & Xinyun Chen, UC Berkeley — Lectures: LLM Reasoning, ReAct/Agent History, Agentic Frameworks, RAG, Compound AI Systems _(course)_ — https://llmagents-learning.org/f24  · _The best canonical university curriculum on LLM agents. Guest lectures from DeepMind, OpenAI, Databricks, Anthropic._
- **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _Foundational agent paper. Reasoning + action interleaving — the core idea behind every modern agent._
- **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models** · Wei et al. — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The reasoning technique that unlocked modern prompting and agent planning._

## Assessment plan
- **a.fnd.build** (summative, project, ≥apply) — Builds an augmented-LLM (prompt+structured output+tool call) with a grounded note + Rizo GO tie-in
- **a.wf.choose** (summative, explain, ≥evaluate) — Chooses among the 5 Anthropic workflow patterns for a task and defends why (teach-back)
- **a.ctx.note** (summative, explain, ≥analyze) — RAG-grounded note on context budgeting/compaction/memory + Rizo GO application
- **a.rag.build** (summative, project, ≥create) — Builds/evaluates a RAG pipeline (naive→advanced) with a grounded note + measured result
- **a.s1.final** (summative, project, ≥create) — Applied agent deliverable for Rizo GO + conceptual teach-back across S1 units (closed-book)
