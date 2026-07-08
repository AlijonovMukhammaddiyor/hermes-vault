# AG201 — AI Agent Engineering

> Design, build, evaluate, and deploy production-grade AI agent systems — from a single ReAct loop to multi-agent orchestrations — with the architectural judgment of a staff-level engineer.

From scratch to frontier: a 24-week, two-semester course that builds every layer of AI agent engineering. Starts with Python and LLM fundamentals (transformers, attention, prompting), then constructs the full agent stack layer by layer — structured output, tool use, agent loops, context engineering, RAG, multi-agent orchestration, code-execution agents, and production deployment. Evaluation and observability are threaded throughout, not deferred. Grounded in primary research (Anthropic, Cognition, Manus, Berkeley LLM Agents MOOC) and anchored by Jurafsky & Martin SLP3 plus Chip Huyen's AI Engineering. Graduates ship a portfolio-grade agent system and can defend architecture choices with quantitative reasoning about cost, latency, and reliability.

**Credits:** 4  ·  **Domain:** ai-engineering  ·  **Prereqs:** none

## Who this course is for
- Comfortable with Python basics (functions, dicts, list comprehensions) and eager to go deep — this course builds the agent stack from the metal up. You want to understand WHY, not just wire frameworks.
- You have 3h/day to commit and are willing to implement things from scratch before reaching for abstractions. The bar is staff-level engineering thinking.

**Not for — look elsewhere if:**
- Already shipping production agent systems at scale and reading COLM papers weekly — you may want a more targeted deep-dive (e.g., the Berkeley Advanced LLM Agents MOOC directly).
- Looking for a framework-wiring tutorial (LangChain/CrewAI quickstart). This course builds from first principles — you'll use frameworks later, but only after you can rebuild them.
- No Python experience at all — start with DeepLearning.AI's 'AI Python for Beginners' first, then come back.

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

## Assessment & grading
**Assignments (take-home)** 40% · **Quizzes** 15% · **Unit exams** 15% · **Midterm** 10% · **Finals** 20%

How it works: every week ships a **take-home assignment** (the deliverable in the plan below). Each unit closes with a **quiz**; there's a **midterm** at the semester mid-point and **finals** in the last week. Every graded item maps to an outcome and is scored against its rubric — no grade without a proof.

## Week-by-week plan

