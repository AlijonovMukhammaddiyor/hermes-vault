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

### Sem 1 · Tool Use — Building Agents That Act
- **Anthropic: Writing Effective Tools for AI Agents** — full guide, especially best practices section _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use  · _The primary reference for tool-design principles — written by the team defining the field._
- **Hugging Face Agents Course — Unit 1: Introduction to Agents** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit1  · _Hands-on with smolagents: tool definition, agent initialization, first agent run._
- **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. (ICLR 2023) — full paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational paper — read the primary source that defined the pattern._

### Sem 1 · Agent Loops — ReAct, Reflection & Planning
- **DeepLearning.AI: Agentic AI (Andrew Ng)** — full course (4 design patterns: reflection, tool use, planning, multi-agent) _(course)_ — https://www.deeplearning.ai/short-courses/agentic-ai/  · _Practical treatment of the four patterns with heavy eval emphasis — the canonical practitioner course._
- **SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering** · Yang, Jimenez, Wettig, Lieret, Yao, Narasimhan, Press (NeurIPS 2024) — full paper — focus on ACI design (sec. 3) _(paper)_ — https://arxiv.org/abs/2405.15793  · _The ACI insight: LM agents need purpose-built interfaces. The most-imitated idea in coding agents._
- **Hugging Face Agents Course — Unit 2: Agentic Patterns** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit2  · _Hands-on: tool use → planning → reflection patterns with smolagents._

### Sem 1 · Context Engineering & Memory
- **Manus: Context Engineering for AI Agents — Lessons from Building Manus** · Yichao 'Peak' Ji — full article (six principles) _(reference)_ — https://manus.im/blog/context-engineering  · _The six principles from a production agent at scale (~50 tool calls/task avg). KV-cache hit rate as the single most important metric._
- **Anthropic: Effective Context Engineering for AI Agents** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/context-window  · _The complementary practitioner treatment from the other major lab._
- **LLMs Get Lost in Multi-Turn Conversation** · Laban, Hayashi et al. — abstract + results (sec. 3-4) _(paper)_ — https://arxiv.org/abs/2505.06120  · _Quantified context rot: 39% drop single-turn → multi-turn across 15 models. The empirical case for context engineering._

### Sem 2 · RAG — Retrieval-Augmented Generation
- **DeepLearning.AI: Building and Evaluating Advanced RAG** — full course _(course)_ — https://www.deeplearning.ai/short-courses/  · _Production-grade RAG from chunking to eval — the practitioner's guide._
- **AI Engineering** · Chip Huyen — ch. 8-9 (RAG architecture, chunking, retrieval, reranking) _(textbook, paid)_  · _The engineering textbook treatment — architecture decisions and trade-offs._
- **Hugging Face Agents Course — Agentic RAG Unit** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit3  · _RAG integrated as an agent tool — retrieval-augmented agent behavior._

### Sem 2 · Multi-Agent Orchestration
- **Anthropic: How We Built Our Multi-Agent Research System** — full article _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _The defining multi-agent reference: orchestrator-worker, artifact pattern, rainbow deployments._
- **Cognition: Don't Build Multi-Agents** — full article _(reference)_ — https://cognition.ai/blog/dont-build-multi-agents  · _The counter-argument: single context is more reliable for tightly coupled work. Read both sides._
- **Cognition: Multi-Agents — What's Actually Working** — full article _(reference)_ — https://cognition.ai/blog/multi-agents-whats-working  · _Read-only subagents, MCP delegation, deliberate context isolation — the nuanced middle ground._
- **DeepLearning.AI Agentic AI** — multi-agent pattern _(course)_  · _Andrew Ng's practical treatment of the pattern._

### Sem 2 · Code-Execution & Computer-Use Agents
- **CodeAct: Executable Code as a Unified Action Space** · Wang et al. — full paper _(paper)_ — https://arxiv.org/abs/2402.01030  · _The paradigm: code as action space — increasingly outperforms JSON tool-calling._
- **OpenHands (formerly OpenDevin) — Architecture & CodeAct Agent** — architecture docs + CodeAct agent source _(reference)_ — https://github.com/All-Hands-AI/OpenHands  · _Open platform: controller-agent-runtime with sandboxed execution. 65K+ GitHub stars._
- **DeepLearning.AI: Building Code Agents with Hugging Face smolagents** · Thomas Wolf & Aymeric Roucher — full course _(course)_ — https://www.deeplearning.ai/short-courses/building-code-agents-with-smolagents/  · _Hands-on sandboxed code execution with E2B — the fastest path to a working code agent._
- **Anthropic Computer Use Guide** — full guide + cookbook _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/computer-use  · _The primary reference for computer-use agents — screenshots, clicks, typing._

### Sem 2 · Evaluation, Observability & Safety
- **Anthropic: Evaluate Your Agent** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/evaluate  · _End-state eval, LLM-as-judge, human review — the production eval methodology._
- **Langfuse (OSS Observability)** — tracing + evaluation docs _(reference)_ — https://langfuse.com/docs  · _Leading open-source, MIT-licensed. Full-session trace capture for multi-step agent chains._
- **Hugging Face Agents Course — Observability & Eval Unit** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit4  · _Hands-on with Langfuse/OpenTelemetry for agent tracing and evaluation._
- **Berkeley Advanced LLM Agents — Safety Lectures** — safety/guardrails lectures _(course)_ — https://rdi.berkeley.edu/advanced-agentic-ai/  · _Rigorous academic treatment of agent safety, alignment, and guardrails._

### Sem 2 · Production Deployment & Capstone
- **AI Engineering** · Chip Huyen — ch. 13-15 (deployment, monitoring, continuous improvement) _(textbook, paid)_  · _The production deployment chapters — what it takes to ship and maintain._
- **Anthropic: Building Effective Agents (eBook)** — full — Coinbase & Thomson Reuters case studies _(reference)_ — https://docs.anthropic.com/en/docs/build-with-claude/agent-patterns  · _Real enterprise case studies of agent deployment at scale._
