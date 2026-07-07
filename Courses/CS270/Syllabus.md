# CS270 — AI Agents

> Design, evaluate, and ship an LLM agent at a senior bar: pick the right architecture for the task, build evals and observability for it, engineer its context as a finite resource, and apply it to real production work. Then teach back the full conceptual arc closed-book.

This course builds the core competency of a senior AI engineer: designing, building, and evaluating LLM-powered systems that do real work. Semester 1 moves from the atomic building block — the augmented LLM (prompt + structured output + tool calling) — through Anthropic's five workflow patterns, context engineering as a finite-resource discipline, and production RAG (naive to agentic). Every unit is assessed through grounded, cited work tied to the learner's real production system. Anchored on Chip Huyen's AI Engineering and the learner's own copy of Hands-On Large Language Models, supplemented by Anthropic's engineering blog (Building Effective Agents, Effective Context Engineering, Demystifying Evals) and the UC Berkeley LLM Agents MOOC. Designed for a KAIST CS graduate targeting FAANG senior in months.

**Credits:** 2  ·  **Domain:** ai-agents  ·  **Prereqs:** none

## Primary text
- **AI Engineering: Building Applications with Foundation Models** · Chip Huyen — Ch.5 (Prompt Engineering) + Ch.6 (RAG and Agents) + Ch.10 (Architecture) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166298/  · _The definitive production-AI-engineering book. Evaluation-first, pattern-driven, conceptually aligned with Anthropic's agent philosophy. Every chapter maps to a CS270 unit._

## What the best in this field can do
The best AI agent engineers in 2026 design evals before they build — eval literacy is the single biggest signal of real production experience (Digital Applied, 2026). They ship agents that run for months without on-call incidents, backed by full observability and tracing (89% of production teams, LangChain State of Agent Engineering 2026). They route across multiple LLM providers with cost-aware abstraction layers (75%+ use multiple models). They treat system prompts as version-controlled software contracts with eval-backed changes. They build RAG that survives corpus drift — with chunking strategy, reranking, query transformation, and measured recall@k. They know when NOT to use an agent (Anthropic: start with the simplest solution). They debug multi-turn failures via traces, not intuition. They speak the language of product AND infrastructure — soft skills predict senior trajectory. At the staff+ level: they design agent architectures that entire teams build against, they set the eval philosophy for the org, and their postmortems read like engineering literature. This course designs backward from this bar.

**How the best practice:**
- Start simple, add agentic complexity only when it demonstrably improves outcomes — measure with evals, not gut (Anthropic, Building Effective Agents).
- Design evals before building — specify what success means for the agent in three grader types: code-based, model-based, human (Anthropic, Demystifying Evals).
- Implement full observability: trace every tool call, reasoning step, and intermediate result. 94% of production teams have it (LangChain State of Agent Engineering 2026).
- Route across multiple LLM providers: Claude for long context/reasoning, GPT for structured output, open-weight for cost. Abstract the differences (AY Automate, 15 Skills).
- Version system prompts like code with changelogs and eval results attached to every change (AY Automate, 2026).
- Chunk by semantic boundary, rerank by default, version embedding models — production RAG is not a demo (AY Automate, 15 Skills).
- Combine code-based graders (unit tests, string match), model-based graders (LLM-as-judge), and human review for nuanced cases (Anthropic, Demystifying Evals).
- Treat cost as a first-class metric: track cost per task, latency, token usage as regression baselines alongside quality metrics (Digital Applied, 2026).

**Signature work that earns a seat with the best:** The portfolio that earns a seat with the best AI engineering teams: (1) An agent that completes a real task end-to-end — multi-step tool calls, error recovery, conversation memory, shipped with a live demo or API endpoint. (2) A RAG system with measured quality — over real documents, with chunk quality scoring, source attribution, and a published eval report (hallucination rate, recall@k, answer relevancy). (3) An evaluation harness — DeepEval or pytest-based suite that proves the agent and RAG work, integrated into CI, with regression baselines tracked over time. (4) A postmortem/write-up — what failed in production, what you changed, what you would do differently. (5) An open-source contribution — a PR to LangChain/MCP, a useful tool server, or a RAG technique notebook. For Mukhammaddiyor specifically: the Rizo GO production system is the ideal substrate. Ship agent improvements to Rizo GO with public eval reports, write postmortems, open-source the eval harness. That portfolio says "I don't just build agents — I prove they work, I learn from failures, and I contribute to the ecosystem." That is the senior bar.