| Week | Focus | Readings | Assignment (take-home) | Assessment |
|---|---|---|---|---|
| S1 W1 | Python environment, data structures, functions, type hints, list/dict comprehensions — the patterns agents use to process LLM output. | AI Python for Beginners (DeepLearning.AI) Lessons 1-2 | A Python script that calls a REST API (e.g., OpenWeatherMap), parses JSON, handles errors, and prints a formatted summary. | — |
| S1 W2 | Async I/O, HTTP clients (httpx/aiohttp), error handling patterns, logging, environment management (venv/uv), debugging with pdb. | AI Python for Beginners (DeepLearning.AI) Lessons 3-4 | An async script that makes 3+ concurrent API calls, handles timeouts/retries, logs each step, and writes structured results to a JSON file. | 📝 Unit quiz |
| S1 W3 | Tokenization — BPE, token vocabulary, special tokens, context windows. What the model actually 'sees' vs what you send. | Karpathy: Let's build GPT from scratch first 60 min (tokenization + bigram baseline); SLP3 ch. 2 sec. 2.5 (tokenization) | Implement a BPE tokenizer from scratch on a small corpus. Explain: why subword tokenization? What happens to out-of-vocabulary words? | — |
| S1 W4 | Attention — query, key, value, scaled dot-product, multi-head attention, causal masking. The core mechanism that makes transformers work. | 3Blue1Brown: Attention in transformers, visually explained full video (26 min); SLP3 ch. 9 sec. 9.1-9.4 (self-attention, multi-head, transformer blocks) | Implement multi-head self-attention from scratch (NumPy/PyTorch) on a small sequence. Trace Q, K, V through the computation and explain at the tensor level. | — |
| S1 W5 | Full transformer — encoder-decoder vs decoder-only, layer norm, residual connections, feed-forward, positional encoding. What happens during inference vs training. | Karpathy: Let's build GPT from scratch remainder (60 min → end, GPT implementation); SLP3 ch. 9 sec. 9.5-9.8 (full architecture), ch. 10 (pretraining) | Complete a working tiny GPT that can generate text. Explain: what happens step-by-step during a single forward pass of inference. Why decoder-only for modern LLMs? | 📝 Unit quiz |
| S1 W6 | System messages, few-shot examples, CoT, output format specification. Prompt as programming — explicit over implicit, constraints over hopes. | Anthropic Prompt Engineering Guide full; ChatGPT Prompt Engineering (DLAI) lessons 1-6 | Write 5 prompts for the same task (e.g., 'classify customer support tickets by urgency and category') with escalating quality: naive → system message → few-shot → CoT → structured JSON output. Score each on accuracy against a 10-example test set. Explain why each improvement moved the needle. | 🎯 Midterm exam |
| S1 W7 | JSON mode, function/tool calling schemas, response_format, API contract pattern. Parsing partial/incomplete JSON from streaming responses. | OpenAI Structured Outputs Guide full; Anthropic Tool Use Guide overview + defining tools sections | Build a 'smart form filler' that takes natural language input (e.g., 'schedule lunch with Sarah next Tuesday at noon') and extracts structured JSON with date, time, attendees, title. Handle missing/ambiguous fields with clarification questions. ≥80% accuracy on 10 test cases. | 📝 Unit quiz |
| S1 W8 | Tool definition — schemas, descriptions, parameter design. Single-tool agents: calling one API, parsing the result, deciding next action. Direct API calls, no framework. | Anthropic Tool Use Guide overview → defining tools → tool use workflow; Hugging Face Agents Course — Unit 1 full | Build a single-tool agent that can search the web (Serper/Brave API) and answer questions with citations. Raw API calls only. | — |
| S1 W9 | Multi-tool agents — tool selection, parallel execution, error recovery. Retry with backoff, fallback to alternative tool, escalate to user. The tool-design principles that matter. | Anthropic: Writing Effective Tools best practices section; ReAct (Yao et al.) full paper | Build an agent with 3+ tools (search, calculator, weather/API) that correctly selects tools, handles tool failures (retry/fallback), and never hallucinates tool results. Test on 10 edge-case queries. | 📝 Unit quiz |
| S1 W10 | The ReAct loop — interleaving reasoning traces and actions. Observation → Thought → Action → Observation cycle. Implementing the loop from scratch (~200 lines). | DeepLearning.AI Agentic AI tool use + planning patterns; SWE-agent sec. 1-3 (intro, ACI design) | Implement a ReAct agent loop from scratch — reason → act → observe → reason — with 2+ tools. Must handle: when to stop, what to do on tool error, how to avoid loops. | — |
| S1 W11 | Reflection and planning — self-critique loops (Reflexion), plan-and-execute vs ReAct, when each pattern wins. The ACI concept: designing interfaces for agents, not humans. | DeepLearning.AI Agentic AI reflection pattern + full review; Hugging Face Agents Course — Unit 2 planning + reflection sections | Extend your ReAct agent with a reflection step — after producing an answer, critique it, then improve. Compare ReAct vs Plan+Execute on 5 tasks. Write: when does reflection actually help? | 📝 Unit quiz |
| S1 W12 | KV-cache economics — prompt prefix stability, append-only context, cached vs uncached cost (10× difference). File system as externalized memory. Masking tool logits. Keeping wrong turns in. Attention through recitation. | Manus: Context Engineering full (all six principles); Anthropic: Effective Context Engineering full | Take your ReAct agent from U6 and instrument it: track token usage per turn, KV-cache hit rate, and context length. Implement 2 context-engineering techniques (e.g., append-only context, file-system offloading of long tool outputs). Measure the improvement. Due: end of Semester 1. | 🏁 Finals |
| S2 W1 | Embeddings, vector stores (ChromaDB/FAISS), chunking strategies, basic retrieval. The naive RAG pipeline. | AI Engineering (Huyen) ch. 8; DeepLearning.AI Advanced RAG chunking + retrieval modules | Build a RAG pipeline: embed a corpus (your choice — docs, codebase, papers), store in a vector DB, retrieve top-k for a query, and generate an answer. Compute precision@k and recall@k. | — |
| S2 W2 | Hybrid search, reranking, citation, agent-integrated RAG. The agent decides WHEN to retrieve. | AI Engineering (Huyen) ch. 9; Hugging Face Agents Course — Agentic RAG full unit | Wire your RAG pipeline as a tool in your agent. The agent decides when retrieval is needed (vs answering from context). Test on 15 queries. ≥80% answer quality with citations. | 📝 Unit quiz |
| S2 W3 | Orchestrator-worker pattern — task decomposition, parallel worker dispatch, artifact-passing via file system. The anthropic research system architecture. | Anthropic: Multi-Agent Research System full; Cognition: Don't Build Multi-Agents full | Design (on paper) a multi-agent architecture for a research task. Decompose into orchestrator + 3 workers. Specify: what each agent sees, how they communicate, and the artifact format. | — |
| S2 W4 | Building it — implementing orchestrator-worker with 2+ workers, artifact-passing, and comparing single-agent vs multi-agent performance. The 'game of telephone' problem. | Cognition: Multi-Agents — What's Actually Working full; DeepLearning.AI Agentic AI multi-agent pattern | Build a working multi-agent system: orchestrator dispatches to 2+ workers, workers pass artifacts (via file system or message bus). Compare single-agent vs multi-agent on the same task. Write an architecture decision record with quantitative reasoning. | 📝 Unit quiz |
| S2 W5 | Code execution in sandboxes — E2B, Docker-based isolation. The code-agent loop: write code → execute → read output → fix errors → re-execute. CodeAct vs JSON tool-calling. | DLAI Building Code Agents full course; CodeAct sec. 1-3 | Build a code-execution agent that writes Python to solve a task, runs it in E2B sandbox, reads the output, and iterates on errors. Test on 3 programming tasks. | — |
| S2 W6 | Study a production code agent — OpenHands architecture deep-dive: controller → agent → sandbox runtime, event stream, AgentHub. SWE-agent ACI design. | OpenHands Architecture full architecture docs + CodeAct agent source | Read OpenHands source (controller, agent loop, sandbox runtime). Write a 1-page architectural analysis identifying 3 specific design decisions and why they matter. | — |
| S2 W7 | Computer-use agents — screenshots as input, click/type/keypress as actions. Browser agents (Playwright). The OSWorld benchmark landscape. | Anthropic Computer Use full guide | Extend your agent with a browser tool (Playwright) — navigate to a URL, extract structured data, fill a form. Handle dynamic pages and errors. | 🎯 Midterm exam |
| S2 W8 | Eval design — end-state vs turn-by-turn, held-out sets, LLM-as-judge, the eval-driven development loop. Build an eval harness for your agent. | Anthropic: Evaluate Your Agent full | Build an eval harness for your agent: ≥20 held-out test cases, end-state assertions, LLM-as-judge scoring. Run it and produce an error analysis identifying the weakest component. | — |
| S2 W9 | Observability — full-session tracing with Langfuse/OpenTelemetry. Track: total runtime, tool calls, token consumption, tool error rates, trajectory quality. Diagnose failures from traces. | Langfuse Docs tracing quickstart + eval features; Hugging Face Agents Course — Unit 4 full unit | Wire your agent with Langfuse tracing. Run 10 tasks, capture full traces. From the traces: identify the single worst-performing component, fix it, and show before/after metrics. | — |
| S2 W10 | Safety, guardrails, and alignment — prompt injection, the lethal trifecta, confidence estimation, human-in-the-loop escalation, content safety filters. | Berkeley Advanced LLM Agents safety/guardrails lectures | Add guardrails to your agent: content safety filter, confidence threshold for escalation, prompt-injection detection. Test with 5 adversarial inputs. Document the guardrail architecture. | 📝 Unit quiz |
| S2 W11 | Production deployment — checkpointing, retry logic, incremental deploys, cost monitoring, multi-model resilience. Study the Fin/Anthropic production patterns. | AI Engineering (Huyen) ch. 13-15; Anthropic: Building Effective Agents production deployment + case studies | Deploy your capstone agent with: checkpointing (can resume from mid-task failure), cost tracking (tokens + latency per task), and a health endpoint. Document the deployment architecture. | — |
| S2 W12 | Capstone completion — architecture decision record, final eval run, demo, and retrospective. | — | Ship your portfolio-grade agent system. Must demonstrate ≥3 of: code execution, RAG, multi-agent, context engineering, computer use. Include: full observability, eval harness, architecture decision record (quantitative reasoning for each choice), and a retrospective of what you'd change. | 🏁 Finals |

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
- **apply** — Design tool-calling schemas and extract structured JSON from LLM outputs with schema validation, handling missing/ambiguous fields gracefully.
  - *proof:* Smart form filler that extracts structured JSON from natural language, with schema validation, error handling for missing/ambiguous fields, and ≥80% accuracy on 10 test inputs.
