# Research Dossier — AG201: AI Agent Engineering

## A — Canonical Curriculum

| Source | URL | Why | What It Corroborated | Confidence |
|--------|-----|-----|----------------------|------------|
| UC Berkeley CS294/194-196 "LLM Agents" (Dawn Song) | https://llmagents-learning.org/ | Definitive academic agent course; public MOOC | Standard curriculum: LLM basics → tool use → agent loops → multi-agent → eval → safety | high |
| Stanford CS336 "Language Modeling from Scratch" | https://cs336.stanford.edu/ | Build LLM end-to-end; unmatched depth on fundamentals | LLM fundamentals must come before agent layers | high |
| Anthropic "Building Effective Agents" (Dec 2024) | https://docs.anthropic.com/en/docs/build-with-claude/agent-patterns | Single most-cited practitioner reference | Start simple, add complexity only when needed; five agentic patterns | high |
| DeepLearning.AI "Agentic AI" (Andrew Ng, Oct 2025) | https://www.deeplearning.ai/short-courses/agentic-ai/ | Four design patterns; eval-driven development | Eval must be threaded throughout, not deferred; reflection/tool-use/planning/multi-agent | high |
| Hugging Face Agents Course | https://huggingface.co/learn/agents-course | Free, hands-on: smolagents → LangGraph → eval → RAG | Proven hands-on sequence; leaderboard final challenge | high |
| Jurafsky & Martin SLP3 (draft, Aug 2025) | https://web.stanford.edu/~jurafsky/slp3/ | Canonical NLP/LLM reference; free | Chapters 9-12 cover transformers, LLMs, prompting, fine-tuning, RLHF, RAG, agents | high |
| Chip Huyen "AI Engineering" (O'Reilly, 2025) | https://www.oreilly.com/library/view/ai-engineering/9781098166309/ | Textbook for building LLM applications end-to-end | Evals, RAG, agents, deployment — the engineering side | high |
| Jay Alammar & Maarten Grootendorst "Hands-On Large Language Models" | https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/ | Visual, code-first companion to SLP3 | Visual transformer/attention intuition; code-along approach | high |

## B — The Excellence Bar

| Source | URL | Why | What It Corroborated | Confidence |
|--------|-----|-----|----------------------|------------|
| Anthropic FDE/Staff MLE job specs | https://www.anthropic.com/careers | Defines what "can build agents" means at the top | Production experience with LLMs, agent dev, eval frameworks, deployment at scale | med-high |
| Anthropic multi-agent variance analysis | https://www.anthropic.com/engineering/multi-agent-research-system | Token usage = 80% of performance variance | Staff-level = quantitative reasoning about cost/latency/reliability, not prompt-polishing | high |
| Cognition "Don't Build Multi-Agents" (June 2025) | https://cognition.ai/blog/dont-build-multi-agents | The counter-argument; context engineering focus | Architecture judgment: single-agent wins for tightly coupled work | high |
| SWE-agent paper (Yang et al., NeurIPS 2024) | https://arxiv.org/abs/2405.15793 | ACI concept; 12.47% vs prior 3.8% on SWE-bench | The most-imitated idea in coding agents | high |
| OpenHands/CodeAct (Wang et al.) | https://github.com/All-Hands-AI/OpenHands | Code-as-unified-action-space; 53% SWE-bench Verified | Open platform architecture: controller-agent-runtime with sandboxed execution | high |

## C — Expert Practices

| Source | URL | Why | What It Corroborated | Confidence |
|--------|-----|-----|----------------------|------------|
| Andrew Ng "Agentic AI" error analysis workflow | https://www.deeplearning.ai/short-courses/agentic-ai/ | Build fast → analyze traces → small evals → improve weakest component | The canonical dev loop; eval is the #1 differentiator | high |
| Anthropic eval guidance | https://docs.anthropic.com/en/docs/build-with-claude/evaluate | End-state eval for stateful agents; LLM-as-judge + human review | Eval design: held-out sets, end-state not turn-by-turn, human catches SEO/content-farm bias | high |
| Langfuse (OSS observability) | https://langfuse.com/docs | Leading open-source, MIT-licensed, acquired by ClickHouse Jan 2026 | Full-session trace capture for multi-step causal chains | high |
| Braintrust (eval-first, CI/CD-gated) | https://www.braintrust.dev/ | Generous free tier ~1M spans/month | Eval-as-gate in CI/CD pipeline | high |
| Anthropic reliability practices | https://docs.anthropic.com/en/docs/build-with-claude/agent-patterns | Keep architecture simple, reasoning visible; checkpointing, rainbow deploys | Compound/cascading errors; context rot; tool-call hallucination | high |
| Laban et al. "LLMs Get Lost in Multi-Turn" | https://arxiv.org/abs/2505.06120 | 39% average drop single-turn → multi-turn across 15 models | Context rot is quantifiably real; context engineering is not optional | high |

## D — The Frontier

| Source | URL | Why | What It Corroborated | Confidence |
|--------|-----|-----|----------------------|------------|
| Anthropic multi-agent research system | https://www.anthropic.com/engineering/multi-agent-research-system | 90.2% over single-agent Opus 4; 15× tokens | Orchestrator-worker; artifact pattern; rainbow deployments | high |
| Manus "Context Engineering" (Peak Ji, July 2025) | https://manus.im/blog/context-engineering | Six principles from a production agent at scale (~50 tool calls/task avg) | KV-cache hit rate is the single most important metric; file system as context; keep wrong turns in | high |
| Cognition "Multi-Agents: What's Actually Working" | https://cognition.ai/blog/multi-agents-whats-working | Read-only subagents; manager-Devin via internal MCP | Multi-agent that works: parallelize independent subtasks only; deliberate context isolation | high |
| ReAct (Yao et al., ICLR 2023) | https://arxiv.org/abs/2210.03629 | The base agent loop pattern | Reason+Act interleaved; still the foundational pattern | high |
| SWE-bench Verified leaderboard (2025-2026) | https://www.swebench.com/ | Saturated at ~77-81% by top models → field moving to harder benchmarks | SWE-bench Pro, Terminal-Bench, SWE-bench Multilingual | med-high |
| Fin (Intercom) engineering | https://fin.ai/ | Six-layer engine; 99.97% uptime; multi-model resilience | Production agent at scale: refine→retrieve→rerank→generate→validate→optimize | med |
| AgentGym-RL, RAGEN (multi-turn RL papers) | https://arxiv.org/ | Turn-level reward design; context-folding for long horizons | Post-training specifically for agentic behavior is the next frontier | med |

## E — Staying Current

| Source | URL | Why | What It Corroborated | Confidence |
|--------|-----|-----|----------------------|------------|
| Latent Space (swyx & Alessio) | https://www.latentspacepod.com/ | The AI-engineering publication of record | Newsletter + podcast; weekly LLM Paper Club on Discord | high |
| Simon Willison's Weblog | https://simonwillison.net/ | Near-daily practical AI engineering | "Lethal trifecta" for tool-using agent security | high |
| Sebastian Raschka "Ahead of AI" | https://magazine.sebastianraschka.com/ | Deep technical dives on LLM research | Staying current on training/fine-tuning advances | high |
| Nathan Lambert "Interconnects" | https://www.interconnects.ai/ | RLHF/post-training deep analysis | The training side of agent capability | high |
| LLM Agents Discord (Berkeley MOOC) | https://discord.gg/llm-agents | Active community around the Berkeley course | Peer learning, paper discussion, project sharing | med |
| COLM (Conference on Language Modeling) | https://colmweb.org/ | The LLM-focused academic venue | Where the best agent architecture papers are published | high |

## Open Questions / Could Not Verify

- **"Hermes-level" architecture:** Nous Research's Hermes is primarily a model series with a function-calling format; no distinct "Hermes agent system" architecture writeup was found publicly. The excellence-bar analysis generalizes from Anthropic/Cognition/Manus/Fin.
- **Fin.AI internal architecture:** Described mainly through marketing; deep engineering internals not fully public. Resolution rate claims (76% vendor vs 42-67% independent) are disputed.
- **Benchmark figures are time-stamped snapshots:** GPT-5.4, Claude Opus 4.6, Sonnet 4.5 scores are vendor self-reports; the reliable OSWorld anchor is human baseline 72.36%.
- **Staff-level salary/leveling specifics:** Synthesized from job specs and engineering blogs, not a formal leveling rubric.
- **Berkeley MOOC certificate windows:** Past semester certificates are closed; lecture videos remain free at https://llmagents-learning.org/ and https://rdi.berkeley.edu/advanced-agentic-ai/. Verify current enrollment before relying on live cohorts.
