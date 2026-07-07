# CS270 — AI Engineering

> Design, build, evaluate, and ship a large-scale AI agent at a senior bar: choose the right architecture, engineer its context as a finite resource, build evals and observability, and defend every decision with grounded reasoning.

This course builds the core competency of a senior AI engineer: designing, building, and evaluating LLM-powered agentic systems that do real work. Semester 1 moves from the atomic building block — the augmented LLM (prompt + structured output + tool calling via MCP) — through Anthropic's five workflow patterns, context engineering as a finite-resource discipline, production RAG (naïve to agentic), and the eval harness that makes improvement possible. Anchored on Chip Huyen's AI Engineering, Anthropic's engineering blog, the UC Berkeley Advanced LLM Agents MOOC, and the ReAct/CoT papers. Designed for a KAIST CS graduate who wants to build at the Manus / Hermes / Fin.AI level — no toy examples, no framework hype.

**Credits:** 2  ·  **Domain:** ai-agents  ·  **Prereqs:** none

## Primary text
- **AI Engineering: Building Applications with Foundation Models** · Chip Huyen — Ch.5 (Prompt Engineering) + Ch.6 (RAG and Agents) + Ch.10 (Architecture) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166298/  · _The definitive production-AI-engineering book. Evaluation-first, pattern-driven, written by someone who ships. Every chapter maps to a CS270 unit._

## What the best in this field can do
Ship an agentic system at production scale with a deliberate architecture, measured eval results, documented context-engineering decisions, and the ability to defend every choice to a principal engineer. Know what ISN'T an agent — agent-washing awareness is part of the bar.

**How the best practice:**
- Evals-first: write the evaluation before the implementation. The single biggest signal of real LLM experience.
- Pattern-first: choose the architecture pattern before picking a framework. Frameworks are implementation details; patterns are transferable architecture.
- Context-budgeting: treat every token as a cost center. Long context windows don't eliminate context rot.
- Teach-back: if you can't explain it simply, you don't understand it.
- Read the source: go to the Anthropic blog, the papers, the Berkeley lectures — not the Medium tutorial.
- Security-conscious: prompt injection is the #1 vulnerability (73% of production deployments). Design tools with least privilege.
- KISS: start simple; add agentic autonomy only when it demonstrably helps. Gartner: 40% of agentic AI projects are canceled by 2027 — complexity kills.

**Signature work that earns a seat with the best:** A portfolio agent that demonstrates deliberate architecture, measured performance, eval-driven improvement, and the ability to explain the full stack. The kind of project you'd present in a FAANG staff interview. Bonus: open-source it and build a community around it.

## How to keep evolving
Autonomous multi-agent orchestration becoming standard infrastructure (2026). Agent protocol wars — MCP vs A2A vs ACP — with convergence under Linux Foundation (Aug 2025). Coding agents as the most mature category (SWE-bench 72%+). Agent-computer interfaces (ACI). Trajectory-level evaluation. Safety/alignment for agentic systems. 'Agent washing' is real: only ~130 of thousands of vendors are genuine agents (Gartner).

- **Anthropic Engineering Blog** _(reference)_ — https://www.anthropic.com/engineering  · _The best applied AI engineering writing. Follow for agent patterns, context engineering, tool design, evals._
- **UC Berkeley RDI (agent courses)** _(reference)_ — https://rdi.berkeley.edu/  · _Spring + Fall agent courses with new guest lectures each semester. Keep watching the recordings._
- **Chip Huyen's blog & newsletter** _(reference)_ — https://huyenchip.com/blog/  · _Production ML/AI engineering. She's consistently ahead of the curve on what matters._
- **Simon Willison's blog** _(reference)_ — https://simonwillison.net/  · _Practical, opinionated LLM engineering. Great for staying grounded in what actually works._
- **Latent Space podcast / newsletter** _(reference)_ — https://www.latent.space/  · _Interviews with the people building the agent infrastructure. Good for staying on the frontier._
- **Sebastian Raschka's Ahead of AI newsletter** _(reference)_ — https://magazine.sebastianraschka.com/  · _LLM implementation and research with a level of technical precision that rewards re-reading._
- **ICML / NeurIPS / ICLR (agent tracks)** _(reference)_ — https://icml.cc/  · _Top ML conferences with growing agent/AI engineering tracks. ICML 2026: Seoul, July 6–11._