- *readings:*
  - **OpenAI Structured Outputs / Function Calling** — full guide (structured outputs + function calling) _(docs)_ — https://platform.openai.com/docs/guides/structured-outputs  · _The canonical API spec — understand the contract before abstracting it._
  - **Anthropic Tool Use Guide** — full guide (overview → defining tools → tool use workflow → best practices) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use  · _Anthropic's tool-use paradigm — the other major API contract._

### Sem 1 · Weeks 8–9 · Tool Use — Building Agents That Act
_Move from calling one tool to designing multi-tool agents: tool selection, error recovery (retry/fallback/escalate), parallel tool execution, and the tool-design principles that separate reliable agents from brittle ones._
- **apply** — Build a multi-tool agent (3+ tools, raw API calls, no framework) with retry/fallback/escalation error recovery that correctly selects tools ≥80% of the time on edge-case queries.
  - *proof:* Multi-tool agent (3+ tools, raw API calls, no framework) with retry/fallback/escalation error recovery, tested on 10 edge-case queries with ≥80% correct tool selection.
- *readings:*
  - **Anthropic: Writing Effective Tools for AI Agents** — full guide, especially best practices section _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use  · _The primary reference for tool-design principles — written by the team defining the field._
  - **Hugging Face Agents Course — Unit 1: Introduction to Agents** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit1  · _Hands-on with smolagents: tool definition, agent initialization, first agent run._
  - **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. (ICLR 2023) — full paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational paper — read the primary source that defined the pattern._

