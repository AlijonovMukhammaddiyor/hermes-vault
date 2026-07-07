# AG201 — AI Agent Engineering

> Design, build, evaluate, and deploy production-grade AI agent systems — from a single ReAct loop to multi-agent orchestrations — with the architectural judgment of a staff-level engineer.

From scratch to frontier: a 24-week, two-semester course that builds every layer of AI agent engineering. Starts with Python and LLM fundamentals (transformers, attention, prompting), then constructs the full agent stack layer by layer — structured output, tool use, agent loops, context engineering, RAG, multi-agent orchestration, code-execution agents, and production deployment. Evaluation and observability are threaded throughout, not deferred. Grounded in primary research (Anthropic, Cognition, Manus, Berkeley LLM Agents MOOC) and anchored by Jurafsky & Martin SLP3 plus Chip Huyen's AI Engineering. Graduates ship a portfolio-grade agent system and can defend architecture choices with quantitative reasoning about cost, latency, and reliability.

**Credits:** 4  ·  **Domain:** ai-engineering  ·  **Prereqs:** none

## Primary text
- **Speech and Language Processing (3rd ed. draft)** · Dan Jurafsky & James H. Martin — ch. 9-12 (transformers, LLMs, prompting, fine-tuning, RLHF, RAG, agents) _(textbook)_ — https://web.stanford.edu/~jurafsky/slp3/  · _The canonical, free, continuously updated NLP/LLM reference — chapters 9-12 cover the full LLM stack that agents are built on._

## What the best in this field can do
A staff-level agent engineer can: (1) decompose an ambiguous problem into the right control-flow shape (prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer); (2) build the evaluation and observability infrastructure that makes iteration possible; (3) reason quantitatively about cost, latency, and reliability trade-offs; (4) design agent harnesses that survive model upgrades; (5) know when NOT to add agentic complexity; (6) read and critique a frontier agent architecture from primary sources; (7) ship a production agent system that others use.

**How the best practice:**
- Build fast, analyze traces, run small evals (10-20 samples), do error analysis to isolate the weakest component, improve that component, repeat. This loop IS the work.
- End-state evaluation for stateful agents, not turn-by-turn. LLM-as-judge for scalable scoring plus mandatory human review to catch edge cases.
- Track total runtime per tool call, total tool calls, total token consumption, tool error rates, and trajectory quality — not just top-line accuracy.
- Keep architecture simple. Make reasoning visible. Ensure reliable, well-scoped tool interactions. Use checkpointing, retry logic, and incremental deployments.
- Design harnesses expecting to re-architect repeatedly as models improve. The willingness to strip away scaffolding when models internalize it is the staff-level muscle.

**Signature work that earns a seat with the best:** A portfolio-grade agent system shipped and used by real people: either (a) a code-execution agent that solves real software engineering tasks in a sandbox, (b) a research agent that performs multi-source deep research with citations, or (c) a domain-specific multi-agent system that orchestrates parallel workers. The system must have full observability, a documented eval harness, and an architecture decision record explaining each choice quantitatively. This is what earns a seat with the best — not a certificate, but demonstrable capability.

## How to keep evolving
The central live debate (2025-2026): single-agent (Cognition) vs. multi-agent (Anthropic). Anthropic's multi-agent system outperforms single-agent by 90.2% on internal evals but uses 15× more tokens. Code-execution agents (CodeAct) increasingly outperform JSON tool-calling. The field is moving from SWE-bench Verified (now saturated) to harder benchmarks (SWE-bench Pro, Terminal-Bench, SWE-bench Multilingual). Multi-turn RL for agentic behavior (AgentGym-RL, RAGEN) is the next frontier — training agents, not just prompting them. Standardization is emerging (MCP for tool integration, AGENTS.md for project context).

- **Latent Space (swyx & Alessio)** _(reference)_ — https://latentspacepod.com  · _The AI-engineering publication of record — newsletter, podcast, weekly LLM Paper Club on Discord._
- **Simon Willison's Weblog** _(reference)_ — https://simonwillison.net  · _Near-daily practical AI engineering — the 'lethal trifecta' framing for agent security._
- **Ahead of AI (Sebastian Raschka)** _(reference)_ — https://magazine.sebastianraschka.com  · _Deep technical dives on LLM research — especially training and fine-tuning advances._
- **Interconnects (Nathan Lambert)** _(reference)_ — https://interconnects.ai  · _RLHF and post-training deep analysis — the training side of agent capability._
- **LLM Agents Discord (Berkeley MOOC community)** _(reference)_ — https://discord.gg/llm-agents  · _Peer learning, paper discussion, project sharing around the Berkeley course._
- **COLM (Conference on Language Modeling)** _(reference)_ — https://colmweb.org  · _The LLM-focused academic venue — where the best agent architecture papers are published._
- **Anthropic Engineering Blog** _(reference)_ — https://anthropic.com/engineering  · _Primary source for production agent architecture, eval methodology, and tool design._