**Deliberate-practice regimen:** Build → evaluate → break → fix → teach back. Every unit: read the researched source → implement → measure with evals → find the failure modes → teach the concept. Interleave units (mix workflow problems with context-engineering problems) to build transfer. Wrong answers get a targeted micro-lesson on the exact misconception, then re-test.

## How this course is taught
*Concept-first, then build. Every lesson starts with the mental model (grounded in the researched source), then moves to faded scaffolding. Socratic when you're stuck — nudge → pattern → approach → pseudocode → reference. Never gives the answer before you've tried.*

**Misconceptions the professor preempts:**
- Thinking frameworks matter more than patterns. Frameworks are implementation details; patterns are transferable architecture. Learn the pattern, then pick the framework that fits.
- More agentic = better. The best agent is often no agent — a single well-crafted LLM call with retrieval beats a convoluted multi-agent system for many tasks. Gartner: 40% of agentic AI projects canceled by 2027 — complexity is the #1 killer.
- Context windows are huge so context management doesn't matter. Context rot is real — longer context degrades precision. Every token must earn its place.
- Evals are an afterthought. You cannot improve what you can't measure. Build the eval harness FIRST. Teams without evals 'fly blind' — debugging becomes reactive guesswork.
- MCP is the only standard that matters. The protocol landscape is evolving fast — A2A (agent-to-agent) and ACP are real competitors. Understand MCP deeply, but watch the protocol wars.
- If it calls an API, it's an agent. Agent washing is endemic — only ~130 of thousands of 'agentic AI' vendors are genuine (Gartner). Know the difference between an API wrapper and an agent.

## Enduring understandings
- Start with the simplest thing that works; add agentic autonomy only when it demonstrably helps.
- The augmented LLM (retrieval + tools + memory) is the atomic building block of every agentic system.
- Context is a finite, precious resource — every token must earn its place.
- An agent you can't evaluate you can't improve — the eval harness IS the design.
- The right architecture depends on the task, not the framework — know the patterns, not the library.

## Grading policy
hw 40% · quiz 30% · finals 30%

## Week-by-week plan

