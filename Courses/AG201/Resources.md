# 📖 Resources — AG201 AI Agent Engineering

## Primary text
- **Speech and Language Processing (3rd ed. draft)** · Dan Jurafsky & James H. Martin — ch. 9-12 (transformers, LLMs, prompting, fine-tuning, RLHF, RAG, agents) _(textbook)_ — https://web.stanford.edu/~jurafsky/slp3/  · _The canonical, free, continuously updated NLP/LLM reference — chapters 9-12 cover the full LLM stack that agents are built on._

## Course library
- **AI Engineering** · Chip Huyen — whole (evals ch. 5-7, RAG ch. 8-9, agents ch. 10-12, deployment ch. 13-15) _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166309/  · _The practitioner's textbook for building LLM applications end-to-end — bridges theory to production._
- **Hands-On Large Language Models** · Jay Alammar & Maarten Grootendorst — whole _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Visual, code-first companion — builds transformer/attention intuition through implementation._
- **UC Berkeley CS294/194-196: Large Language Model Agents** · Dawn Song, Xinyun Chen — Lectures 1-14 (full MOOC) _(course)_ — https://llmagents-learning.org/  · _The definitive academic agent course — guest lectures from the researchers who defined the field._
- **Stanford CS336: Language Modeling from Scratch** · Percy Liang, et al. — Lectures 1-10 _(course)_ — https://cs336.stanford.edu/  · _Build an LLM end-to-end — deepest possible foundation for understanding what agents run on._

## By unit

### Sem 1 · Python for AI Engineering
- **AI Python for Beginners (DeepLearning.AI)** — all 4 lessons _(course)_ — https://www.deeplearning.ai/short-courses/ai-python-for-beginners/  · _Fastest path to the specific Python (data handling, APIs, async) that agents need — agent-oriented from day one._
- **Python Crash Course (3rd ed.)** · Eric Matthes — ch. 1-11, 15-17 (APIs), 18-20 (Django intro — skip, just read API patterns) _(textbook, paid)_  · _Solid Python foundations if the learner needs more depth than the DLAI course._

### Sem 1 · LLM Fundamentals — Transformers, Attention, Tokenization
- **Neural Networks: Zero to Hero (Andrej Karpathy)** — Lectures 1-7 (micrograd → GPT from scratch) _(video)_ — https://www.youtube.com/playlist?list=PLAqhIrjkxrVzNBzVO2E4PcbWQyZJ4hR9h  · _Builds GPT from scratch — unmatched intuition for what happens inside the model agents call._
- **3Blue1Brown: Transformers & Attention** — full series _(video)_ — https://www.youtube.com/watch?v=eMlx5fFNoYc  · _Visual intuition for attention, query/key/value, and multi-head attention — the 'aha' moment._
- **Speech and Language Processing (3rd ed.)** · Jurafsky & Martin — ch. 9 (transformers), ch. 10 (pretraining & fine-tuning), ch. 11 (prompting & in-context learning) _(textbook)_ — https://web.stanford.edu/~jurafsky/slp3/  · _The authoritative technical reference — read alongside Karpathy for theory + implementation._
- **Hands-On Large Language Models** · Alammar & Grootendorst — ch. 1-4 (tokenization → attention → transformers) _(textbook, paid)_ — https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/  · _Code-first, visual companion — implement as you read._

### Sem 1 · Prompt Engineering — Programming in Natural Language
- **Anthropic Prompt Engineering Guide** — full guide (overview → be clear and direct → use examples → chain of thought → system prompts) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Vendor-authoritative, research-backed, continuously updated — the primary reference._
- **ChatGPT Prompt Engineering for Developers (DeepLearning.AI)** — all lessons _(course)_ — https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/  · _Hands-on with the patterns: iterative refinement, summarizing, inferring, transforming, expanding._
- **Prompting Guide (DAIR.AI)** — techniques section (zero-shot, few-shot, CoT, self-consistency, ReAct) _(reference)_ — https://www.promptingguide.ai/  · _Comprehensive catalog of prompting techniques with research paper citations._

### Sem 1 · Structured Output & Function Calling
- **OpenAI Structured Outputs / Function Calling** — full guide (structured outputs + function calling) _(docs)_ — https://platform.openai.com/docs/guides/structured-outputs  · _The canonical API spec — understand the contract before abstracting it._
- **Anthropic Tool Use Guide** — full guide (overview → defining tools → tool use workflow → best practices) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use  · _Anthropic's tool-use paradigm — the other major API contract._

### Sem 1 · Tool-Use Architectures
- **Anthropic: Writing Effective Tools for AI Agents** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use/best-practices  · _Eval-driven tool design principles from the team defining the field._
- **Anthropic: Building Effective Agents** — full (especially the augmenting LLMs and workflow patterns sections) _(reference)_ — https://docs.anthropic.com/en/docs/build-with-claude/agent-patterns  · _The five agentic patterns and when to use each. Read before building anything._

### Sem 1 · Agent Loops — ReAct, Planning & Reflection
- **ReAct: Synergizing Reasoning and Acting in Language Models (Yao et al., ICLR 2023)** — full paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent-loop paper — the pattern every agent inherits from._
- **Reflexion: Language Agents with Verbal Reinforcement Learning (Shinn et al.)** — full paper _(paper)_ — https://arxiv.org/abs/2303.11366  · _The reflection/self-improvement pattern — agents that learn from their own failures._
- **DeepLearning.AI: Agentic AI (Andrew Ng)** — all lessons (reflection, tool use, planning, multi-agent patterns) _(course)_ — https://www.deeplearning.ai/short-courses/agentic-ai/  · _Practical treatment of four design patterns with eval woven throughout._
- **Hugging Face Agents Course** — Units 0-2 (intro → smolagents → tools & agents) _(course)_ — https://huggingface.co/learn/agents-course  · _Hands-on with a framework AFTER building from scratch — learn what frameworks abstract._