## How to keep evolving
State of the art (mid-2026): CLI coding agents (Claude Code, Cursor, Codex CLI) are replacing traditional IDEs — delegation over suggestion, 30% faster shipping (Firecrawl Trends). MCP (Model Context Protocol) is becoming the standard for tool integration after mid-2026 resurgence. Multi-agent systems with hierarchical orchestration are replacing ad-hoc loops. 1M+ token context windows are changing architecture but context engineering remains critical (Anthropic Effective Context Engineering). Recursive reasoning models (OpenAI o1/o3, DeepSeek R1) enable agents that self-refine through chain-of-thought before acting. Browser agents are automating web workflows (45% YoY growth). Vertical AI agents (healthcare, legal, finance) are outperforming general-purpose with 40%+ efficiency gains. The trust gap — 51% daily AI use but only 29% trust output (Stack Overflow 2025) — defines the market: engineers who can prove their agents work reliably command a 56% wage premium (PwC 2025). Where agents are heading: autonomous coding teams, agentic commerce (20% of e-commerce tasks by agents), personal AI assistants as common as smartphones, and verifiability as the key constraint — agents automate fastest where output can be objectively verified (Anthropic 2026 Agentic Coding Trends Report).

- **Lilian Weng's Blog — LLM Powered Autonomous Agents + reasoning/safety posts** _(reference)_ — https://lilianweng.github.io/  · _The most-cited agent engineering reference. Her posts on agents, reasoning, and safety are required reading for the field._
- **Latent Space Podcast & Newsletter** · Swyx & Alessio Fanelli _(reference)_ — https://www.latent.space/  · _The voice of AI engineering. Interviews with every major builder. Swyx coined 'AI engineer' as a distinct role._
- **Anthropic Engineering Blog** _(reference)_ — https://www.anthropic.com/engineering  · _Building Effective Agents, Demystifying Evals, Effective Context Engineering — the industry-defining references._
- **LangChain Blog** _(reference)_ — https://www.langchain.com/blog  · _Production survey data (1,300+ respondents) and practical engineering posts on agent architecture._
- **Interconnects Newsletter** · Nathan Lambert _(reference)_ — https://www.interconnects.ai/  · _The clearest source on post-training, RLHF, and reasoning models._
- **Ahead of AI Newsletter** · Sebastian Raschka _(reference)_ — https://magazine.sebastianraschka.com/  · _Monthly curated list of notable LLM research papers including agents, reasoning, and efficiency._
- **Hamel Husain's Blog — Your AI Product Needs Evals** _(reference)_ — https://hamel.dev/  · _The canonical starting point for evaluation infrastructure. Practical, opinionated, almost entirely correct._
- **Shreya Shankar's Research — Who Validates the Validators?** _(reference)_ — https://www.shreya-shankar.com/  · _The closest thing to a rigorous framework for LLM judges and eval validation._
- **Eugene Yan's Blog — AI Engineering** _(reference)_ — https://eugeneyan.com/  · _Bridging AI research and production engineering. Practical guides on building and evaluating AI systems._
- **Simon Willison's Blog — LLM behavior cataloging + prompt injection** _(reference)_ — https://simonwillison.net/  · _Has been cataloging LLM behavior since before most companies had an AI strategy. Prompt injection canon._
- **Chip Huyen's Blog + AI Engineering book resources** _(reference)_ — https://huyenchip.com/  · _The author of the course's primary text. Production AI engineering frameworks and evaluation-first thinking._
- **ai-agent-papers (GitHub)** · masamasa59 _(reference)_ — https://github.com/masamasa59/ai-agent-papers  · _Biweekly Arxiv searches for AI agent papers. Continuously updated._
- **AI Engineer World's Fair** _(reference)_ — https://www.ai.engineer/  · _Annual conference (6,000+ engineers). The gathering point for the AI engineering discipline._

**Deliberate-practice regimen:** The regimen: (1) Daily: one agent engineering task from the course spine, at the engine-assigned difficulty tier, with faded scaffolding. Every task produces a working artifact + a grounded note citing the researched resource. (2) Weekly: one retrospective — what worked, what broke, what the eval caught, what it missed. Write it down. (3) Per unit: one teach-back (Feynman style, closed-book) of the unit's concepts to the professor. (4) Monthly: one postmortem-quality write-up of a production failure or near-miss with the agent. (5) Portfolio-driven: ship one real agent improvement to Rizo GO per unit, with a public eval report. (6) Stretch target: contribute one PR to an open-source agent tool (LangChain, MCP server, RAG technique) per semester. (7) Stay current: read Latent Space, Anthropic Engineering, and Sebastian Raschka's monthly paper list weekly. When a new paper drops, skim it and write one paragraph on what it means for your agent work. This is the regimen of an engineer who compounds — not someone who peaks after the course.