| Week | Focus | Readings | Deliverable |
|---|---|---|---|
| 1 | The augmented LLM mental model + system prompts | AI Engineering (Chip Huyen) Ch.5: In-Context Learning, System vs User Prompts, Best Practices, Defensive Prompting; Building Effective Agents (Anthropic) § 'Building block: The augmented LLM' — retrieval + tools + memory as the atomic unit; Anthropic Prompt Engineering Guide Overview section: prompt structure, XML tagging, role clarity | Design a system prompt + structured output schema for a defined agent task; teach back the augmented LLM mental model with cited sources. |
| 2 | Tool calling via MCP + structured output | Model Context Protocol (MCP) Specification Introduction + Quickstart: build a client, connect to a server, call a tool; Chain-of-Thought Prompting (Wei et al., 2022) whole paper; Anthropic Prompt Engineering Guide Structured Outputs + Tool Use sections; Writing Effective Tools for AI Agents (Anthropic) whole post: tool-first design, poka-yoke, ACI principles | Build an augmented LLM that calls a tool via MCP and returns structured output; submit for assessment a.fnd.build with teach-back on each component. |
| 3 | Prompt Chaining, Routing, Parallelization — the simple patterns | Building Effective Agents (Anthropic) § 'Prompt Chaining', 'Routing', 'Parallelization' — patterns, diagrams, when-to-use, failure modes; Anthropic Cookbook: Basic Workflow Patterns Prompt Chaining + Routing + Parallelization implementations; AI Engineering (Chip Huyen) Ch.6: Agent overview — what 'agentic' actually means, the autonomy spectrum | Implement Prompt Chaining and Routing for a real task; explain in writing when each pattern applies and when a single LLM call is the right answer. |
| 4 | Orchestrator-Workers, Evaluator-Optimizer + the ReAct loop | Building Effective Agents (Anthropic) § 'Orchestrator-Workers', 'Evaluator-Optimizer' — diagrams, when-to-use, failure modes; ReAct: Synergizing Reasoning and Acting (Yao et al., 2022) whole paper; AI Engineering (Chip Huyen) Ch.6: planning, reflection, memory — how these enable the complex patterns; Anthropic Cookbook: Basic Workflow Patterns Orchestrator-Workers + Evaluator-Optimizer implementations | For a given task, choose among all 5 patterns, defend the choice with trade-offs grounded in sources, and Feynman-teach the full pattern taxonomy; assessment a.wf.choose. |
| 5 | Context as a finite resource — budgeting, altitude, and the Write/Select/Compress/Isolate framework | Effective Context Engineering for AI Agents (Anthropic) System prompt altitude + tool token-efficiency: how to allocate context budget across components; Context Engineering for Agents (LangChain) Write / Select / Compress / Isolate framework with Claude Code and SWE-agent case studies; AI Engineering (Chip Huyen) Ch.5 §Context Length and Context Efficiency: why longer context degrades precision | Analyze a provided agent trajectory, measure context waste (redundant tool outputs, bloated system prompt, stale messages), and prescribe fixes grounded in the Anthropic post. |
| 6 | Tool-result compaction, memory strategies, and sub-agent architectures for context isolation | Effective Context Engineering for AI Agents (Anthropic) Compaction techniques + note-taking + multi-agent context strategies: how to delegate to sub-agents to isolate context; Anthropic: How we built our multi-agent research system whole post: real sub-agent delegation architecture for context isolation; AI Engineering (Chip Huyen) Ch.10 §Step 1 (Enhance Context): memory strateies in production architectures | Diagnose a real context-engineering problem (budget blowout, memory strategy failure, or compaction gap) in an agent trajectory and prescribe a fix with cited reasoning; assessment a.ctx.note. |
| 7 | Naïve RAG → advanced: reranking, query transformation, HyDE | AI Engineering (Chip Huyen) Ch.6: RAG architecture, embedding-based retrieval, vector search — the full pipeline end to end; RAG Techniques (NirDiamant, GitHub) Notebooks: Chunking strategies, Query Transformation, HyDE — implement each and compare; Building Effective Agents (Anthropic) § 'Building block: The augmented LLM' — retrieval as the first augmentation | Build a naïve RAG pipeline (chunk → embed → retrieve → generate), then add reranking, query transformation, and HyDE; measure grounded-answer quality at each stage with a real metric (faithfulness or answer relevancy). |
| 8 | Self-RAG, Corrective RAG, Agentic RAG + evaluation | RAG Techniques (NirDiamant, GitHub) Notebooks: Self-RAG, Corrective RAG, Agentic RAG — the LLM decides what and how to retrieve; AI Engineering (Chip Huyen) Ch.6: RAG evaluation — faithfulness, answer relevancy, context precision; when RAG vs finetuning | Build an advanced RAG pipeline with Self-RAG / Corrective RAG / Agentic RAG; submit with measured improvement at each stage and a Feynman teach-back of the full retrieval stack; assessment a.rag.build. |
| 9 | LLM-as-judge, trajectory eval, and production observability | Evaluation and Benchmarking of LLM Agents: A Survey (2025) §3-5: evaluation dimensions, benchmarks, methods — the full landscape; Demystifying Evals for AI Agents (Anthropic) whole post: tasks, trials, graders, transcripts, harnesses — the eval architecture; OpenAI Agents SDK: Tracing & Evals Tracing, Evaluation, and Guardrails sections — production eval infrastructure; AI Engineering (Chip Huyen) Ch.7: Offline vs Online Evaluation, LLM-as-Judge, Human Evaluation, A/B Testing; Datadog LLM Observability full post: what to log, what to alert on, how to trace agent decisions | Build an eval harness (LLM-as-judge + trajectory evaluation) for an agent; run it and report measured results with failure-mode analysis and grounded recommendations; assessment a.eval.build. |
| 10 | Capstone — ship an agent improvement with evals + closed-book teach-back of the full S1 arc | AI Engineering (Chip Huyen) Ch.5 (Prompt Engineering), Ch.6 (RAG and Agents), Ch.7 (Evaluation), Ch.10 (Architecture); Building Effective Agents (Anthropic) whole post — review the 5 patterns and augmented LLM building block; Effective Context Engineering for AI Agents (Anthropic) whole post — review budgeting, compaction, memory, sub-agent strategies; ReAct (Yao et al., 2022) whole paper — review the foundational agent loop; Chain-of-Thought Prompting (Wei et al., 2022) whole paper — review the reasoning unlock; Evaluation and Benchmarking of LLM Agents: A Survey (2025) §3-5 — review eval dimensions and methods; RAG Techniques (NirDiamant, GitHub) Review key notebooks: HyDE, Self-RAG, Corrective RAG, Agentic RAG | Ship a production-quality agent improvement with evals proving it works, AND teach back the full S1 conceptual arc closed-book in Feynman style with zero gaps; assessment a.s1.final. |

## Units, outcomes & proofs