### Sem 2 · Memory & Context Engineering
- **Manus: Context Engineering for AI Agents (Peak Ji, July 2025)** — full — all six principles _(reference)_ — https://manus.im/blog/context-engineering  · _The single best primary source on production context engineering at scale. KV-cache hit rate as the #1 metric._
- **Anthropic: Effective Context Engineering for AI Agents** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/context-engineering  · _Anthropic's treatment of context management — the other half of the frontier picture._
- **LLMs Get Lost in Multi-Turn Conversation (Laban, Hayashi et al., arXiv:2505.06120)** — full _(paper)_ — https://arxiv.org/abs/2505.06120  · _Quantifies context rot: 39% average drop single-turn → multi-turn. This is WHY context engineering matters._

### Sem 2 · Retrieval-Augmented Generation
- **DeepLearning.AI: Building and Evaluating Advanced RAG** — all lessons _(course)_ — https://www.deeplearning.ai/short-courses/advanced-retrieval-for-ai/  · _Production-grade RAG coverage from architecture to eval — the DLAI RAG series is the best hands-on path._
- **AI Engineering (Chip Huyen)** — ch. 8-9 (RAG architecture, chunking, embedding, retrieval, reranking, evaluation) _(textbook, paid)_  · _Engineering-first treatment: how to choose chunk size, when to rerank, how to eval retrieval quality._
- **Anthropic: Contextual Retrieval** — full post _(docs)_ — https://www.anthropic.com/news/contextual-retrieval  · _Contextual retrieval — enriching chunks with document context before embedding — a technique that significantly improves retrieval quality._
- **Hugging Face Agents Course: Agentic RAG Unit** — Agentic RAG unit _(course)_ — https://huggingface.co/learn/agents-course  · _RAG specifically in the agent context — when the agent decides what and when to retrieve._

### Sem 2 · Multi-Agent Systems & Orchestration
- **Anthropic: How We Built Our Multi-Agent Research System** — full _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _The definitive multi-agent case study: orchestrator-worker, 90.2% improvement, artifact pattern, rainbow deployments._
- **Cognition: Don't Build Multi-Agents (June 2025)** — full _(reference)_ — https://cognition.ai/blog/dont-build-multi-agents  · _The counter-argument: context engineering over parallelism, single coherent context is more reliable._
- **Cognition: Multi-Agents — What's Actually Working** — full _(reference)_ — https://cognition.ai/blog/multi-agents-whats-working  · _When multi-agent DOES work: read-only subagents, manager-devin delegation, deliberate context isolation._
- **UC Berkeley LLM Agents MOOC** — Multi-agent systems lecture (Dawn Song) _(course)_ — https://llmagents-learning.org/  · _Academic framing of the multi-agent design space._

### Sem 2 · Code Execution & Computer-Use Agents
- **SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering (Yang et al., NeurIPS 2024)** — full _(paper)_ — https://arxiv.org/abs/2405.15793  · _Introduced the ACI concept — the most-imitated idea in coding agents: agents need purpose-built interfaces, not human UIs._
- **OpenHands (formerly OpenDevin): CodeAct Architecture** — README + docs/architecture _(reference)_ — https://github.com/All-Hands-AI/OpenHands  · _CodeAct 2.1 reached SOTA open-source SWE-bench Verified (~53%); study the controller-agent-runtime architecture._
- **DeepLearning.AI: Building Code Agents with Hugging Face smolagents (Wolf & Roucher)** — all lessons _(course)_ — https://www.deeplearning.ai/short-courses/building-code-agents/  · _Hands-on sandboxed code execution using E2B — practical intro to the paradigm._
- **Anthropic Computer Use Documentation** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/computer-use  · _The reference implementation for computer-use/GUI agents — screenshot → action → observe loop._

### Sem 2 · Evaluation, Observability & Debugging
- **Anthropic: Evaluation Guidance for AI Agents** — full _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/evaluate  · _End-state evaluation, LLM-as-judge, human review, held-out test sets — from the team that built it._
- **Hamel Husain: Evals Writing & Error Analysis** — eval-related posts _(reference)_ — https://hamel.dev/  · _The practitioner's voice on eval design — practical, opinionated, battle-tested._
- **Langfuse Documentation** — tracing + evaluation sections _(docs)_ — https://langfuse.com/docs  · _Leading open-source observability platform — instrument and trace multi-step agent runs._
- **Arize Phoenix Documentation** — tracing + evals _(docs)_ — https://docs.arize.com/phoenix  · _OpenTelemetry-native, open-source, 50+ eval metrics — framework-agnostic alternative._

### Sem 2 · Production, Safety & Frontier Architecture
- **Cognition, Anthropic, Manus, Fin — all primary architecture sources from the course** — synthesis across all studied systems _(reference)_ — various  · _Now is when all the architecture study across the course synthesizes into your own judgment._
- **AI Engineering (Chip Huyen)** — ch. 13-15 (deployment, monitoring, scaling, cost optimization) _(textbook, paid)_  · _Production deployment pragmatics — what actually matters when people rely on your system._
- **UC Berkeley: Advanced LLM Agents (Spring 2025)** — safety lectures (Dawn Song), post-training lectures, frontier guest lectures _(course)_ — https://rdi.berkeley.edu/advanced-agentic-ai/  · _The research frontier — safety, multi-turn RL, and what's coming next._
- **Anthropic: Guardrails & Safety** — full _(reference)_ — https://docs.anthropic.com/en/docs/build-with-claude/guardrails  · _Production guardrail patterns: keep a human in the loop for high-stakes decisions, confidence assessment, escalation._
