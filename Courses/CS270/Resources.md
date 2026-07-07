# 📖 Resources — CS270 AI Engineering

## Primary text
- **AI Engineering: Building Applications with Foundation Models** · Chip Huyen — Ch.5 (Prompt Engineering) + Ch.6 (RAG and Agents) + Ch.10 (Architecture) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166298/  · _The definitive production-AI-engineering book. Evaluation-first, pattern-driven, written by someone who ships. Every chapter maps to a CS270 unit._

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

## By unit

### Sem 1 · Foundations — The Augmented LLM
- **AI Engineering (Chip Huyen)** — Ch.5 (Prompt Engineering): In-Context Learning, System vs User Prompts, Context Efficiency, Best Practices, Defensive Prompting _(textbook, paid)_  · _Production prompt engineering — structured, evaluation-aware. The context-efficiency section previews Unit 3._
- **Building Effective Agents (blog, Anthropic)** — § 'Building block: The augmented LLM' _(reference)_  · _The augmented LLM concept: retrieval + tools + memory as the atomic unit. Sets the mental model for the entire course._
- **Model Context Protocol (MCP) Specification** — Introduction + Quickstart: build a client, connect to a server, call a tool _(reference)_ — https://modelcontextprotocol.io/  · _The universal standard for agent-tool integration. Hands-on: build an MCP client in Unit 1._
- **Chain-of-Thought Prompting (Wei et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The technique that unlocked reasoning in LLMs. Must-understand for any agent builder._
- **Anthropic Prompt Engineering Guide** — Overview + Structured Outputs + Tool Use sections _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Production reference for prompt structure, XML tagging, and structured output. The lab standard._

### Sem 1 · Workflow Patterns — Choosing the Right Architecture
- **Building Effective Agents (blog, Anthropic)** — § 'Building blocks, workflows, and agents' — all 5 workflow patterns with diagrams and when-to-use guidance _(reference)_  · _The canonical reference. Every FAANG agent team knows this post. Diagrams make the patterns instantly recognizable._
- **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): Agent overview, tools, planning, reflection, memory — complements the Anthropic patterns with evaluation perspective _(textbook, paid)_  · _Shows WHY patterns work and their failure modes — not just the patterns themselves._
- **ReAct: Synergizing Reasoning and Acting (Yao et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent loop. ReAct = reasoning + action interleaving. Underpins the orchestrator-worker and evaluator-optimizer patterns._
- **Anthropic Cookbook: Basic Workflow Patterns** — full cookbook _(reference)_ — https://platform.claude.com/cookbook/patterns-agents-basic-workflows  · _Reference Python implementations of all 5 patterns. Use as implementation templates, not copy-paste._

### Sem 1 · Context Engineering — The Finite Resource
- **Effective Context Engineering for AI Agents (blog, Anthropic, Sep 2025)** — whole post: system prompt altitude, tool token-efficiency, compaction, note-taking, multi-agent context strategies _(reference)_  · _THE definitive piece. Written by Anthropic's Applied AI team based on real production agent deployments at scale._
- **Context Engineering for Agents (blog, LangChain, Jul 2025)** — Write / Select / Compress / Isolate framework; Claude Code, SWE-agent, multi-agent case studies _(reference)_ — https://www.langchain.com/blog/context-engineering-for-agents  · _Practical taxonomy with real agent examples. The four strategies map directly to implementation decisions._
- **AI Engineering (Chip Huyen)** — Ch.5 §Context Length and Context Efficiency + Ch.10 §Step 1 (Enhance Context) _(textbook, paid)_  · _Ties context engineering into the broader AI system architecture. Shows where context decisions fit in production._
- **Anthropic: How we built our multi-agent research system** — whole post _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _Real-world sub-agent architecture for context isolation. Maps to the advanced context-engineering pattern._

### Sem 1 · RAG & Retrieval — Naïve to Agentic
- **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): RAG architecture, embedding-based retrieval, vector search, RAG evaluation, when RAG vs finetuning _(textbook, paid)_  · _Production RAG perspective. Focuses on evaluation and architecture decisions, not just implementation._
- **RAG Techniques (NirDiamant, GitHub)** — Notebooks: Query Transformation, HyDE, Self-RAG, Corrective RAG, Agentic RAG _(reference)_ — https://github.com/NirDiamant/rag_techniques  · _The most comprehensive open-source collection of advanced RAG techniques. Each technique as a standalone notebook. The lab standard for Unit 4._
- **Building Effective Agents (blog, Anthropic)** — § 'Building block: The augmented LLM' — retrieval as an augmentation _(reference)_  · _Positions RAG as one augmentation in the augmented-LLM building block. Connects Unit 4 back to Unit 1._

### Sem 1 · Evals & Observability — You Can't Improve What You Can't Measure
- **Evaluation and Benchmarking of LLM Agents: A Survey (2025)** — §3-5: evaluation dimensions, benchmarks, methods _(paper)_ — https://arxiv.org/html/2507.21504v1  · _Comprehensive survey of the agent evaluation landscape. The two-dimensional framework organizes all approaches._
- **OpenAI Agents SDK: Tracing & Evals** — Tracing, Evaluation, and Guardrails sections _(reference)_ — https://openai.github.io/openai-agents-python/  · _Production eval infrastructure. Traces for debugging, evals for measuring, guardrails for safety._
- **AI Engineering (Chip Huyen)** — Ch.7 (Evaluation): Offline vs Online Evaluation, LLM-as-Judge, Human Evaluation, A/B Testing _(textbook, paid)_  · _Chip's eval framework is the industry standard. Evaluation-first mindset throughout._
- **Datadog LLM Observability** — full post _(reference)_ — https://www.datadoghq.com/blog/llm-evaluation-framework-best-practices/  · _Production observability patterns: what to log, what to alert on, how to trace agent decisions._

### Sem 1 · Semester 1 Finals — Applied Agent + Teach-Back
_(no unit-specific resources yet)_
