# 📖 Resources — AG201 AI Agent Engineering

## Primary text
- **AI Engineering: Building Applications with Foundation Models** · Chip Huyen — whole — ch. 4 (eval), ch. 5 (prompting), ch. 6 (RAG & agents), ch. 9–10 (architecture & deployment). Local copy: Uploads/AG201/AI Engineering by Chip Huyen.md _(textbook, paid)_ — https://www.oreilly.com/library/view/ai-engineering/9781098166309/  · _The single best prose-based textbook for this learner — concept-first, no code required, with the eval rigor and production architecture judgment that separates senior engineers. Read cover-to-cover. Full markdown in vault._

## Course library
- **UC Berkeley CS294/194-196: LLM Agents MOOC** · Dawn Song, Xinyun Chen — F24 foundations, Sp25 Advanced LLM Agents, F25 Agentic AI — full lecture videos on YouTube _(course)_ — https://llmagents-learning.org/  · _The definitive academic agent course — guest lectures from the researchers who defined the field. The structured spine for the whole course._
- **Anthropic Engineering Blog — Agent Essays** — "Building Effective Agents", "How we built our multi-agent research system", "Effective context engineering", "Effective harnesses for long-running agents", "When to use multi-agent systems (and when not to)" _(reference)_ — https://anthropic.com/engineering  · _The highest-signal free resource for architectural reasoning. These five essays teach the design tradeoffs frontier teams actually use._
- **Lilian Weng: LLM Powered Autonomous Agents** · Lilian Weng — full post _(reference)_ — https://lilianweng.github.io/posts/2023-06-23-agent/  · _The canonical free deep-dive on planning, memory, and tool-use — still the most-cited agent primer._
- **"The Second Half"** · Shunyu Yao — full essay _(reference)_ — https://ysymyth.github.io/The-Second-Half/  · _The canonical framing of the frontier shift: evaluation over training. Sets the philosophical spine for the entire course._
- **Manus: Context Engineering for AI Agents** · Yichao 'Peak' Ji — full article (six principles) _(reference)_ — https://manus.im/blog/context-engineering  · _The six principles from a production agent at scale — KV-cache hit rate as the single most important metric._
- **Model Context Protocol (MCP)** — specification + docs _(reference)_ — https://modelcontextprotocol.io  · _The de-facto standard for connecting agents to tools/data via JSON-RPC. Core knowledge for any agent engineer._

## By unit

### Sem 1 · LLM Foundations — What You Need to Reason About
- **3Blue1Brown: Transformers & Attention** — full series _(video)_ — https://www.youtube.com/watch?v=eMlx5fFNoYc  · _The visual intuition for attention, Q/K/V, and multi-head — the 'aha' moment before diving into details._
- **Andrej Karpathy: Deep Dive into LLMs like ChatGPT** — full video (~3.5h) _(video)_ — https://www.youtube.com/watch?v=7xTGNNLPyMI  · _The fastest path to a strong mental model of how LLMs work — tokenization, pretraining, fine-tuning, RLHF, tool use, multimodal._
- **"The Second Half" (Shunyu Yao)** — full essay _(reference)_ — https://ysymyth.github.io/The-Second-Half/  · _Sets the philosophical spine: evaluation over training. Read first — it frames why this course is eval-forward._
- **AI Engineering (Huyen)** — ch. 1–3 (foundation models overview) _(textbook, paid)_  · _The engineering perspective: what matters for building on top of models, not training them._

### Sem 1 · Prompt Engineering & Structured Output — Programming in Natural Language
- **Anthropic Prompt Engineering Guide** — full guide (overview → be clear and direct → use examples → chain of thought → system prompts) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview  · _Vendor-authoritative, research-backed, continuously updated — the primary reference._
- **OpenAI Structured Outputs / Function Calling** — full guide _(docs)_ — https://platform.openai.com/docs/guides/structured-outputs  · _The canonical API spec for structured output and tool-calling schemas._
- **AI Engineering (Huyen)** — ch. 5 (prompt engineering) _(textbook, paid)_  · _Concept-first treatment of prompt architecture, few-shot selection, and structured output as programming._
- **Lilian Weng: Prompt Engineering** — full post _(reference)_ — https://lilianweng.github.io/posts/2024-02-05-prompt-engineering/  · _Comprehensive taxonomy of prompting techniques with research citations._