### Sem 1 · Weeks 10–11 · Agent Loops — ReAct, Reflection & Planning
_Build the core agent loop. Implement ReAct (Reason+Act) from scratch, then layer on reflection (self-critique + improvement) and planning (decompose → execute → verify). Study the SWE-agent ACI insight._
- **create** — Build a working ReAct agent from scratch (~400 lines, no framework) with ≥3 real tools, reflection capability, and ≥10 eval cases. Explain the loop architecture and the ACI design principle.
  - *proof:* Working ReAct agent from scratch (~400 lines, no framework) with ≥3 real tools, ≥10 eval cases, error analysis, and self-explanation of the loop architecture.
- *readings:*
  - **DeepLearning.AI: Agentic AI (Andrew Ng)** — full course (4 design patterns: reflection, tool use, planning, multi-agent) _(course)_ — https://www.deeplearning.ai/short-courses/agentic-ai/  · _Practical treatment of the four patterns with heavy eval emphasis — the canonical practitioner course._
  - **SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering** · Yang, Jimenez, Wettig, Lieret, Yao, Narasimhan, Press (NeurIPS 2024) — full paper — focus on ACI design (sec. 3) _(paper)_ — https://arxiv.org/abs/2405.15793  · _The ACI insight: LM agents need purpose-built interfaces. The most-imitated idea in coding agents._
  - **Hugging Face Agents Course — Unit 2: Agentic Patterns** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit2  · _Hands-on: tool use → planning → reflection patterns with smolagents._