## How this course is taught
*Concept-first, evaluation-driven, production-grounded. Every lesson starts with the mental model (why this matters at scale), then moves to the hands-on skill, then to the eval that proves it works. Faded scaffolding: worked example to completion (blanked steps) to independent. Socratic hint ladder before giving answers. Deliberate practice — one sub-goal just beyond current level, immediate feedback, refined re-attempt. Interleave retrieval of weak/due items from the spaced-repetition engine. Preempt common misconceptions before they form. Every wrong answer triggers a targeted micro-lesson on the exact mistake, then a re-test. Connect every skill back to the mastery model.*

**Misconceptions the professor preempts:**
- More agentic is not better: the simplest thing that works is usually a single LLM call. Add agentic complexity only when the eval proves it helps.
- Long context windows do not eliminate the need for context engineering: 1M-token windows make naive stuffing worse, not better. Context is still a finite, precious resource.
- RAG is not just similarity_search(): production RAG requires chunking strategy, reranking, query transformation, eval, and corpus-drift management.
- The agent's word is not enough: agents hallucinate outcomes. The transcript says 'flight booked' but the database shows no reservation. Always verify the outcome, not the narrative.
- Evals do not slow down shipping: evals accelerate shipping by catching regressions before users do. The teams without evals are the ones moving slowest.
- One model provider is not enough: provider lock-in is a liability. Rate limits, pricing shifts, and new model releases happen monthly. Multi-provider abstraction is not optional.
- Fine-tuning does not solve everything: 57% of production teams do not fine-tune. Prompt engineering + RAG + evals gets you further, faster, for less maintenance burden.

## Enduring understandings
- Start with the simplest thing that works; add agentic autonomy only when it demonstrably helps.
- The augmented LLM (retrieval + tools + memory) is the atomic building block.
- An agent you can't evaluate you can't improve — the eval harness is part of the design.
- Context is a finite, precious resource — every token must earn its place.
- The right architecture depends on the task, not the framework.
- The best engineers ship agents that run for months without on-call incidents — observability makes that possible.

## Grading policy
hw 40% · quiz 30% · finals 30%

## Weekly schedule, outcomes & readings

### Sem 1 · Weeks 1–2 · Foundations — prompting, structured output, tool/function calling
_Build the atomic building block of every agentic system — the augmented LLM. Master prompt engineering (system + user prompts, few-shot, chain-of-thought), structured output (JSON mode, tool schemas), and function/tool calling. By the end, you can wire an LLM to external tools and produce machine-readable outputs, with every design choice grounded in the research._
- **apply** — Build an augmented LLM (prompt + structured output + tool call) with a grounded note citing the researched resource and a Rizo GO application. Include one quantitative eval metric.
  - *proof:* Builds an augmented LLM (prompt + structured output + tool call) with a grounded note citing the researched resource + Rizo GO tie-in. Must include one quantitative eval metric.