**Deliberate-practice regimen:** Each unit: concept lesson (diagram + primary source) → minimal from-scratch implementation → eval (10-20 sample test set) → error analysis → improve → re-eval. Weekly: read one agent paper and write a one-paragraph critique. By Semester 2: study one production agent system's source code or architecture deep-dive each month (OpenHands, SWE-agent, Aider). Ship one real project by course end. The rhythm is build → measure → improve → reflect, every week.

## How this course is taught
*Concept-first, build-second, evaluate-third. Every new idea starts with the mental model (diagram + primary source), then a minimal implementation from scratch (no framework on first pass), then an eval that proves it works. Faded scaffolding: heavily guided on foundations, increasingly independent as the learner builds agency. Wrong answers get targeted micro-lessons on the exact misconception, then re-testing. Every unit connects back to a real production system the learner is studying (Anthropic, Manus, Cognition, Fin).*

**Misconceptions the professor preempts:**
- Agents are just LLMs with tools wired in — the real complexity is context management, error recovery, and eval, not the wiring.
- Multi-agent is always better — in reality, single-agent beats multi-agent for tightly coupled work, and multi-agent's cost (15× tokens) must be justified by the task structure.
- You need LangChain/CrewAI to build agents — the best engineers build directly against APIs first, add framework abstraction only when it earns its place.
- Prompt engineering is tweaking wording — it's programming in natural language: structured output schemas, few-shot selection, system-message architecture.
- Eval can wait until the end — eval is the engine of improvement and must be built alongside the agent from day one.
- KV-cache is an infra detail — KV-cache hit rate is the single most important metric for production agent cost and latency.

## Enduring understandings
- The LLM is the reasoning core; tools are its arms; structured output is its reliable communication protocol. Every agent architecture is a composition of these three primitives.
- Evaluation is not a final step — it is the engine of improvement. The #1 differentiator between competent and excellent agent engineers is disciplined eval and error analysis.
- Context engineering — KV-cache economics, compaction, externalized memory, preserving failures — is where reliability is won or lost, not prompt polishing.
- Architecture follows task structure. Multi-agent wins for parallelizable, independent subtasks. Single-agent or deterministic pipelines win for tightly coupled work. Know when not to add agentic complexity.
- The Bitter Lesson applies at the application layer: scaffolding that models can internalize will be obsolete. Build harnesses that survive model upgrades.
- Compound errors in agentic systems mean minor issues can derail entire runs. Observability, checkpointing, and graceful error recovery are not optional — they are the system.
- The goal is not to wire a framework — it is to understand the architecture deeply enough to rebuild it when the framework changes.

## Grading policy
hw 40% · quiz 15% · exam 15% · midterm 10% · finals 20%

## Week-by-week plan