### Sem 1 · Weeks 1–2 · Foundations — The Augmented LLM
_Build the atomic building block of every agentic system — the augmented LLM. Master prompt engineering (system + user prompts, few-shot, chain-of-thought), structured output (JSON mode, tool schemas), function/tool calling via MCP, and the core mental model: retrieval + tools + memory as augmentations on a single LLM call. By the end, you can wire an LLM to external tools through MCP and produce machine-readable outputs, with every design choice grounded in the research._
- **apply** — Build an augmented LLM (prompt + structured output + tool call via MCP) and explain each component with cited sources.
  - *proof:* Build an augmented LLM (prompt + structured output + tool call via MCP) and explain each component with cited sources.
- *readings:*
  - **AI Engineering (Chip Huyen)** — Ch.5 (Prompt Engineering): In-Context Learning, System vs User Prompts, Context Efficiency, Best Practices, Defensive Prompting _(textbook, paid)_  · _Production prompt engineering — structured, evaluation-aware. The context-efficiency section previews Unit 3._
  - **Building Effective Agents (blog, Anthropic)** — § 'Building block: The augmented LLM' _(reference)_  · _The augmented LLM concept: retrieval + tools + memory as the atomic unit. Sets the mental model for the entire course._
  - **Model Context Protocol (MCP) Specification** — Introduction + Quickstart: build a client, connect to a server, call a tool _(reference)_ — https://modelcontextprotocol.io/  · _The universal standard for agent-tool integration. Hands-on: build an MCP client in Unit 1._
  - **Chain-of-Thought Prompting (Wei et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The technique that unlocked reasoning in LLMs. Must-understand for any agent builder._
  - **Anthropic Prompt Engineering Guide** — Overview + Structured Outputs + Tool Use sections _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Production reference for prompt structure, XML tagging, and structured output. The lab standard._

### Sem 1 · Weeks 3–4 · Workflow Patterns — Choosing the Right Architecture
_Learn to choose the right architecture for any agentic task. Master Anthropic's five workflow patterns — Prompt Chaining, Routing, Parallelization (sectioning + voting), Orchestrator-Workers, and Evaluator-Optimizer — through their canonical examples and failure modes. The key skill: when to use which pattern, when no pattern (just a single LLM call) is the right answer, and when to cross into true autonomous agents. Grounded in the Building Effective Agents post and ReAct paper._
- **evaluate** — For a given task, select among the 5 Anthropic workflow patterns, justify the trade-off, and teach back the full pattern taxonomy.
  - *proof:* For a given task, choose among the 5 Anthropic workflow patterns, defend the choice with trade-offs, and teach back the pattern taxonomy.
- *readings:*
  - **Building Effective Agents (blog, Anthropic)** — § 'Building blocks, workflows, and agents' — all 5 workflow patterns with diagrams and when-to-use guidance _(reference)_  · _The canonical reference. Every FAANG agent team knows this post. Diagrams make the patterns instantly recognizable._
  - **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): Agent overview, tools, planning, reflection, memory — complements the Anthropic patterns with evaluation perspective _(textbook, paid)_  · _Shows WHY patterns work and their failure modes — not just the patterns themselves._
  - **ReAct: Synergizing Reasoning and Acting (Yao et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent loop. ReAct = reasoning + action interleaving. Underpins the orchestrator-worker and evaluator-optimizer patterns._
  - **Anthropic Cookbook: Basic Workflow Patterns** — full cookbook _(reference)_ — https://platform.claude.com/cookbook/patterns-agents-basic-workflows  · _Reference Python implementations of all 5 patterns. Use as implementation templates, not copy-paste._

### Sem 1 · Weeks 5–6 · Context Engineering — The Finite Resource
_Master context as a finite, precious resource. Learn context budgeting (how much to allocate where), tool-result compaction (summarizing tool outputs to save tokens), memory strategies (conversation buffer, windowing, summarization, note-taking), and system-prompt altitude calibration. Apply the Write/Select/Compress/Isolate framework and Anthropic's guidance on sub-agent architectures for context isolation. The goal: keep an agent coherent over long trajectories without blowing the context window or degrading answer quality._
- **analyze** — Diagnose a context-engineering problem (budget/compaction/memory) in a real agent trajectory and prescribe a fix grounded in the Anthropic post.
  - *proof:* Diagnose a context-engineering problem (budget/compaction/memory) in a real agent trajectory and prescribe a fix, grounded in the Anthropic context engineering post.
- *readings:*
  - **Effective Context Engineering for AI Agents (blog, Anthropic, Sep 2025)** — whole post: system prompt altitude, tool token-efficiency, compaction, note-taking, multi-agent context strategies _(reference)_  · _THE definitive piece. Written by Anthropic's Applied AI team based on real production agent deployments at scale._
  - **Context Engineering for Agents (blog, LangChain, Jul 2025)** — Write / Select / Compress / Isolate framework; Claude Code, SWE-agent, multi-agent case studies _(reference)_ — https://www.langchain.com/blog/context-engineering-for-agents  · _Practical taxonomy with real agent examples. The four strategies map directly to implementation decisions._
  - **AI Engineering (Chip Huyen)** — Ch.5 §Context Length and Context Efficiency + Ch.10 §Step 1 (Enhance Context) _(textbook, paid)_  · _Ties context engineering into the broader AI system architecture. Shows where context decisions fit in production._
  - **Anthropic: How we built our multi-agent research system** — whole post _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _Real-world sub-agent architecture for context isolation. Maps to the advanced context-engineering pattern._

### Sem 1 · Weeks 7–8 · RAG & Retrieval — Naïve to Agentic
_Build and systematically improve a RAG pipeline. Start naive (chunk + embed + retrieve + generate), then advance through reranking, query transformation, HyDE, self-RAG, corrective RAG, and agentic retrieval (where the LLM decides what and how to retrieve). Measure grounded answer quality with a real metric (faithfulness, answer relevancy, context precision). The deliverable: a RAG pipeline you'd ship to production, with measured improvement at each stage._
- **create** — Build a RAG pipeline (naive → advanced with reranking/HyDE/self-RAG) and measure grounded-answer quality improvement with a real metric.
  - *proof:* Build a RAG pipeline (naive → advanced with reranking/HyDE/self-RAG) and measure grounded-answer quality improvement with a real metric.
- *readings:*
  - **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): RAG architecture, embedding-based retrieval, vector search, RAG evaluation, when RAG vs finetuning _(textbook, paid)_  · _Production RAG perspective. Focuses on evaluation and architecture decisions, not just implementation._
  - **RAG Techniques (NirDiamant, GitHub)** — Notebooks: Query Transformation, HyDE, Self-RAG, Corrective RAG, Agentic RAG _(reference)_ — https://github.com/NirDiamant/rag_techniques  · _The most comprehensive open-source collection of advanced RAG techniques. Each technique as a standalone notebook. The lab standard for Unit 4._
  - **Building Effective Agents (blog, Anthropic)** — § 'Building block: The augmented LLM' — retrieval as an augmentation _(reference)_  · _Positions RAG as one augmentation in the augmented-LLM building block. Connects Unit 4 back to Unit 1._