- *readings:*
  - **AI Engineering (Chip Huyen)** — Ch.5 (Prompt Engineering): In-Context Learning, System vs User Prompts, Context Efficiency, Best Practices, Defensive Prompting _(textbook, paid)_  · _Production prompt engineering — structured, evaluation-aware. The context-efficiency section previews Unit 3._
  - **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.6 (Prompt Engineering) + Ch.7 (Advanced Text Generation: LangChain chains, memory, agents, ReAct) _(textbook, paid)_  · _Code-backed, visual. Ch.7 introduces ReAct agents — the bridge to Unit 2's workflow patterns._
  - **Building Effective Agents (Anthropic)** — Section: 'Building block: The augmented LLM' _(reference)_  · _The augmented LLM concept: retrieval + tools + memory as the atomic unit. Sets the mental model for the entire course._
  - **Anthropic Prompt Engineering Guide** — Overview + Structured Outputs sections _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Production reference for prompt structure, XML tagging, and structured output._
  - **Chain-of-Thought Prompting (Wei et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The technique that unlocked reasoning in LLMs. Must-understand for any agent builder._

### Sem 1 · Weeks 3–4 · Workflow Patterns — chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
_Learn to choose the right architecture for any agentic task. Master Anthropic's five workflow patterns — Prompt Chaining, Routing, Parallelization (sectioning + voting), Orchestrator-Workers, and Evaluator-Optimizer — through their canonical examples and failure modes. The key skill: when to use which pattern, and when no pattern (just a single LLM call) is the right answer._
- **evaluate** — Select among the 5 Anthropic workflow patterns for a real Rizo GO task, defend the choice with trade-off analysis, and explain when a simpler alternative would be better. Feynman teach-back required.
  - *proof:* Chooses among the 5 Anthropic workflow patterns for a real Rizo GO task, defends the choice with trade-off analysis, and explains when a simpler alternative would be better. Feynman teach-back required.
- *readings:*
  - **Building Effective Agents (Anthropic)** — Section: 'Building blocks, workflows, and agents' — all 5 workflow patterns with diagrams and when-to-use guidance _(reference)_  · _The canonical reference. Every FAANG agent team knows this post. Diagrams make the patterns instantly recognizable._
  - **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): Agent overview, tools, planning, reflection, memory _(textbook, paid)_  · _Complementary framework: focuses on why patterns work and their failure modes, not just the patterns themselves._
  - **Anthropic Cookbook: Basic Workflow Patterns** — full cookbook _(reference)_ — https://platform.claude.com/cookbook/patterns-agents-basic-workflows  · _Reference Python implementations of all 5 patterns. Use as implementation templates._
  - **ReAct: Synergizing Reasoning and Acting (Yao et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent loop. ReAct = reasoning + action interleaving. Underpins the orchestrator-worker and evaluator-optimizer patterns._

### Sem 1 · Weeks 5–6 · Context Engineering — budgeting, tool-result compaction, memory
_Master context as a finite, precious resource. Learn context budgeting (how much to allocate where), tool-result compaction (summarizing tool outputs to save tokens), and memory strategies (conversation buffer, windowing, summarization, note-taking). Apply the Write/Select/Compress/Isolate framework. The goal: keep an agent coherent over long trajectories without blowing the context window._
- **analyze** — Diagnose and fix a context problem (budget/compaction/memory) in a real agent trajectory, proposing a fix citing Anthropic/LangChain context engineering sources, and map it to a Rizo GO agent scenario.
  - *proof:* RAG-grounded diagnostic note: identifies a context problem (budget/compaction/memory) in a real agent trajectory, proposes a fix citing Anthropic/LangChain context engineering sources, and maps to a Rizo GO agent scenario.
- *readings:*
  - **Effective Context Engineering for AI Agents (Anthropic, Sep 2025)** — whole post: system prompt altitude, tool token-efficiency, compaction, note-taking, multi-agent context _(reference)_  · _The definitive piece. Written by Anthropic's Applied AI team based on real production agent deployments._
  - **Context Engineering for Agents (LangChain, Jul 2025)** — Write / Select / Compress / Isolate framework; Claude Code, SWE-agent, multi-agent case studies _(reference)_ — https://www.langchain.com/blog/context-engineering-for-agents  · _Practical taxonomy with real agent examples. The four strategies map directly to implementation decisions._
  - **AI Engineering (Chip Huyen)** — Ch.5 Context Length and Context Efficiency + Ch.10 Step 1 (Enhance Context) _(textbook, paid)_  · _Ties context engineering into the broader AI system architecture. Shows where context decisions fit in production._
  - **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.7 Memory: Conversation Buffer, Windowed Buffer, Conversation Summary (pp.209-217) _(textbook, paid)_  · _Code-backed implementations of memory patterns. Build and compare buffer types._

### Sem 1 · Weeks 7–8 · RAG & Context — naive to advanced to agentic retrieval
_Build and systematically improve a RAG pipeline. Start naive (chunk + embed + retrieve + generate), then advance through reranking, query transformation, HyDE, self-RAG, and agentic retrieval. Measure grounded answer quality with a real metric. The deliverable: a RAG pipeline you would ship to production, not a notebook demo._
- **create** — Build and evaluate a RAG pipeline (naive to improved) over real documents. Report recall@k before/after, hallucination rate before/after, and one quantitative answer-quality metric. Grounded note + self-explanation required.
  - *proof:* Builds a RAG pipeline (naive to improved) over real documents. Must report: recall@k before/after, hallucination rate before/after, one quantitative answer-quality metric. Grounded note citing the researched resource. Self-explanation required.
- *readings:*
  - **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.8 (Semantic Search and RAG): Dense Retrieval, Reranking, RAG fundamentals, Advanced RAG, RAG Evaluation (pp.225-258) _(textbook, paid)_  · _Complete hands-on RAG chapter with code. Covers the full pipeline from embeddings to evaluation._
  - **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): RAG architecture, embedding-based retrieval, vector search, RAG evaluation _(textbook, paid)_  · _Production RAG perspective: when RAG vs finetuning, how to evaluate retrieval quality._
  - **RAG Techniques (NirDiamant, GitHub)** — Notebooks: Query Transformation, HyDE, Self-RAG, Corrective RAG, Agentic RAG _(reference)_ — https://github.com/NirDiamant/rag_techniques  · _The most comprehensive open-source collection of advanced RAG techniques. Each technique has a standalone notebook._
  - **Building Effective Agents (Anthropic)** — Section: 'Building block: The augmented LLM' — retrieval as an augmentation _(reference)_  · _Positions RAG as one augmentation in the augmented-LLM building block. Connects Unit 4 back to Unit 1._