### Sem 1 · The Augmented LLM Loop — ReAct, Planning & Reflection
- **ReAct: Synergizing Reasoning and Acting in Language Models** · Yao et al. (ICLR 2023) — full paper _(paper)_ — https://arxiv.org/abs/2210.03629  · _The foundational agent-loop paper — read the primary source that defined the pattern._
- **Reflexion: Language Agents with Verbal Reinforcement Learning** · Shinn et al. (NeurIPS 2023) — full paper _(paper)_ — https://arxiv.org/abs/2303.11366  · _The reflection pattern: self-critique + improvement loop — the second major agent pattern._
- **Lilian Weng: LLM Powered Autonomous Agents** — full post _(reference)_ — https://lilianweng.github.io/posts/2023-06-23-agent/  · _The canonical survey: planning, memory, tool-use — the complete agent architecture picture._
- **SWE-agent: Agent-Computer Interfaces** · Yang, Jimenez et al. (NeurIPS 2024) — sec. 1–3 (ACI design) _(reference)_ — https://arxiv.org/abs/2405.15793  · _The ACI insight: agents need purpose-built interfaces, not human UIs. A core architectural principle._
- **Anthropic: Building Effective Agents** — full essay _(reference)_ — https://www.anthropic.com/engineering/building-effective-agents  · _Workflows vs agents — the most important architectural distinction. When simplicity wins._

### Sem 1 · Eval Foundations — The Engine of Improvement
- **Hamel Husain: Your AI Product Needs Evals** — full post _(reference)_ — https://hamel.dev/blog/posts/evals/  · _The canonical eval essay — why evals matter and how to build them from day one._
- **Hamel Husain: A Field Guide to Rapidly Improving AI Products** — full post _(reference)_ — https://hamel.dev/blog/posts/field-guide/  · _The eval-driven development loop — build, measure, analyze, improve, repeat._
- **Anthropic: Evaluate Your Agent** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/evaluate  · _End-state eval, LLM-as-judge, human review — the production eval methodology from a frontier lab._
- **Eugene Yan: An LLM-as-Judge Won't Save the Product** — full post _(reference)_ — https://eugeneyan.com/writing/llm-judge/  · _The limits of LLM-as-judge — when it works, when it doesn't, and why human review is non-negotiable._
- **AI Engineering (Huyen)** — ch. 4 (evaluate AI systems) _(textbook, paid)_  · _The engineering textbook treatment of eval — metrics, test sets, error analysis._

### Sem 1 · Tool Use & MCP — Connecting Agents to the World
- **Anthropic Tool Use Guide** — full guide (overview → defining tools → tool use workflow → best practices) _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/tool-use  · _The primary reference for tool-design principles — written by the team defining the field._
- **OpenAI Function Calling Guide** — full guide _(docs)_ — https://platform.openai.com/docs/guides/function-calling  · _The other major API contract — understand both paradigms._
- **Toolformer: Language Models Can Teach Themselves to Use Tools** · Schick et al. — full paper _(paper)_ — https://arxiv.org/abs/2302.04761  · _The foundational paper on tool use — how models learn to call APIs._
- **Model Context Protocol (MCP) Specification** — specification + quickstart _(docs)_ — https://modelcontextprotocol.io  · _The de-facto standard for agent-tool integration — JSON-RPC, Resources/Tools/Prompts primitives. Required knowledge._
- **ReAct (Yao et al.)** — tool-use sections (re-read with fresh eyes) _(paper)_ — https://arxiv.org/abs/2210.03629  · _Re-read the tool-use sections now that you understand the loop — see how tool design shapes loop behavior._