### Sem 1 · Week 12 · Context Engineering & Memory
_Master the discipline that separates production agents from demos: KV-cache economics, context compaction, externalized memory (file system as context), and preserving failure traces._
- **evaluate** — Instrument an agent with context-efficiency metrics and implement at least 2 context-engineering techniques with a measured before/after improvement report.
  - *proof:* Instrumented agent with context-efficiency metrics (KV-cache hit rate, token usage), at least 2 context-engineering techniques implemented, and a measured improvement report.
- *readings:*
  - **Manus: Context Engineering for AI Agents — Lessons from Building Manus** · Yichao 'Peak' Ji — full article (six principles) _(reference)_ — https://manus.im/blog/context-engineering  · _The six principles from a production agent at scale (~50 tool calls/task avg). KV-cache hit rate as the single most important metric._
  - **Anthropic: Effective Context Engineering for AI Agents** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/context-window  · _The complementary practitioner treatment from the other major lab._
  - **LLMs Get Lost in Multi-Turn Conversation** · Laban, Hayashi et al. — abstract + results (sec. 3-4) _(paper)_ — https://arxiv.org/abs/2505.06120  · _Quantified context rot: 39% drop single-turn → multi-turn across 15 models. The empirical case for context engineering._

### Sem 2 · Weeks 1–2 · RAG — Retrieval-Augmented Generation
_Build the retrieval backbone that grounds agents in real data: embeddings, vector stores, chunking strategies, hybrid search, reranking, and citation. Integrate RAG as an agent tool._
- **apply** — Build a RAG pipeline with embedding, vector store, retrieval, and citation. Integrate as an agent tool. ≥80% answer quality on 15 queries with precision@k and recall@k reported.
  - *proof:* RAG pipeline with embedding, vector store, retrieval, and citation. Integrated as agent tool. ≥80% answer quality on 15 queries with precision@k and recall@k reported.
- *readings:*
  - **DeepLearning.AI: Building and Evaluating Advanced RAG** — full course _(course)_ — https://www.deeplearning.ai/short-courses/  · _Production-grade RAG from chunking to eval — the practitioner's guide._
  - **AI Engineering** · Chip Huyen — ch. 8-9 (RAG architecture, chunking, retrieval, reranking) _(textbook, paid)_  · _The engineering textbook treatment — architecture decisions and trade-offs._
  - **Hugging Face Agents Course — Agentic RAG Unit** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit3  · _RAG integrated as an agent tool — retrieval-augmented agent behavior._

### Sem 2 · Weeks 3–4 · Multi-Agent Orchestration
_Design and build multi-agent systems. Study both sides of the debate (Anthropic orchestrator-worker vs Cognition single-agent). Learn artifact-passing, delegation patterns, and when NOT to use multi-agent._
- **create** — Design and build a multi-agent system with ≥2 workers, artifact-passing, and a written ADR comparing single-agent vs multi-agent with quantitative reasoning about cost, latency, and reliability.
  - *proof:* Working multi-agent system with ≥2 workers, artifact-passing (file system or message bus), ≥10 eval cases, and a written architecture decision record comparing single-agent vs multi-agent with quantitative reasoning.
- *readings:*
  - **Anthropic: How We Built Our Multi-Agent Research System** — full article _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _The defining multi-agent reference: orchestrator-worker, artifact pattern, rainbow deployments._
  - **Cognition: Don't Build Multi-Agents** — full article _(reference)_ — https://cognition.ai/blog/dont-build-multi-agents  · _The counter-argument: single context is more reliable for tightly coupled work. Read both sides._
  - **Cognition: Multi-Agents — What's Actually Working** — full article _(reference)_ — https://cognition.ai/blog/multi-agents-whats-working  · _Read-only subagents, MCP delegation, deliberate context isolation — the nuanced middle ground._
  - **DeepLearning.AI Agentic AI** — multi-agent pattern _(course)_  · _Andrew Ng's practical treatment of the pattern._