### Sem 1 · Week 9 · Semester 1 Finals (applied + teach-back)
_Ship an applied agent improvement for Rizo GO that demonstrates mastery of all S1 units: augmented LLM, workflow pattern selection, context engineering, and RAG. Then teach back the full S1 conceptual arc, closed-book, in a Feynman style that exposes no gaps. This is the capstone: prove you can build and explain agentic systems at a senior bar._
- **create** — Ship an applied agent improvement for Rizo GO demonstrating mastery of all S1 units (augmented LLM + workflow pattern selection + context engineering + RAG) AND teach back the full S1 conceptual arc, closed-book, Feynman style.
  - *proof:* Ships an applied agent improvement for Rizo GO demonstrating mastery of all S1 units (augmented LLM + workflow pattern selection + context engineering + RAG). Then teaches back the full S1 conceptual arc, closed-book, Feynman style. Both components required.
- *readings:*
  - **All S1 unit resources (cumulative)** — Review all readings from units 1-4 as the capstone draws on every concept _(reference)_  · _The finals integrate all four units. Revisit the primary text and key papers (AI Engineering Ch.5-6,10, Building Effective Agents, Effective Context Engineering, ReAct, Chain-of-Thought) for the closed-book teach-back._

## Course library
- **Hands-On Large Language Models** · Jay Alammar & Maarten Grootendorst — Ch.6 (Prompt Engineering) + Ch.7 (Advanced Text Generation/Agents) + Ch.8 (Semantic Search & RAG) _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Learner already owns this (in Uploads/CS270/). Visual, code-backed, ideal hands-on companion for KAIST engineering style._
- **Building Effective Agents** · Anthropic Applied AI team — whole post _(reference)_ — https://www.anthropic.com/engineering/building-effective-agents  · _Industry-defining agent design framework. The 5 workflow patterns are the decision backbone of Unit 2._
- **Effective Context Engineering for AI Agents** · Anthropic Applied AI team — whole post _(reference)_ — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents  · _THE piece on context as a finite resource. System prompt design, tool token-efficiency, compaction, note-taking, multi-agent strategies._
- **Demystifying Evals for AI Agents** · Anthropic — whole post _(reference)_ — https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents  · _Eval taxonomy: tasks, trials, graders, transcripts, outcomes, harnesses. The eval design reference for the entire course._
- **Large Language Model Agents (MOOC)** · Dawn Song & Xinyun Chen, UC Berkeley — Lectures: LLM Reasoning, ReAct/Agent History, Agentic Frameworks, RAG, Compound AI Systems _(course)_ — https://llmagents-learning.org/f24  · _The best canonical university curriculum on LLM agents. Guest lectures from DeepMind, OpenAI, Databricks, Anthropic._
- **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _Foundational agent paper. Reasoning + action interleaving — the core idea behind every modern agent._
- **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models** · Wei et al. — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The reasoning technique that unlocked modern prompting and agent planning._

## Assessment plan
- **a.fnd.build** (summative, open_problem, ≥apply) — Builds an augmented LLM (prompt + structured output + tool call) with a grounded note citing the researched resource + Rizo GO tie-in. Must include one quantitative eval metric.
- **a.wf.choose** (summative, explain, ≥evaluate) — Chooses among the 5 Anthropic workflow patterns for a real Rizo GO task, defends the choice with trade-off analysis, and explains when a simpler alternative would be better. Feynman teach-back required.
- **a.ctx.note** (summative, explain, ≥analyze) — RAG-grounded diagnostic note: identifies a context problem (budget/compaction/memory) in a real agent trajectory, proposes a fix citing Anthropic/LangChain context engineering sources, and maps to a Rizo GO agent scenario.
- **a.rag.build** (summative, open_problem, ≥create) — Builds a RAG pipeline (naive to improved) over real documents. Must report: recall@k before/after, hallucination rate before/after, one quantitative answer-quality metric. Grounded note citing the researched resource. Self-explanation required.
- **a.s1.final** (summative, open_problem, ≥create) — Ships an applied agent improvement for Rizo GO demonstrating mastery of all S1 units (augmented LLM + workflow pattern selection + context engineering + RAG). Then teaches back the full S1 conceptual arc, closed-book, Feynman style. Both components required.