### Sem 1 · Context Engineering & Memory — Where Reliability Is Won
- **Manus: Context Engineering for AI Agents** · Yichao 'Peak' Ji — full article (six principles) _(reference)_ — https://manus.im/blog/context-engineering  · _The six principles from a production agent at scale — KV-cache hit rate as the single most important metric._
- **Anthropic: Effective Context Engineering for AI Agents** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/context-window  · _The complementary practitioner treatment from the other major lab._
- **MemGPT: Towards LLMs as Operating Systems** · Packer et al. — full paper _(paper)_ — https://arxiv.org/abs/2310.08560  · _The OS-analogy paper: virtual context management, interrupt-driven memory — the conceptual foundation._
- **Anthropic: Effective Harnesses for Long-Running Agents** — full essay _(reference)_ — https://www.anthropic.com/engineering/effective-harnesses  · _How to build harnesses that support long-horizon agent runs — progress artifacts, checkpointing, initialization._

### Sem 1 · RAG & Retrieval Architecture — Grounding Agents in Data
- **AI Engineering (Huyen)** — ch. 6 (RAG and agents — retrieval, reranking, agent-integrated RAG) _(textbook, paid)_  · _The engineering textbook treatment — architecture decisions and trade-offs, not just vector search._
- **Jason Liu: RAG is More Than Embedding Search** — full post _(reference)_ — https://jxnl.co/writing/2024/05/10/rag-is-more-than-embedding-search/  · _The systems view: retrieval, reranking, evaluation — RAG as architecture, not a library call._
- **Hugging Face Agents Course — Agentic RAG Unit** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit3  · _RAG integrated as an agent tool — the agent decides when to retrieve._

### Sem 2 · Multi-Agent Orchestration — When to Scale Out
- **Anthropic: How We Built Our Multi-Agent Research System** — full article _(reference)_ — https://www.anthropic.com/engineering/multi-agent-research-system  · _The defining multi-agent reference: orchestrator-worker, artifact pattern, rainbow deployments._
- **Cognition: Don't Build Multi-Agents** — full article _(reference)_ — https://cognition.ai/blog/dont-build-multi-agents  · _The counter-argument: single context is more reliable for tightly coupled work. Read both sides._
- **Cognition: Multi-Agents — What's Actually Working** — full article _(reference)_ — https://cognition.ai/blog/multi-agents-whats-working  · _Read-only subagents, MCP delegation, deliberate context isolation — the nuanced middle ground._
- **Anthropic: When to Use Multi-Agent Systems (and When Not To)** — full essay _(reference)_ — https://www.anthropic.com/engineering/when-to-use-multi-agent  · _The decision framework: task structure, cost, reliability — when multi-agent is worth 15× tokens._

### Sem 2 · Code-Execution & Computer-Use Agents — Agents That Act in Digital Worlds
- **CodeAct: Executable Code as a Unified Action Space** · Wang et al. — full paper _(paper)_ — https://arxiv.org/abs/2402.01030  · _The paradigm: code as action space — increasingly outperforms JSON tool-calling._
- **OpenHands Architecture & CodeAct Agent** — architecture docs + CodeAct agent source _(reference)_ — https://github.com/All-Hands-AI/OpenHands  · _Open platform: controller-agent-runtime with sandboxed execution. 65K+ GitHub stars._
- **SWE-agent: Agent-Computer Interfaces (NeurIPS 2024)** · Yang, Jimenez et al. — full paper — focus on ACI design _(reference)_ — https://arxiv.org/abs/2405.15793  · _The ACI concept: purpose-built interfaces for agents. Mini-SWE-agent reaches >74% SWE-bench in ~100 lines._
- **Anthropic Computer Use Guide** — full guide _(docs)_ — https://docs.anthropic.com/en/docs/build-with-claude/computer-use  · _The primary reference for computer-use agents — screenshots, clicks, typing._
- **OpenAI Computer-Using Agent System Card** — full system card _(reference)_ — https://openai.com/index/computer-using-agent/  · _The other major computer-use paradigm — compare approaches._