| Week | Focus | Readings | Deliverable |
|---|---|---|---|
| 1 | Python environment, data structures, functions, type hints, list/dict comprehensions — the patterns agents use to process LLM output. | AI Python for Beginners (DeepLearning.AI) Lessons 1-2 | A Python script that calls a REST API (e.g., OpenWeatherMap), parses JSON, handles errors, and prints a formatted summary. |
| 1 | Tokenization — BPE, token vocabulary, special tokens, context windows. What the model actually 'sees' vs what you send. | Karpathy: Let's build GPT from scratch first 60 min (tokenization + bigram baseline); SLP3 ch. 2 sec. 2.5 (tokenization) | Implement a BPE tokenizer from scratch on a small corpus. Explain: why subword tokenization? What happens to out-of-vocabulary words? |
| 1 | System messages, few-shot examples, CoT, output format specification. Prompt as programming — explicit over implicit, constraints over hopes. | Anthropic Prompt Engineering Guide full; ChatGPT Prompt Engineering (DLAI) lessons 1-6 | Write 5 prompts for the same task (e.g., 'classify customer support tickets by urgency and category') with escalating quality: naive → system message → few-shot → CoT → structured JSON output. Score each on accuracy against a 10-example test set. Explain why each improvement moved the needle. |
| 1 | JSON mode vs function calling vs structured outputs. Schema design. Parsing and validation. The API contract pattern: define schema → send with prompt → parse response → act on structured result. | OpenAI Structured Outputs full; Anthropic Tool Use full | Build a 'smart form filler' that takes a natural language description (e.g., 'I want to book a flight to Tokyo next Tuesday, prefer morning, economy') and returns a validated JSON object with extracted fields. Handle missing fields, ambiguous values, and validation errors. Test against 10 varied inputs. |
| 1 | Tool definition (name, description, parameter schema — the description IS the interface). Single tool call: LLM decides → code executes → result fed back. Error modes: hallucinated calls, missing args, wrong tool selection. | Anthropic: Writing Effective Tools full | Build a single-tool agent (e.g., weather-by-city, currency converter, or database query) that: (a) defines a tool with a proper schema and description, (b) calls the LLM, (c) parses the tool-call from the response, (d) executes the tool, (e) feeds the result back to the LLM for a final answer. No framework — raw API calls only. |
| 1 | The ReAct loop: Thought → Action → Observation → (repeat) → Final Answer. Prompt structure: system message + tool descriptions + scratchpad. Stop conditions and max steps. | ReAct (Yao et al.) sec. 1-3 (intro, method, experiments); Agentic AI (DLAI) reflection + tool use lessons | Implement a working ReAct agent from scratch (~400 lines, no framework) with 2-3 real tools. Include: system prompt with tool descriptions, a Thought-Action-Observation loop, stop conditions (max steps + final answer detection), and a 10-example eval set. |
| 1 | KV-cache economics — what it is, why the hit rate is the #1 metric, 10× cost difference cached vs uncached. Context compaction strategies. The 'keep wrong turns in' principle. | Manus Context Engineering Principles 1-3 (KV-cache, mask-don't-remove, file system as context); LLMs Get Lost in Multi-Turn abstract + sec. 1-3 | Instrument your ReAct agent to measure: tokens per tool call, KV-cache hit rate, context window usage %. Run 5 multi-turn tasks and produce a context-efficiency report. Identify the biggest context-waster and fix it. |
| 1 | Embeddings, vector databases, chunking strategies, semantic search. The RAG pipeline: ingest → chunk → embed → index → retrieve → augment → generate. | Advanced RAG (DLAI) lessons 1-4 (sentence window, auto-merging retrieval); AI Engineering (Huyen) ch. 8 (RAG architecture) | Build a RAG pipeline from scratch (embedding model + vector store + retrieval + LLM generation). Index a corpus of 20+ documents. Implement evaluation: precision@k, recall@k, and LLM-as-judge for answer quality. Test with 15 queries. |
| 1 | The orchestrator-worker pattern. Task decomposition — what can be parallelized? The artifact pattern: subagents write to filesystem, return lightweight references. The 'game of telephone' problem. | Anthropic Multi-Agent System full; Cognition: Don't Build Multi-Agents full | Design (on paper first) a multi-agent architecture for a research task: orchestrator decomposes a complex question → dispatches to 2-3 parallel subagents (each with different tools) → subagents write findings to files → orchestrator synthesizes. Write an architecture decision record: why multi-agent for this task? What's the cost (estimated tokens)? |
| 1 | Code-as-action-space: why executing code beats JSON tool-calling for complex tasks. Sandboxing (E2B, Docker). The Agent-Computer Interface: windowed file viewing, edit-with-linting, informative error feedback. | SWE-agent sec. 1-4 (intro, ACI design, experiments); Building Code Agents (DLAI) lessons 1-3 | Build a code-execution agent in a sandbox (E2B or Docker): the agent writes Python code, executes it, reads stdout/stderr, and iterates. Task: the agent must write a script that fetches data from an API, processes it, and produces a chart — all in the sandbox. Include error recovery for syntax errors and runtime exceptions. |
| 1 | Eval design for agents: end-state evaluation (not turn-by-turn), LLM-as-judge + human review, held-out test sets, metrics that matter (not just accuracy). Error analysis: isolate the weakest component. | Anthropic Eval Guidance full | Build an eval harness for your agent: ≥20 held-out test cases, end-state assertions, LLM-as-judge scoring, and a written error analysis identifying the top 3 failure modes with concrete examples. Run the full eval, produce a score, and identify which component (tool selection? reasoning? execution?) causes the most failures. |
| 1 | Production reliability: checkpointing, retry logic, rainbow/canary deployments, cost optimization (cached vs uncached, model selection, token budgeting). Safety: guardrails, human-in-the-loop, confidence metrics, prompt injection defense. The 'lethal trifecta.' | AI Engineering (Huyen) ch. 13-15; Anthropic Guardrails full | Production-readiness audit of your agent system: assess and document (a) reliability — what fails and how it recovers, (b) safety — what guardrails exist and what's missing, (c) cost — token budget analysis and optimization opportunities, (d) deployment plan — how you'd ship this to real users. Address at least 3 concrete improvements. |
| 2 | Async I/O, HTTP clients (httpx/aiohttp), error handling patterns, logging, environment management (venv/uv), debugging with pdb. | AI Python for Beginners (DeepLearning.AI) Lessons 3-4 | An async script that makes 3+ concurrent API calls, handles timeouts/retries, logs each step, and writes structured results to a JSON file. |
| 2 | Attention — query, key, value, scaled dot-product, multi-head attention, causal masking. The core mechanism that makes transformers work. | 3Blue1Brown: Attention in transformers, visually explained full video (26 min); SLP3 ch. 9 sec. 9.1-9.4 (self-attention, multi-head, transformer blocks) | Implement multi-head self-attention from scratch (NumPy/PyTorch) on a small sequence. Trace Q, K, V through the computation and explain at the tensor level. |
| 2 | Multi-tool agents: parallel tool calls, sequential tool chains, tool selection ambiguity. Error recovery: retry, fallback, escalation. Tool result formatting — what the LLM needs vs what the tool returns. | Anthropic: Building Effective Agents augmented LLM + workflow patterns sections | Extend the agent to 3+ tools with potential overlap (e.g., a 'research assistant' with search, fetch-page, and summarize tools). Add error recovery: if a tool fails, the agent should retry once, then try an alternative tool, then report the failure honestly. Test with 10 queries designed to trigger edge cases. |
| 2 | Planning: Plan-and-Execute pattern. The plan as structured output. Replanning on failure. Tree-of-Thought mental model. | ReAct (Yao et al.) sec. 4-5 (results, analysis, related work) | Add planning to your ReAct agent: before acting, the agent outputs a 3-5 step plan as structured JSON. If a step fails, it replans. Compare plan-ahead vs reactive ReAct on the same 10 eval cases — which performs better, and on what kind of tasks? |
| 2 | Externalized memory: file system as context, restorable compression (drop content, keep reference), append-only context, todo.md for attention manipulation. Anthropic's artifact pattern. | Manus Context Engineering Principles 4-6 (keep wrong turns, attention manipulation, avoid few-shot trap); Anthropic Context Engineering full | Add file-system-as-context to your agent: (a) agent writes intermediate results to files, (b) drops full content but keeps file references in context, (c) uses a todo.md for planning state. Compare context usage before/after: how much did you save? |
| 2 | Advanced retrieval: hybrid search, reranking, contextual retrieval, query rewriting. Agentic RAG — the agent decides when and what to retrieve, not a fixed pipeline. | Advanced RAG (DLAI) lessons 5-8 (evaluation, advanced techniques); Anthropic Contextual Retrieval full | Add RAG as a tool to your agent: the agent can call `search_docs(query)` and `fetch_doc(id)` to ground its answers in the indexed corpus. Add citation: every claim from a document must cite the source. Test with 10 questions that require cross-document synthesis. |
| 2 | Implementing the orchestrator-worker. Context isolation strategies. The single-vs-multi debate resolved: multi-agent wins when tasks are parallelizable, independent, and breadth-first; single-agent/deterministic wins for tightly coupled work. | Cognition: Multi-Agents — What's Actually Working full | Build a working multi-agent system with ≥2 workers, artifact-passing (file system), and a synthesizer. Test on 5 complex multi-faceted questions. Write a quantitative comparison: single-agent vs multi-agent on the same tasks — which performs better, and at what token cost? |
| 2 | Computer-use agents: screenshot → mouse/keyboard action → observe loop. OSWorld and WebArena benchmarks. The broader CodeAct paradigm — any action expressible as code. | OpenHands Architecture full architecture docs; Anthropic Computer Use full | Study the OpenHands source code. Write a 1-page architectural analysis: how does OpenHands structure its controller-agent-runtime? What does the ACI look like? If you were redesigning one component, which would it be and why? Bonus: extend your code-execution agent to handle multi-step programming tasks (write → test → debug → fix). |
| 2 | Observability: full-session trace capture, OpenTelemetry/OpenInference, metric dashboards. Debugging multi-step failures: trace → isolate → fix → re-eval. The observability-driven development loop. | Langfuse Docs tracing + evaluation | Instrument your agent with Langfuse (or Arize Phoenix): capture full traces for every run, including LLM calls, tool calls, tool results, and errors. Run 10 tasks and produce a dashboard or report showing: avg tokens/task, avg tool calls/task, tool error rate, latency per step, and the most common failure pattern. Fix the #1 failure pattern and show the before/after eval score. |
| 2 | Capstone: ship a portfolio-grade agent system. Synthesize everything: ReAct loop, tools, context engineering, RAG (or multi-agent, or code-execution), eval harness, observability. Architecture decision record. The Bitter Lesson and the frontier — where agent engineering is heading. | Berkeley Advanced LLM Agents frontier + safety lectures | **Capstone:** a portfolio-grade agent system that demonstrates mastery of at least 3 of: code execution, RAG, multi-agent orchestration, context engineering, computer use. Requirements: shipped and usable, full observability (Langfuse/Arize traces), eval harness with ≥20 cases, architecture decision record explaining each choice with quantitative reasoning. Plus: a 2-page paper reading the frontier — pick 2 recent agent papers from COLM/NeurIPS/ICLR, summarize, and connect to your system's architecture. |
| 3 | Full transformer — encoder-decoder vs decoder-only, layer norm, residual connections, feed-forward, positional encoding. What happens during inference vs training. | Karpathy: Let's build GPT from scratch remainder (60 min → end, GPT implementation); SLP3 ch. 9 sec. 9.5-9.8 (full architecture), ch. 10 (pretraining) | Complete a working tiny GPT that can generate text. Explain: what happens step-by-step during a single forward pass of inference. Why decoder-only for modern LLMs? |
| 3 | Reflection: self-critique, verbal reinforcement, learning from failures. The Reflexion pattern. Compare ReAct vs ReAct+Reflection. | Reflexion (Shinn et al.) full; Agentic AI (DLAI) reflection lesson (deep dive) | Add reflection to your agent: after completing a task, the agent self-critiques (what went wrong, what it would do differently) and stores the reflection for future runs. Run a 3-task sequence where the agent improves from task 1 → task 3 using its own reflections. Write a 1-page analysis: when does reflection help? When does it hurt (overthinking)? |