### Sem 2 · Weeks 5–7 · Code-Execution & Computer-Use Agents
_Build agents that write, run, and iterate on code in sandboxes. Study the CodeAct paradigm, study OpenHands/SWE-agent source, and explore computer-use agents (GUI, browser)._
- **analyze** — Build a code-execution agent in a sandbox that writes, runs, and iterates on code with error recovery. Write a 1-page architectural analysis of OpenHands or SWE-agent identifying specific code-level design decisions.
  - *proof:* Code-execution agent in sandbox that writes, runs, and iterates on code with error recovery. Plus a 1-page architectural analysis of OpenHands or SWE-agent with specific code-level observations.
- *readings:*
  - **CodeAct: Executable Code as a Unified Action Space** · Wang et al. — full paper _(paper)_ — https://arxiv.org/abs/2402.01030  · _The paradigm: code as action space — increasingly outperforms JSON tool-calling._
  - **OpenHands (formerly OpenDevin) — Architecture & CodeAct Agent** — architecture docs + CodeAct agent source _(reference)_ — https://github.com/All-Hands-AI/OpenHands  · _Open platform: controller-agent-runtime with sandboxed execution. 65K+ GitHub stars._
  - **DeepLearning.AI: Building Code Agents with Hugging Face smolagents** · Thomas Wolf & Aymeric Roucher — full course _(course)_ — https://www.deeplearning.ai/short-courses/building-code-agents-with-smolagents/  · _Hands-on sandboxed code execution with E2B — the fastest path to a working code agent._
  - **Anthropic Computer Use Guide** — full guide + cookbook _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/computer-use  · _The primary reference for computer-use agents — screenshots, clicks, typing._

### Sem 2 · Weeks 8–10 · Evaluation, Observability & Safety
_Build the eval-and-observe infrastructure that makes reliable agents possible: held-out test sets, LLM-as-judge, end-state eval, full-session tracing, error analysis, guardrails, and the eval-driven development loop._
- **evaluate** — Build a complete eval harness (≥20 held-out cases, LLM-as-judge, error analysis) with full-session observability traces, and demonstrate a measurable before/after improvement from diagnosis to fix.
  - *proof:* Complete eval harness (≥20 held-out cases, LLM-as-judge, error analysis), full-session observability traces, and a measurable before/after improvement from diagnosis to fix.
- *readings:*
  - **Anthropic: Evaluate Your Agent** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/evaluate  · _End-state eval, LLM-as-judge, human review — the production eval methodology._
  - **Langfuse (OSS Observability)** — tracing + evaluation docs _(reference)_ — https://langfuse.com/docs  · _Leading open-source, MIT-licensed. Full-session trace capture for multi-step agent chains._
  - **Hugging Face Agents Course — Observability & Eval Unit** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit4  · _Hands-on with Langfuse/OpenTelemetry for agent tracing and evaluation._
  - **Berkeley Advanced LLM Agents — Safety Lectures** — safety/guardrails lectures _(course)_ — https://rdi.berkeley.edu/advanced-agentic-ai/  · _Rigorous academic treatment of agent safety, alignment, and guardrails._

### Sem 2 · Weeks 11–12 · Production Deployment & Capstone
_Ship your portfolio-grade agent system. Deploy with reliability patterns (checkpointing, retry, rainbow deploys), write the architecture decision record, and present the system end-to-end._
- **create** — Ship a portfolio-grade agent system with full observability, eval harness, and an architecture decision record. Demonstrate at least 3 advanced capabilities and defend every architectural choice quantitatively.
  - *proof:* Portfolio-grade agent system: shipped, observable, eval-harnessed, with an architecture decision record. Must demonstrate at least 3 of: code execution, RAG, multi-agent, context engineering, computer use.
- *readings:*
  - **AI Engineering** · Chip Huyen — ch. 13-15 (deployment, monitoring, continuous improvement) _(textbook, paid)_  · _The production deployment chapters — what it takes to ship and maintain._
  - **Anthropic: Building Effective Agents (eBook)** — full — Coinbase & Thomson Reuters case studies _(reference)_ — https://docs.anthropic.com/en/docs/build-with-claude/agent-patterns  · _Real enterprise case studies of agent deployment at scale._

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
