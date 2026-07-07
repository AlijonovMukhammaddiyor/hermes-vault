# 📖 Resources — CS270 AI Agents

## Primary text
- **AI Engineering: Building Applications with Foundation Models** · Chip Huyen — Ch.5 (Prompt Engineering) + Ch.6 (RAG and Agents) + Ch.10 (Architecture) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166298/  · _The definitive production-AI-engineering book. Evaluation-first, pattern-driven, conceptually aligned with Anthropic's agent philosophy. Every chapter maps to a CS270 unit._

## Course library
- **Hands-On Large Language Models** · Jay Alammar & Maarten Grootendorst — Ch.6 (Prompt Engineering) + Ch.7 (Advanced Text Generation/Agents) + Ch.8 (Semantic Search & RAG) _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Learner already owns this (in Uploads/CS270/). Visual, code-backed, ideal hands-on companion for KAIST engineering style._
- **Building Effective Agents** · Anthropic Applied AI team — whole post _(reference)_ — https://www.anthropic.com/engineering/building-effective-agents  · _Industry-defining agent design framework. The 5 workflow patterns are the decision backbone of Unit 2._
- **Effective Context Engineering for AI Agents** · Anthropic Applied AI team — whole post _(reference)_ — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents  · _THE piece on context as a finite resource. System prompt design, tool token-efficiency, compaction, note-taking, multi-agent strategies._
- **Demystifying Evals for AI Agents** · Anthropic — whole post _(reference)_ — https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents  · _Eval taxonomy: tasks, trials, graders, transcripts, outcomes, harnesses. The eval design reference for the entire course._
- **Large Language Model Agents (MOOC)** · Dawn Song & Xinyun Chen, UC Berkeley — Lectures: LLM Reasoning, ReAct/Agent History, Agentic Frameworks, RAG, Compound AI Systems _(course)_ — https://llmagents-learning.org/f24  · _The best canonical university curriculum on LLM agents. Guest lectures from DeepMind, OpenAI, Databricks, Anthropic._
- **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _Foundational agent paper. Reasoning + action interleaving — the core idea behind every modern agent._
- **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models** · Wei et al. — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The reasoning technique that unlocked modern prompting and agent planning._

## By unit

### Sem 1 · Foundations — prompting, structured output, tool/function calling
- **AI Engineering (Chip Huyen)** — Ch.5 (Prompt Engineering): In-Context Learning, System vs User Prompts, Context Efficiency, Best Practices, Defensive Prompting _(textbook, paid)_  · _Production prompt engineering — structured, evaluation-aware. The context-efficiency section previews Unit 3._
- **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.6 (Prompt Engineering) + Ch.7 (Advanced Text Generation: LangChain chains, memory, agents, ReAct) _(textbook, paid)_  · _Code-backed, visual. Ch.7 introduces ReAct agents — the bridge to Unit 2's workflow patterns._
- **Building Effective Agents (Anthropic)** — Section: 'Building block: The augmented LLM' _(reference)_  · _The augmented LLM concept: retrieval + tools + memory as the atomic unit. Sets the mental model for the entire course._
- **Anthropic Prompt Engineering Guide** — Overview + Structured Outputs sections _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Production reference for prompt structure, XML tagging, and structured output._
- **Chain-of-Thought Prompting (Wei et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2201.11903  · _The technique that unlocked reasoning in LLMs. Must-understand for any agent builder._

### Sem 1 · Workflow Patterns — chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
- **Building Effective Agents (Anthropic)** — Section: 'Building blocks, workflows, and agents' — all 5 workflow patterns with diagrams and when-to-use guidance _(reference)_  · _The canonical reference. Every FAANG agent team knows this post. Diagrams make the patterns instantly recognizable._
- **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): Agent overview, tools, planning, reflection, memory _(textbook, paid)_  · _Complementary framework: focuses on why patterns work and their failure modes, not just the patterns themselves._
- **Anthropic Cookbook: Basic Workflow Patterns** — full cookbook _(reference)_ — https://platform.claude.com/cookbook/patterns-agents-basic-workflows  · _Reference Python implementations of all 5 patterns. Use as implementation templates._
- **ReAct: Synergizing Reasoning and Acting (Yao et al., 2022)** — whole paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent loop. ReAct = reasoning + action interleaving. Underpins the orchestrator-worker and evaluator-optimizer patterns._

### Sem 1 · Context Engineering — budgeting, tool-result compaction, memory
- **Effective Context Engineering for AI Agents (Anthropic, Sep 2025)** — whole post: system prompt altitude, tool token-efficiency, compaction, note-taking, multi-agent context _(reference)_  · _The definitive piece. Written by Anthropic's Applied AI team based on real production agent deployments._
- **Context Engineering for Agents (LangChain, Jul 2025)** — Write / Select / Compress / Isolate framework; Claude Code, SWE-agent, multi-agent case studies _(reference)_ — https://www.langchain.com/blog/context-engineering-for-agents  · _Practical taxonomy with real agent examples. The four strategies map directly to implementation decisions._
- **AI Engineering (Chip Huyen)** — Ch.5 Context Length and Context Efficiency + Ch.10 Step 1 (Enhance Context) _(textbook, paid)_  · _Ties context engineering into the broader AI system architecture. Shows where context decisions fit in production._
- **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.7 Memory: Conversation Buffer, Windowed Buffer, Conversation Summary (pp.209-217) _(textbook, paid)_  · _Code-backed implementations of memory patterns. Build and compare buffer types._

### Sem 1 · RAG & Context — naive to advanced to agentic retrieval
- **Hands-On Large Language Models (Alammar & Grootendorst)** — Ch.8 (Semantic Search and RAG): Dense Retrieval, Reranking, RAG fundamentals, Advanced RAG, RAG Evaluation (pp.225-258) _(textbook, paid)_  · _Complete hands-on RAG chapter with code. Covers the full pipeline from embeddings to evaluation._
- **AI Engineering (Chip Huyen)** — Ch.6 (RAG and Agents): RAG architecture, embedding-based retrieval, vector search, RAG evaluation _(textbook, paid)_  · _Production RAG perspective: when RAG vs finetuning, how to evaluate retrieval quality._
- **RAG Techniques (NirDiamant, GitHub)** — Notebooks: Query Transformation, HyDE, Self-RAG, Corrective RAG, Agentic RAG _(reference)_ — https://github.com/NirDiamant/rag_techniques  · _The most comprehensive open-source collection of advanced RAG techniques. Each technique has a standalone notebook._
- **Building Effective Agents (Anthropic)** — Section: 'Building block: The augmented LLM' — retrieval as an augmentation _(reference)_  · _Positions RAG as one augmentation in the augmented-LLM building block. Connects Unit 4 back to Unit 1._

### Sem 1 · Semester 1 Finals (applied + teach-back)
- **All S1 unit resources (cumulative)** — Review all readings from units 1-4 as the capstone draws on every concept _(reference)_  · _The finals integrate all four units. Revisit the primary text and key papers (AI Engineering Ch.5-6,10, Building Effective Agents, Effective Context Engineering, ReAct, Chain-of-Thought) for the closed-book teach-back._