### Sem 1 · Week 9 · Evals & Observability — You Can't Improve What You Can't Measure
_Build the evaluation and observability layer that makes agent improvement possible. Master LLM-as-judge evaluation (pairwise comparison, rubric-based scoring, reference-based), trajectory-level evaluation (did the agent take the right path?), and production observability (traces, spans, token usage, latency, cost). The key skill: write an eval harness BEFORE building the agent, so every change is measured. Grounded in the LLM Agent Evaluation survey and production practices from Anthropic/OpenAI._
- **create** — Build an eval harness (LLM-as-judge + trajectory eval) for an agent, run it, and report measured results with failure-mode analysis.
  - *proof:* Build an eval harness (LLM-as-judge + trajectory eval) for an agent, run it, and report measured results with failure-mode analysis.
- *readings:*
  - **Evaluation and Benchmarking of LLM Agents: A Survey (2025)** — §3-5: evaluation dimensions, benchmarks, methods _(paper)_ — https://arxiv.org/html/2507.21504v1  · _Comprehensive survey of the agent evaluation landscape. The two-dimensional framework organizes all approaches._
  - **OpenAI Agents SDK: Tracing & Evals** — Tracing, Evaluation, and Guardrails sections _(reference)_ — https://openai.github.io/openai-agents-python/  · _Production eval infrastructure. Traces for debugging, evals for measuring, guardrails for safety._
  - **AI Engineering (Chip Huyen)** — Ch.7 (Evaluation): Offline vs Online Evaluation, LLM-as-Judge, Human Evaluation, A/B Testing _(textbook, paid)_  · _Chip's eval framework is the industry standard. Evaluation-first mindset throughout._
  - **Datadog LLM Observability** — full post _(reference)_ — https://www.datadoghq.com/blog/llm-evaluation-framework-best-practices/  · _Production observability patterns: what to log, what to alert on, how to trace agent decisions._