## Units, outcomes & proofs

### Sem 1 · Weeks 1–2 · Python for AI Engineering
_Build the Python toolkit agents need: API calls, JSON handling, async I/O, data structures for LLM pipelines, environment management, and debugging._
- **apply** — Write async Python scripts that call REST APIs, parse structured JSON responses, handle errors (timeout/retry/fallback), and log execution — all without a framework.
  - *proof:* Async Python script that calls 3+ APIs, handles errors, logs execution, and writes structured output. Must run without errors and pass 5 test cases.
- *readings:*
  - **AI Python for Beginners (DeepLearning.AI)** — all 4 lessons _(course)_ — https://www.deeplearning.ai/short-courses/ai-python-for-beginners/  · _Fastest path to the specific Python (data handling, APIs, async) that agents need — agent-oriented from day one._
  - **Python Crash Course (3rd ed.)** · Eric Matthes — ch. 1-11, 15-17 (APIs), 18-20 (Django intro — skip, just read API patterns) _(textbook, paid)_  · _Solid Python foundations if the learner needs more depth than the DLAI course._

### Sem 1 · Weeks 3–5 · LLM Fundamentals — Transformers, Attention, Tokenization
_Build deep understanding of what agents run on: the transformer architecture, attention mechanism, tokenization, pretraining, and inference. Implement a tiny transformer from scratch._
- **apply** — Implement a minimal transformer (multi-head attention + feed-forward + layer norm) and explain attention computation, tokenization, and the inference forward pass from first principles.
  - *proof:* Working minimal transformer implementation (attention + FFN + layer norm) with a written explanation of attention computation, tokenization, and inference forward pass from first principles.