### Sem 2 · Safety, Guardrails & Reliability — Capping the Blast Radius
- **OWASP Top 10 for LLM Applications** — full list with descriptions _(reference)_ — https://owasp.org/www-project-top-10-for-large-language-model-applications/  · _The industry-standard threat model — every agent engineer should know these 10 risks._
- **Simon Willison: Prompt Injection and the Lethal Trifecta** — series of posts _(reference)_ — https://simonwillison.net/series/prompt-injection/  · _The clearest explainer of prompt injection — why it's the hardest security problem in agent systems._
- **Berkeley Advanced LLM Agents MOOC — Safety Lectures** — safety/guardrails lectures _(course)_ — https://rdi.berkeley.edu/advanced-agentic-ai/  · _Rigorous academic treatment of agent safety, alignment, and guardrails._
- **Fin by Intercom: Safety Architecture** — escalation + safety sections _(reference)_ — https://www.intercom.com/blog/announcing-fin/  · _Production case study: escalation-to-human on low confidence, content safety filters, 99.97% uptime._

### Sem 2 · Production Deployment & Cost Engineering — Shipping Reliable Agents
- **AI Engineering (Huyen)** — ch. 9–10 (architecture, deployment, monitoring) _(textbook, paid)_  · _The production deployment chapters — what it takes to ship and maintain agent systems._
- **Anthropic: Effective Harnesses for Long-Running Agents** — full essay _(reference)_ — https://www.anthropic.com/engineering/effective-harnesses  · _Checkpointing, progress artifacts, initialization — the patterns for long-horizon reliability._
- **Manus: Context Engineering (production economics)** · Yichao 'Peak' Ji — KV-cache economics sections (re-read) _(reference)_ — https://manus.im/blog/context-engineering  · _The economics of running agents at scale — cost tracking, optimization, why Manus refused to fine-tune._
- **"The Landscape of Agentic Reinforcement Learning for LLMs: A Survey"** · Zhang et al. — abstract + key results _(reference)_ — https://arxiv.org/abs/2509.02547  · _The SOTA map of agentic RL — when training agents beats prompting them._

### Sem 2 · Observability & Trajectory Evals — Diagnosing Failure at Scale
- **Langfuse Documentation** — tracing + evaluation docs _(reference)_ — https://langfuse.com/docs  · _Leading open-source, MIT-licensed. Full-session trace capture for multi-step agent chains._
- **Hamel Husain: A Field Guide to Rapidly Improving AI Products** — full post (re-read with fresh eyes) _(reference)_ — https://hamel.dev/blog/posts/field-guide/  · _The eval-driven development loop — now with hands-on tracing experience._
- **Shreya Shankar et al.: Who Validates the Validators?** — full paper _(reference)_ — https://arxiv.org/abs/2310.09335  · _LLM-as-judge validation — when the judge is wrong, and how to align it to human judgment._
- **Hugging Face Agents Course — Observability & Eval Unit** — full unit _(course)_ — https://huggingface.co/learn/agents-course/unit4  · _Hands-on with Langfuse/OpenTelemetry for agent tracing and evaluation._
- **τ-bench: A Benchmark for Tool-Agent-User Interaction** · Yao et al. (ICLR 2025) — abstract + benchmark design _(reference)_ — https://arxiv.org/abs/2406.12045  · _The canonical tool-use agent benchmark — what a real agent eval looks like._

### Sem 2 · Capstone — Architecture Decision Record
- **All course resources — this is synthesis, not new material** — revisit as needed _(reference)_  · _The capstone draws on everything: Huyen, Anthropic, Berkeley MOOC, Lilian Weng, Manus, Yao._