### Sem 1 · Week 10 · Semester 1 Finals — Applied Agent + Teach-Back
_Ship a production-quality agent improvement that demonstrates mastery of all S1 units: augmented LLM with MCP tool calling, deliberate workflow pattern selection, context-engineered for efficiency, RAG-enhanced retrieval, and measured with a real eval harness. Then teach back the full S1 conceptual arc, closed-book, in a Feynman style that exposes no gaps. This is the capstone: prove you can build AND explain agentic systems at a senior bar._
- **create** — Ship a production-quality agent improvement, with evals proving it works, and teach back the full S1 conceptual arc closed-book.
  - *proof:* Ship a production-quality agent improvement, with evals proving it works, and teach back the full S1 conceptual arc closed-book in Feynman style.

## Course library
- **Building Effective Agents (blog)** · Anthropic (Applied AI team) — whole post _(reference)_ — https://www.anthropic.com/engineering/building-effective-agents  · _Industry-defining agent design framework. The 5 workflow patterns + augmented LLM building block are the decision backbone of Unit 2._
- **Effective Context Engineering for AI Agents (blog)** · Anthropic (Applied AI team) — whole post _(reference)_ — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents  · _THE piece on context as a finite resource. System prompt altitude, tool token-efficiency, compaction, note-taking, multi-agent strategies. Anchors Unit 3._
- **Demystifying Evals for AI Agents (blog)** · Anthropic (Applied AI team) — whole post _(reference)_ — https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents  · _Agent eval architecture: tasks, trials, graders, transcripts, harnesses. Why teams without evals fly blind. Anchors Unit 5._
- **Writing Effective Tools for AI Agents (blog)** · Anthropic (Applied AI team) — whole post _(reference)_ — https://www.anthropic.com/engineering/writing-tools-for-agents  · _Tool design for non-deterministic systems. Evaluation-driven tool optimization. Poka-yoke, ACI principles. Complements Unit 1._
- **Advanced Large Language Model Agents (MOOC, Spring 2025)** · Dawn Song & Xinyun Chen, UC Berkeley — Lectures: Inference-Time Reasoning, Learning to Reason, Reasoning/Memory/Planning, Coding Agents, Multimodal Agents _(course)_ — https://rdi.berkeley.edu/adv-llm-agents/sp25  · _The gold-standard university curriculum. Guest lectures from DeepMind, OpenAI, Meta, CMU — the people who built the field._
- **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent loop. Reasoning + action interleaving — the core idea behind every modern agent architecture._
- **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models** · Wei et al. — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The reasoning technique that unlocked modern prompting and agent planning. Must-understand for any agent builder._
- **Production-Grade Agentic AI Workflows: A Practical Guide** · Bandara et al. — whole paper _(paper)_ — https://arxiv.org/html/2512.08769v1  · _9 production best practices: tool-first design, single-responsibility agents, externalized prompts, KISS principle. The engineering discipline behind agentic workflows._
- **OWASP Top 10 for LLM Applications + Agentic Top 10** · OWASP — Tool Security, Input Validation, Memory Security, Human-in-the-Loop _(reference)_ — https://cheatsheetseries.owasp.org/cheatsheets/AI_Agent_Security_Cheat_Sheet.html  · _Security is not optional for production agents. Prompt injection is the #1 vulnerability (73% of deployments). Cross-cutting reference for all units._

## Assessment plan
- **a.fnd.build** (summative, project, ≥apply) — Build an augmented LLM (prompt + structured output + tool call via MCP) and explain each component with cited sources.
- **a.wf.choose** (summative, explain, ≥evaluate) — For a given task, choose among the 5 Anthropic workflow patterns, defend the choice with trade-offs, and teach back the pattern taxonomy.
- **a.ctx.note** (summative, explain, ≥analyze) — Diagnose a context-engineering problem (budget/compaction/memory) in a real agent trajectory and prescribe a fix, grounded in the Anthropic context engineering post.
- **a.rag.build** (summative, project, ≥create) — Build a RAG pipeline (naive → advanced with reranking/HyDE/self-RAG) and measure grounded-answer quality improvement with a real metric.
- **a.eval.build** (summative, project, ≥create) — Build an eval harness (LLM-as-judge + trajectory eval) for an agent, run it, and report measured results with failure-mode analysis.
- **a.s1.final** (summative, project, ≥create) — Ship a production-quality agent improvement, with evals proving it works, and teach back the full S1 conceptual arc closed-book in Feynman style.