- *readings:*
  - **Neural Networks: Zero to Hero (Andrej Karpathy)** — Lectures 1-7 (micrograd → GPT from scratch) _(video)_ — https://www.youtube.com/playlist?list=PLAqhIrjkxrVzNBzVO2E4PcbWQyZJ4hR9h  · _Builds GPT from scratch — unmatched intuition for what happens inside the model agents call._
  - **3Blue1Brown: Transformers & Attention** — full series _(video)_ — https://www.youtube.com/watch?v=eMlx5fFNoYc  · _Visual intuition for attention, query/key/value, and multi-head attention — the 'aha' moment._
  - **Speech and Language Processing (3rd ed.)** · Jurafsky & Martin — ch. 9 (transformers), ch. 10 (pretraining & fine-tuning), ch. 11 (prompting & in-context learning) _(textbook)_ — https://web.stanford.edu/~jurafsky/slp3/  · _The authoritative technical reference — read alongside Karpathy for theory + implementation._
  - **Hands-On Large Language Models** · Alammar & Grootendorst — ch. 1-4 (tokenization → attention → transformers) _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Code-first, visual companion — implement as you read._

### Sem 1 · Week 6 · Prompt Engineering — Programming in Natural Language
_Master prompt engineering as structured programming: system messages, few-shot selection, chain-of-thought, output format constraints, and prompt architecture patterns._
- **evaluate** — Design, test, and iteratively improve prompts using system messages, few-shot examples, chain-of-thought, and structured output specifications. Score and explain which technique improves which failure mode.
  - *proof:* 5 escalating prompts for the same task, each scored against a 10-example test set, with written explanation of why each technique improved which failure mode.
- *readings:*
  - **Anthropic Prompt Engineering Guide** — full guide (overview → be clear and direct → use examples → chain of thought → system prompts) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Vendor-authoritative, research-backed, continuously updated — the primary reference._
  - **ChatGPT Prompt Engineering for Developers (DeepLearning.AI)** — all lessons _(course)_ — https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/  · _Hands-on with the patterns: iterative refinement, summarizing, inferring, transforming, expanding._
  - **Prompting Guide (DAIR.AI)** — techniques section (zero-shot, few-shot, CoT, self-consistency, ReAct) _(reference)_ — https://www.promptingguide.ai/  · _Comprehensive catalog of prompting techniques with research paper citations._

### Sem 1 · Week 7 · Structured Output & Function Calling
_Move from free-text parsing to reliable machine-readable contracts: JSON mode, function/tool calling schemas, response_format, and the API contract pattern._
- **apply** — Design a tool/function schema and build a pipeline that sends a prompt, receives structured JSON output, validates it, and handles schema violations gracefully.
  - *proof:* Smart form filler that extracts structured JSON from natural language, with schema validation, error handling for missing/ambiguous fields, and ≥80% accuracy on 10 test inputs.
- *readings:*
  - **OpenAI Structured Outputs / Function Calling** — full guide (structured outputs + function calling) _(docs)_ — https://platform.openai.com/docs/guides/structured-outputs  · _The canonical API spec — understand the contract before abstracting it._
  - **Anthropic Tool Use Guide** — full guide (overview → defining tools → tool use workflow → best practices) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use  · _Anthropic's tool-use paradigm — the other major API contract._

### Sem 1 · Weeks 8–9 · Tool-Use Architectures
_The LLM as decision-maker: how agents decide which tool to call, generate arguments, process results, and recover from tool failures. Build directly against APIs — no framework._
- **apply** — Build a multi-tool agent from scratch (raw API calls, no framework) that selects the right tool, handles errors with retry/fallback/escalation, and produces reliable results.
  - *proof:* Multi-tool agent (3+ tools, raw API calls, no framework) with retry/fallback/escalation error recovery, tested on 10 edge-case queries with ≥80% correct tool selection.
- *readings:*
  - **Anthropic: Writing Effective Tools for AI Agents** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use/best-practices  · _Eval-driven tool design principles from the team defining the field._
  - **Anthropic: Building Effective Agents** — full (especially the augmenting LLMs and workflow patterns sections) _(reference)_ — https://docs.anthropic.com/en/docs/build-with-claude/agent-patterns  · _The five agentic patterns and when to use each. Read before building anything._

### Sem 1 · Weeks 10–12 · Agent Loops — ReAct, Planning & Reflection
_The core agent control flow: ReAct (Reason + Act), Plan-and-Execute, and Reflection. Build a full ReAct agent from scratch (~400 lines), then add planning and self-critique. Read the papers._
- **create** — Build a complete ReAct agent from scratch (no framework, ~400+ lines) with planning and reflection capabilities. Ship it with a 10+ case eval harness, error analysis, and a self-explanation of the loop architecture citing the ReAct paper.
  - *proof:* Working ReAct agent from scratch (~400 lines, no framework) with ≥3 real tools, ≥10 eval cases, error analysis, and self-explanation of the loop architecture.
- *readings:*
  - **ReAct: Synergizing Reasoning and Acting in Language Models (Yao et al., ICLR 2023)** — full paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent-loop paper — the pattern every agent inherits from._
  - **Reflexion: Language Agents with Verbal Reinforcement Learning (Shinn et al.)** — full paper _(paper)_ — https://arxiv.org/abs/2303.11366  · _The reflection/self-improvement pattern — agents that learn from their own failures._
  - **DeepLearning.AI: Agentic AI (Andrew Ng)** — all lessons (reflection, tool use, planning, multi-agent patterns) _(course)_ — https://www.deeplearning.ai/short-courses/agentic-ai/  · _Practical treatment of four design patterns with eval woven throughout._
  - **Hugging Face Agents Course** — Units 0-2 (intro → smolagents → tools & agents) _(course)_ — https://huggingface.co/learn/agents-course  · _Hands-on with a framework AFTER building from scratch — learn what frameworks abstract._

### Sem 2 · Weeks 1–2 · Memory & Context Engineering
_The frontier discipline: KV-cache economics, context compaction, externalized memory (file system as context), preserving failures, and the 'lost in the middle' problem. Study Manus and Anthropic's approaches._
- **evaluate** — Instrument an agent for context efficiency, measure KV-cache hit rate and token usage, and implement at least two context-engineering techniques (file-system-as-context, compaction, or append-only context) with measured improvement.
  - *proof:* Instrumented agent with context-efficiency metrics (KV-cache hit rate, token usage), at least 2 context-engineering techniques implemented, and a measured improvement report.
- *readings:*
  - **Manus: Context Engineering for AI Agents (Peak Ji, July 2025)** — full — all six principles _(reference)_ — https://manus.im/blog/context-engineering  · _The single best primary source on production context engineering at scale. KV-cache hit rate as the #1 metric._
  - **Anthropic: Effective Context Engineering for AI Agents** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/context-engineering  · _Anthropic's treatment of context management — the other half of the frontier picture._
  - **LLMs Get Lost in Multi-Turn Conversation (Laban, Hayashi et al., arXiv:2505.06120)** — full _(paper)_ — https://arxiv.org/abs/2505.06120  · _Quantifies context rot: 39% average drop single-turn → multi-turn. This is WHY context engineering matters._

### Sem 2 · Weeks 3–4 · Retrieval-Augmented Generation
_Ground agents in external knowledge: embedding, vector search, chunking strategies, reranking, hybrid search, and the full RAG pipeline. Build a RAG-powered agent that retrieves and cites sources._
- **apply** — Build a RAG pipeline (embed → index → retrieve → augment → generate) and integrate it as a tool into an agent that retrieves, cites, and synthesizes across documents.
  - *proof:* RAG pipeline with embedding, vector store, retrieval, and citation. Integrated as agent tool. ≥80% answer quality on 15 queries with precision@k and recall@k reported.
- *readings:*
  - **DeepLearning.AI: Building and Evaluating Advanced RAG** — all lessons _(course)_ — https://www.deeplearning.ai/short-courses/advanced-retrieval-for-ai/  · _Production-grade RAG coverage from architecture to eval — the DLAI RAG series is the best hands-on path._
  - **AI Engineering (Chip Huyen)** — ch. 8-9 (RAG architecture, chunking, embedding, retrieval, reranking, evaluation) _(textbook, paid)_  · _Engineering-first treatment: how to choose chunk size, when to rerank, how to eval retrieval quality._
  - **Anthropic: Contextual Retrieval** — full post _(docs)_ — https://www.anthropic.com/news/contextual-retrieval  · _Contextual retrieval — enriching chunks with document context before embedding — a technique that significantly improves retrieval quality._
  - **Hugging Face Agents Course: Agentic RAG Unit** — Agentic RAG unit _(course)_ — https://huggingface.co/learn/agents-course  · _RAG specifically in the agent context — when the agent decides what and when to retrieve._

### Sem 2 · Weeks 5–6 · Multi-Agent Systems & Orchestration
_When and how to use multiple agents: orchestrator-worker, parallel subagents, artifact-passing, and the single-vs-multi-agent debate. Study Anthropic and Cognition's opposing architectures._
- **create** — Design and build a multi-agent system with ≥2 workers, artifact-passing, and a synthesizer. Write an architecture decision record comparing single-agent vs multi-agent with quantitative reasoning about cost, latency, and reliability.
  - *proof:* Working multi-agent system with ≥2 workers, artifact-passing (file system or message bus), ≥10 eval cases, and a written architecture decision record comparing single-agent vs multi-agent with quantitative reasoning.
- *readings:*
  - **Anthropic: How We Built Our Multi-Agent Research System** — full _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _The definitive multi-agent case study: orchestrator-worker, 90.2% improvement, artifact pattern, rainbow deployments._
  - **Cognition: Don't Build Multi-Agents (June 2025)** — full _(reference)_ — https://cognition.ai/blog/dont-build-multi-agents  · _The counter-argument: context engineering over parallelism, single coherent context is more reliable._
  - **Cognition: Multi-Agents — What's Actually Working** — full _(reference)_ — https://cognition.ai/blog/multi-agents-whats-working  · _When multi-agent DOES work: read-only subagents, manager-devin delegation, deliberate context isolation._
  - **UC Berkeley LLM Agents MOOC** — Multi-agent systems lecture (Dawn Song) _(course)_ — https://llmagents-learning.org/  · _Academic framing of the multi-agent design space._

### Sem 2 · Weeks 7–8 · Code Execution & Computer-Use Agents
_Agents that act by writing and executing code: the CodeAct paradigm, sandboxed execution, Agent-Computer Interface (ACI), and computer-use/GUI agents. Study SWE-agent and OpenHands._
- **analyze** — Build a code-execution agent in a sandbox that writes, runs, and iterates on code, and analyze a production code-agent architecture (OpenHands or SWE-agent) with specific, cited observations.
  - *proof:* Code-execution agent in sandbox that writes, runs, and iterates on code with error recovery. Plus a 1-page architectural analysis of OpenHands or SWE-agent with specific code-level observations.
- *readings:*
  - **SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering (Yang et al., NeurIPS 2024)** — full _(paper)_ — https://arxiv.org/abs/2405.15793  · _Introduced the ACI concept — the most-imitated idea in coding agents: agents need purpose-built interfaces, not human UIs._
  - **OpenHands (formerly OpenDevin): CodeAct Architecture** — README + docs/architecture _(reference)_ — https://github.com/All-Hands-AI/OpenHands  · _CodeAct 2.1 reached SOTA open-source SWE-bench Verified (~53%); study the controller-agent-runtime architecture._
  - **DeepLearning.AI: Building Code Agents with Hugging Face smolagents (Wolf & Roucher)** — all lessons _(course)_ — https://www.deeplearning.ai/short-courses/building-code-agents/  · _Hands-on sandboxed code execution using E2B — practical intro to the paradigm._
  - **Anthropic Computer Use Documentation** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/computer-use  · _The reference implementation for computer-use/GUI agents — screenshot → action → observe loop._

### Sem 2 · Weeks 9–10 · Evaluation, Observability & Debugging
_The #1 differentiator: building eval harnesses that catch cascading errors, instrumenting agents for full-session trace capture, and debugging multi-step failures with data, not guesswork._
- **evaluate** — Build a complete eval harness (≥20 held-out cases, LLM-as-judge, error analysis), instrument an agent with full-session observability, and demonstrate a measurable improvement from diagnosis to fix.
  - *proof:* Complete eval harness (≥20 held-out cases, LLM-as-judge, error analysis), full-session observability traces, and a measurable before/after improvement from diagnosis to fix.
- *readings:*
  - **Anthropic: Evaluation Guidance for AI Agents** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/evaluate  · _End-state evaluation, LLM-as-judge, human review, held-out test sets — from the team that built it._
  - **Hamel Husain: Evals Writing & Error Analysis** — eval-related posts _(reference)_ — https://hamel.dev/  · _The practitioner's voice on eval design — practical, opinionated, battle-tested._
  - **Langfuse Documentation** — tracing + evaluation sections _(docs)_ — https://langfuse.com/docs  · _Leading open-source observability platform — instrument and trace multi-step agent runs._
  - **Arize Phoenix Documentation** — tracing + evals _(docs)_ — https://docs.arize.com/phoenix  · _OpenTelemetry-native, open-source, 50+ eval metrics — framework-agnostic alternative._

### Sem 2 · Weeks 11–12 · Production, Safety & Frontier Architecture
_Ship a portfolio-grade agent system. Study production reliability patterns, safety/guardrails, cost optimization, and the frontier — where agent engineering is heading and how to stay ahead._
- **create** — Ship a portfolio-grade agent system with full observability, eval harness, and an architecture decision record. Demonstrate the ability to read and critique frontier research and connect it to practice.
  - *proof:* Portfolio-grade agent system: shipped, observable, eval-harnessed, with an architecture decision record. Must demonstrate at least 3 of: code execution, RAG, multi-agent, context engineering, computer use.
- *readings:*
  - **Cognition, Anthropic, Manus, Fin — all primary architecture sources from the course** — synthesis across all studied systems _(reference)_ — various  · _Now is when all the architecture study across the course synthesizes into your own judgment._
  - **AI Engineering (Chip Huyen)** — ch. 13-15 (deployment, monitoring, scaling, cost optimization) _(textbook, paid)_  · _Production deployment pragmatics — what actually matters when people rely on your system._
  - **UC Berkeley: Advanced LLM Agents (Spring 2025)** — safety lectures (Dawn Song), post-training lectures, frontier guest lectures _(course)_ — https://rdi.berkeley.edu/advanced-agentic-ai/  · _The research frontier — safety, multi-turn RL, and what's coming next._
  - **Anthropic: Guardrails & Safety** — full _(reference)_ — https://docs.anthropic.com/en/docs/build-with-claude/guardrails  · _Production guardrail patterns: keep a human in the loop for high-stakes decisions, confidence assessment, escalation._

## Course library
- **AI Engineering** · Chip Huyen — whole (evals ch. 5-7, RAG ch. 8-9, agents ch. 10-12, deployment ch. 13-15) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166309/  · _The practitioner's textbook for building LLM applications end-to-end — bridges theory to production._
- **Hands-On Large Language Models** · Jay Alammar & Maarten Grootendorst — whole _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Visual, code-first companion — builds transformer/attention intuition through implementation._
- **UC Berkeley CS294/194-196: Large Language Model Agents** · Dawn Song, Xinyun Chen — Lectures 1-14 (full MOOC) _(course)_ — https://llmagents-learning.org/  · _The definitive academic agent course — guest lectures from the researchers who defined the field._
- **Stanford CS336: Language Modeling from Scratch** · Percy Liang, et al. — Lectures 1-10 _(course)_ — https://cs336.stanford.edu/  · _Build an LLM end-to-end — deepest possible foundation for understanding what agents run on._

## Assessment plan
- **a.u6.build** (summative, open_problem, ≥create) — Working ReAct agent from scratch (~400 lines, no framework) with ≥3 real tools, ≥10 eval cases, error analysis, and self-explanation of the loop architecture.
- **a.u9.design** (summative, open_problem, ≥create) — Working multi-agent system with ≥2 workers, artifact-passing (file system or message bus), ≥10 eval cases, and a written architecture decision record comparing single-agent vs multi-agent with quantitative reasoning.
- **a.u12.capstone** (summative, project, ≥create) — Portfolio-grade agent system: shipped, observable, eval-harnessed, with an architecture decision record. Must demonstrate at least 3 of: code execution, RAG, multi-agent, context engineering, computer use.
- **a.u1.python-tools** (summative, worked-completion, ≥apply) — Async Python script that calls 3+ APIs, handles errors, logs execution, and writes structured output. Must run without errors and pass 5 test cases.
- **a.u2.transformer** (summative, open_problem, ≥apply) — Working minimal transformer implementation (attention + FFN + layer norm) with a written explanation of attention computation, tokenization, and inference forward pass from first principles.
- **a.u3.prompt** (summative, open_problem, ≥evaluate) — 5 escalating prompts for the same task, each scored against a 10-example test set, with written explanation of why each technique improved which failure mode.
- **a.u4.structured** (summative, open_problem, ≥apply) — Smart form filler that extracts structured JSON from natural language, with schema validation, error handling for missing/ambiguous fields, and ≥80% accuracy on 10 test inputs.
- **a.u5.tools** (summative, open_problem, ≥apply) — Multi-tool agent (3+ tools, raw API calls, no framework) with retry/fallback/escalation error recovery, tested on 10 edge-case queries with ≥80% correct tool selection.
- **a.u7.context** (summative, open_problem, ≥evaluate) — Instrumented agent with context-efficiency metrics (KV-cache hit rate, token usage), at least 2 context-engineering techniques implemented, and a measured improvement report.
- **a.u8.rag** (summative, open_problem, ≥apply) — RAG pipeline with embedding, vector store, retrieval, and citation. Integrated as agent tool. ≥80% answer quality on 15 queries with precision@k and recall@k reported.
- **a.u10.code-agent** (summative, open_problem, ≥analyze) — Code-execution agent in sandbox that writes, runs, and iterates on code with error recovery. Plus a 1-page architectural analysis of OpenHands or SWE-agent with specific code-level observations.
- **a.u11.eval** (summative, open_problem, ≥evaluate) — Complete eval harness (≥20 held-out cases, LLM-as-judge, error analysis), full-session observability traces, and a measurable before/after improvement from diagnosis to fix.
