# AI Agent Engineering: A From-Scratch-to-Frontier Curriculum & Mastery Roadmap

## TL;DR
- **The fastest proven path to staff-level agent design mastery is a concept-first sequence:** Chip Huyen's *AI Engineering* (O'Reilly, 2025) + Anthropic's engineering essays for the mental models → UC Berkeley's CS294 "LLM Agents / Agentic AI" MOOC lecture series for breadth → deep study of production write-ups from Anthropic (multi-agent research system), Manus (context engineering), and OpenHands/SWE-agent (coding agents) for architecture, all anchored by building an eval + observability discipline. Because the learner already has a coding agent, weight everything toward *why/how systems are designed*, not step-by-step build tutorials.
- **The bar that separates "can use LangChain" from "can design a Fin/Manus-level system" is context engineering, evaluation rigor, and reliability engineering** — KV-cache economics, failure-mode preemption, trajectory-level evals, and reasoning about when NOT to add complexity — not framework fluency.
- **At ~21h/week, plan ~9–12 months to reach senior/staff conceptual capability.** Front-load LLM + prompting + tool-calling fundamentals (months 1–3), then agent loops/memory/RAG/multi-agent (months 4–7), then frontier topics — computer-use, RL for agents, production deployment, safety (months 8–12) — while continuously reading frontier papers and production post-mortems.

## Key Findings

**1. The canonical academic anchor is UC Berkeley's LLM Agents MOOC series (Dawn Song & Xinyun Chen).** It runs as a public MOOC with full lecture videos: Fall 2024 "Large Language Model Agents" (CS294/194-196), Spring 2025 "Advanced LLM Agents" (CS294/194-280), and Fall 2025 "Agentic AI" (CS294-196). Site: llmagents-learning.org. This is the single best free, structured, guest-lecture-driven survey of the whole agent landscape (foundations, reasoning, planning, tool use, code generation, multimodal agents, safety). *Confidence: High.*

**2. For deep LLM foundations, Stanford CS336 "Language Modeling from Scratch" (Spring 2025, ~22h of lectures on YouTube) is the gold standard** — but it is implementation-heavy and may be more than the learner needs given the "understand, don't build" emphasis. A lighter conceptual alternative is Stanford CME 295 "Transformers & LLMs." Stanford CS329A "Self-Improving AI Agents" (Fall 2025 graduate seminar) is the most frontier-oriented university course, covering constitutional AI, verifiers, test-time compute, tool use, memory, and multi-agent evaluation. *Confidence: High.*

**3. Chip Huyen's *AI Engineering: Building Applications with Foundation Models* (O'Reilly, 2025) is the best single textbook** for this learner. Chapter 6 ("RAG and Agents") and Chapter 5 (Prompt Engineering) directly cover the material; Chapter 4 (Evaluate AI Systems) and Chapter 10 (AI Engineering Architecture) build the production/eval judgment that separates senior engineers. It is prose-based (no code), which fits the conceptual emphasis. *Confidence: High.*

**4. Anthropic's engineering blog is the highest-signal free resource for architectural reasoning.** The essential reading set: "Building Effective Agents" (Schluntz & Zhang), "How we built our multi-agent research system," "Effective context engineering for AI agents," "Effective harnesses for long-running agents," and "When to use multi-agent systems (and when not to)." These teach the design tradeoffs (workflows vs. agents, orchestrator-worker patterns, context rot, the artifact pattern) that frontier teams actually use. *Confidence: High.*

**5. The dominant 2025–2026 SOTA paradigms are: the augmented-LLM-in-a-loop (ReAct lineage), orchestrator-worker multi-agent (Anthropic Research), code-execution agents (CodeAct/OpenHands), computer-use/GUI agents (Claude Computer Use, OpenAI CUA/Operator, Gemini Computer Use), and context-engineered long-horizon agents (Manus).** Coding agents on SWE-bench Verified went from <2% (2023) to >70% by late 2025; per the Live-SWE-agent leaderboard (live-swe-agent.github.io, Nov 24, 2025), "Claude Opus 4.5 + Live-SWE-agent scores 79.2% on SWE-bench Verified, leading all current open-source scaffolds and coming very close to Anthropic's internal, manually engineered scaffold for Opus 4.5" (Gemini 3 Pro + Live-SWE-agent scored 77.4%, Nov 20, 2025). *Confidence: High.*

## Details

### RESEARCH TARGET A — Canonical Curriculum

**University courses (best-in-class, with locators):**
- **UC Berkeley CS294/194 LLM Agents MOOC** (Dawn Song, Xinyun Chen of Google DeepMind). Three semesters publicly available at llmagents-learning.org: F24 foundations, Sp25 "Advanced LLM Agents" (reasoning, inference-time techniques, search/planning, code, math), F25 "Agentic AI." Full lecture videos on YouTube. Guest lecturers include Jason Weston (self-rewarding LLMs) and Yann Dubois (agent overview). *This is the recommended structured spine.*
- **Stanford CS336 "Language Modeling from Scratch"** (Spring 2025 archive + Spring 2026). ~22 hours of lectures on YouTube covering tokenization, architectures, MoE, GPUs/Triton, parallelism, scaling laws (Lec 9, 11), inference (Lec 10), evaluation (Lec 12), data. Optional deep dive — heavy on implementation.
- **Stanford CS329A "Self-Improving AI Agents"** (Fall 2025 graduate seminar): constitutional AI, verifiers, scaling test-time compute, search + LLMs, RL, tool use/code/memory, multi-agent, robust evaluation.
- **Stanford CME 295 "Transformers & LLMs"** — lighter conceptual transformer/LLM course with a public cheatsheet.
- **CMU CS 11-711 "Advanced NLP"** (Graham Neubig). Fall 2024: phontron.com/class/anlp-fall2024/; Spring 2025 adaptation at cmu-l3.github.io/anlp-spring2025/. Full lecture videos on YouTube ("CMU Advanced NLP Fall 2024" playlist). Strong for neural/LLM methods and a research-reimplementation capstone. (Note: a distinct CMU "11-868 LLM agents" course could not be verified.)

**Industry training:**
- **DeepLearning.AI "Agentic AI"** (Andrew Ng, launched Oct 2025) — vendor-neutral, raw-Python, teaches four design patterns (Reflection, Tool Use, Planning, Multi-agent) with heavy emphasis on **evals and error analysis** as the biggest predictor of success. Best single industry course for this learner's goal. Pro membership ~$30/mo monthly / ~$25/mo annual; auditable free without certificate.
- **DeepLearning.AI "AI Agentic Design Patterns with AutoGen"** (Chi Wang, Qingyun Wu — AutoGen creators) and **"AI Agents in LangGraph"** (Harrison Chase, Rotem Weiss).
- **Anthropic**: "Building Effective Agents" essay + resources hub PDF ("Architecture Patterns and Implementation Frameworks"); claude-cookbooks (github.com/anthropics/claude-cookbooks, patterns/agents); context-engineering cookbook (compaction, tool-result clearing, memory).
- **OpenAI**: "A Practical Guide to Building Agents" (PDF), Agents SDK docs, Computer-Using Agent / Operator system card.
- **LangChain/LangGraph Academy**; **Hugging Face Agents Course** (huggingface.co/learn/agents-course).

**Standard textbooks / canonical references:**
- Chip Huyen, *AI Engineering* (O'Reilly, 2025) — primary text.
- Lilian Weng, "LLM Powered Autonomous Agents" (lilianweng.github.io, 2023) — canonical free deep-dive on planning/memory/tool-use; still the most-cited agent primer.
- Foundational papers (read as a set): ReAct (Yao et al., arXiv:2210.03629), Reflexion (Shinn et al., NeurIPS 2023, 2303.11366), Toolformer (Schick et al., 2302.04761), Tree of Thoughts (Yao et al., 2305.10601), Voyager (Wang et al., 2305.16291), Generative Agents (Park et al., 2304.03442), MemGPT (Packer et al., 2310.08560), Cognitive Architectures for Language Agents (Sumers & Yao, TMLR 2024).
- Latent Space "2025 AI Engineering Reading List" (50 papers/blogs across 10 fields) — excellent curated starting point.

**Proven dependency order (from scratch):** Python fluency (enough to read/reason about code) → LLM fundamentals (transformers, attention, sampling, context windows) → prompt engineering (zero/few-shot, CoT, structured output) → structured output / function calling → tool-use architectures → agent loops (ReAct → planning → reflection) → memory & context management → RAG → multi-agent orchestration → code-execution & computer-use agents → evaluation & observability → safety/guardrails → production deployment (scaling, latency, cost) → (optional) fine-tuning/RL for agents. This mirrors both the Berkeley MOOC progression and Huyen's chapter ordering.

### RESEARCH TARGET B — The Excellence Bar

**What top companies look for (senior/staff agent engineers):** The 2026 hiring signal has shifted decisively away from the "LangChain + Pinecone resume." The differentiated skills are: agent orchestration, eval design, MCP integration, production observability/tracing, cost optimization at scale, safety/guardrails, computer-use deployment, and frontier-model fluency. **Eval literacy is repeatedly cited as the single best signal of real experience.** The "trust gap" (developers use AI tools but distrust output) makes candidates who demonstrate eval rigor and failure-mode intuition far more valuable. Frontier-lab senior agent roles pay roughly $300K–$550K total comp; per Glassdoor (as of May 2026), the average Agentic AI Engineer salary is $192,826/yr, with a typical range of $152,427 (25th pct) to $247,443 (75th pct) and a 90th-percentile of $307,216. A recurring theme: hire for "measurable, boring, dependable systems," since per Gartner's June 25, 2025 press release, "over 40% of agentic AI projects will be canceled by the end of 2027, due to escalating costs, unclear business value or inadequate risk controls" (Gartner also estimates only ~130 of thousands of self-described "agentic" vendors are real — "agent washing").

**The knowledge gap ("can use LangChain" vs. "can design a Fin/Manus-level system"):**
- *Context engineering* — treating the context window as a finite, degrading resource; KV-cache hit-rate as the primary cost/latency metric; append-only stable prefixes; compaction, offloading to filesystem, isolation via subagents (Manus's six principles from "Context Engineering for AI Agents: Lessons from Building Manus").
- *Reliability engineering* — understanding compounding error (95% per-step accuracy → ~60% over 10 steps, ~8% over 50 steps), and designing to cap the "blast radius."
- *Evaluation systems* — end-state vs. turn-by-turn evaluation, LLM-as-judge aligned to humans, trajectory-level grading, error analysis as the highest-ROI activity.
- *Architectural judgment* — knowing when a single agent + better prompt beats a multi-agent system (Anthropic: teams spent months on multi-agent architectures that better single-agent prompting matched).

**What a staff-level engineer can do that a mid-level cannot:** Decompose a fuzzy business goal into an eval spec; diagnose whether a plateau is context-bound vs. prompt-bound; choose the right coordination pattern for the task shape; design the harness/environment for long-horizon work (initializer agent + progress artifacts); and reason about cost/latency/reliability tradeoffs. Per Anthropic's "How we built our multi-agent research system," in their browsing evaluations "three factors explained 95% of the performance variance," with token usage alone explaining ~80% (tool-call frequency and model choice made up the rest) — a diagnostic a staff engineer uses to decide that a plateau is context-bound rather than a prompt-polishing problem. The same write-up notes multi-agent systems use ~15× more tokens than chat, justified only for parallelizable breadth-first tasks.

**Open-source projects demonstrating architectural excellence:**
- **SWE-agent** (Princeton/Stanford, NeurIPS 2024) — introduced the **Agent-Computer Interface (ACI)**, the seminal idea that carefully designed agent-facing commands materially change performance. Mini-SWE-agent reaches >74% on SWE-bench Verified in ~100 lines of Python.
- **OpenHands** (formerly OpenDevin) — event-stream architecture (Agent → Actions → Environment → Observations), Docker-sandboxed execution, CodeAct unified action space. The OpenHands Software Agent SDK (arXiv:2511.03690) is a strong study in stateless, event-sourced, composable production design (72% SWE-bench Verified with Claude Sonnet 4.5 + extended thinking).
- **Manus** — "Context Engineering for AI Agents: Lessons from Building Manus" (Yichao "Peak" Ji) documents four full framework rewrites and the economics of production agents at scale.
- **Anthropic multi-agent research system** — the cleanest public orchestrator-worker + CitationAgent design write-up.
- **LangChain Open SWE** (built on Deep Agents + LangGraph) — captures convergent patterns (isolated sandboxes, curated toolsets, subagent orchestration) that Stripe, Ramp, and Coinbase independently arrived at.

### RESEARCH TARGET C — Expert Practices

**Development workflow:** local dev → build evals early (start with a handful of examples, not hundreds) → add tracing/observability → deploy with checkpointing/retry/rainbow deployments → iterate via error analysis. Andrew Ng and Anthropic both stress that a disciplined **eval + error-analysis loop** is the biggest predictor of who builds effective agents.

**Testing/eval — metrics that matter beyond pass/fail:** trajectory-level correctness (tool-call arguments, state propagation, goal-alignment drift) — final-output-only evals overstate pass rates; end-state evaluation for state-mutating agents; LLM-as-judge validated against human judgment; source-quality heuristics (Anthropic found early agents preferred SEO content farms over authoritative sources). Token usage, tool-call count, and cost should be treated as first-class metrics. Canonical eval reading: Hamel Husain "Your AI Product Needs Evals" and "A Field Guide to Rapidly Improving AI Products"; Eugene Yan "An LLM-as-Judge Won't Save the Product"; Shreya Shankar et al. "Who Validates the Validators?"; benchmarks τ-bench (tool-agent-user, Yao et al., ICLR 2025), SWE-bench Verified, GAIA, OSWorld.

**Observability/debugging tools (2026 landscape):** LangSmith (best for LangChain/LangGraph stacks, deep tracing), Langfuse (best open-source self-host, MIT; acquired by ClickHouse Jan 2026), Braintrust (eval-first, CI/CD regression gates), Weights & Biases Weave (for W&B-native ML teams), Arize Phoenix (OpenTelemetry-native), plus newer agent-first entrants (Laminar, Latitude). Rule of thumb: LangSmith if committed to LangGraph, Langfuse for open-source control, Braintrust if the bottleneck is regression testing.

**Reliability, safety, guardrails:** input guardrails (PII, prompt injection) and output guardrails (malformed/unsafe responses); least-privilege sandboxing (Anthropic recommends VMs/containers for computer use); escalation-to-human on low confidence (Fin's design); OWASP LLM Top 10 as the security checklist. Anthropic's framing: "as agents grow more capable, so does their potential blast radius — the engineering question is how to cap it."

**Common failure modes the best preempt:** compounding errors over long trajectories; context rot (accuracy degrades as the window fills — n² attention); over-spawning subagents; redundant tool calls; game-of-telephone information loss between agents (solved by the artifact pattern — write to shared filesystem, pass references); premature fine-tuning (Manus deliberately avoided it, having learned fine-tuned models became obsolete when better foundation models shipped); over-engineering multi-agent systems where a single agent suffices.

### RESEARCH TARGET D — The Frontier

**Current SOTA architectures (2025–2026):** ReAct-style tools-in-a-loop remains the base; Plan-and-Execute and reflection layered on top; orchestrator-worker multi-agent for breadth-first tasks; CodeAct/code-execution agents; computer-use/GUI agents; and context-engineered long-horizon agents. **Model Context Protocol (MCP)** — created by Anthropic (David Soria Parra, Justin Spahr-Summers), announced Nov 25, 2024 — has become the de-facto standard for connecting agents to tools/data via JSON-RPC (host/client/server; Resources, Tools, Prompts primitives). It solves the M×N integration problem, has been adopted across the industry (including OpenAI and Google DeepMind), and was donated to a Linux Foundation fund in Dec 2025. Official docs: modelcontextprotocol.io. This is now core knowledge for any agent engineer.

**Key results/papers (mid-2025 → 2026):**
- SWE-bench Verified: Claude Opus 4.5 + Live-SWE-agent 79.2% (Nov 24, 2025, live-swe-agent.github.io); Gemini 3 Pro 77.4%; Claude Sonnet 4.5 self-reported 77.2% (Anthropic release: "77.2% on SWE-bench Verified and 61.4% on OSWorld for computer use"). Adversarial re-testing (SWE-ABS) shows ~16–18% drops, revealing benchmark fragility.
- Computer use: OSWorld climbed from 12.24% (best model at 2024 launch, vs. 72.36% human) to Claude Sonnet 4.5 at 61.4% (Sep 2025); WebVoyager saturated above 90%. Reliability caveat: cross-app OSWorld workflows still ~12–20%; no major player trusts agents with irreversible financial actions.
- Agentic RL is a major research thrust: "The Landscape of Agentic Reinforcement Learning for LLMs: A Survey" (arXiv:2509.02547, Zhang et al.), plus Search-R1, ReTool, ARTIST, and outcome-based-reward training recipes.
- Shunyu Yao's essay "The Second Half" (Apr 10, 2025, ysymyth.github.io/The-Second-Half/) is the canonical framing of the frontier shift: "the second half of AI — starting now — will shift focus from solving problems to defining problems. In this new era, evaluation becomes more important than training."

**Where it's heading (12–24 months, per current writing — flagged as forward-looking):** asynchronous multi-agent orchestration; better long-horizon harnesses and memory; self-improving agents (Lilian Weng's July 2026 "Harness Engineering for Self-Improvement"); more reliable computer-use; RL-trained agentic models; and a persistent open problem of evaluation/reliability at scale.

**Best-documented large-scale deployments (the closest public analogs to the learner's Manus/Hermes/Fin target):**
- **Anthropic Research** — orchestrator-worker; per "How we built our multi-agent research system," "a multi-agent system with Claude Opus 4 as the lead agent and Claude Sonnet 4 subagents outperformed single-agent Claude Opus 4 by 90.2% on our internal research eval," at ~15× the tokens of a chat interaction.
- **Manus** — KV-cache economics, filesystem as externalized context, four framework rewrites ("Stochastic Graduate Descent"), millions of users.
- **Fin by Intercom** — six-layer proprietary engine with fin-cx-retrieval/fin-cx-reranker models; per Intercom's "From resolutions to outcomes," "our average resolution rate across customers has increased every month and now stands at 76%," and fin.ai states Fin is "battle-tested across billions of customer conversations, with 99.97% uptime" (note: other Fin materials cite a 67% average and a 99.8% SLA), with escalation-to-human when safety parameters aren't met.

### RESEARCH TARGET E — Staying Current

**People to follow:** Lilian Weng (lilianweng.github.io — agents, reasoning, self-improvement); Shunyu Yao (ReAct/SWE-bench/tau-bench author; "The Second Half"); Hamel Husain & Shreya Shankar (evals); Simon Willison (weblog, practical agent analysis); Andrej Karpathy; Harrison Chase (LangChain); Chip Huyen; Nathan Lambert (Interconnects — post-training/RL); Jason Wei ("Verifier's Law"); Eugene Yan; Han-Chung Lee (agent eval infra).

**Paper venues / categories:** NeurIPS, ICLR, ICML, ACL, COLM; arXiv cs.CL, cs.AI, cs.LG, cs.MA; workshops on LLM agents, computer-use agents, agentic RL. Curated hubs: FoundationAgents/awesome-foundation-agents, benchflow-ai/awesome-evals, EthicalML/awesome-agentic-engineering-resources, blacksnail789521/Agentic-RL-Training-Recipes.

**Communities:** Latent Space Discord (very active, weekly LLM Paper Club); LangChain community; Hugging Face; framework-specific Discords; GitHub orgs (OpenHands, SWE-agent/Princeton NLP, Anthropic cookbooks).

**Newsletters/blogs (at depth):** Latent Space (swyx — the canonical AI-engineer publication, weekly essays + daily AINews); Interconnects (Nathan Lambert); Import AI (Jack Clark); The Sequence; AI Tidbits; Anthropic & OpenAI engineering blogs; The Batch (DeepLearning.AI).

**Podcasts/talks:** Latent Space Podcast (top-10 US Tech; deep technical guest interviews); Dwarkesh Podcast (AI-heavy long-form); ThursdAI; the Berkeley LLM Agents MOOC guest lectures on YouTube.

### RESEARCH TARGET F — Best Materials Per Unit

| Unit area | Best resource (with locator) | Platform / cost | Why it's best |
|---|---|---|---|
| Python for AI/ML | *Python for Data Analysis* (McKinney) + official Python docs; light — learner already has a coding agent | Book / free | Enough to read & reason about agent code without a build-heavy course |
| LLM fundamentals (transformers, attention) | Stanford CS336 lectures 1–3 (tokenization, architectures) + 3Blue1Brown "Transformers/Attention" for intuition; Karpathy "Deep Dive into LLMs like ChatGPT" | YouTube / free | CS336 is the most rigorous; Karpathy gives the fastest strong mental model |
| Prompt engineering (structured, few-shot, CoT) | Huyen *AI Engineering* Ch. 5 + Anthropic Prompt Engineering interactive tutorial + Lilian Weng "Prompt Engineering" | Book + free | Concept-first + hands-on taxonomy from frontier labs |
| Structured output / function calling | Anthropic tool-use docs + OpenAI function-calling docs; Huyen Ch. 6 | Free | Primary-source specs; the actual API contracts agents rely on |
| Tool-use architectures | ReAct paper (2210.03629) + Toolformer (2302.04761) + Anthropic "Building Effective Agents" (tools section) | Free | Foundational designs + production framing |
| Agent loops (ReAct, planning, reflection) | Lilian Weng "LLM Powered Autonomous Agents" + Reflexion (2303.11366) + Tree of Thoughts (2305.10601) + DeepLearning.AI "Agentic AI" | Free / ~$30 mo | The canonical loop primer + the four design patterns |
| Memory & context management | Anthropic "Effective context engineering for AI agents" + Manus "Context Engineering" (Peak Ji) + MemGPT (2310.08560) | Free | The two best production write-ups + the OS-analogy paper |
| RAG | Huyen *AI Engineering* Ch. 6 + original RAG paper (Lewis et al., 2020) + Gao et al. RAG survey; Jason Liu "RAG is more than embedding search" | Book / free | Systems view (retrieval, reranking, eval), not just vector search |
| Multi-agent systems & orchestration | Anthropic "How we built our multi-agent research system" + "When to use multi-agent systems (and when not to)" | Free | Best public orchestrator-worker case study + honest when-not-to guidance |
| Code execution agents (sandboxes, interpreters) | SWE-agent paper (ACI) + OpenHands SDK paper (2511.03690) + CodeAct | Free | The seminal ACI concept + a production-grade composable SDK |
| Computer-use / GUI agents | OpenAI "Computer-Using Agent" + Anthropic Computer Use docs + OSWorld paper (NeurIPS 2024) + MarkTechPost explainer | Free | Primary sources + the standard benchmark + a synthesis explainer |
| Agent evaluation & benchmarking | Hamel Husain "Your AI Product Needs Evals" + "A Field Guide…" + τ-bench + SWE-bench + benchflow-ai/awesome-evals | Free | The canonical eval essays + real agent benchmarks |
| Observability, tracing, debugging | LangSmith docs (LangGraph stacks) or Langfuse (open-source) + MLflow/Arize comparison guides | Free / freemium | Match tool to stack; hands-on tracing is the core skill |
| Safety, guardrails, alignment for agents | OWASP LLM Top 10 + Anthropic safety/engineering essays + Berkeley MOOC safety lectures | Free | Industry-standard threat model + frontier-lab practice |
| Production deployment (scaling, reliability, cost) | Manus context-engineering posts (KV-cache economics) + Huyen Ch. 9–10 + Anthropic "Effective harnesses for long-running agents" | Free / book | The economics + architecture of running agents at scale |
| Agentic workflows & business automation | DeepLearning.AI "Agentic AI" (Andrew Ng) + Anthropic "Building Effective Agents: Architecture Patterns" PDF | ~$30 mo / free | Decomposing business processes into patterns; eval-driven |
| Fine-tuning for agent tasks | DeepLearning.AI "Fine-tuning & RL for LLMs: Intro to Post-training" (Sharon Zhou) + "The Landscape of Agentic RL for LLMs" survey (2509.02547) | Freemium / free | Best conceptual post-training course + the SOTA agentic-RL map |

## Recommendations

**Stage 1 (Months 1–3, foundations):** Read Huyen *AI Engineering* cover-to-cover (it is prose and fits the concept-first goal). In parallel, watch Berkeley LLM Agents MOOC F24/F25 lectures and Karpathy's "Deep Dive into LLMs." Read all of Anthropic's core engineering essays. Build one tiny agent from scratch (no framework) just to internalize the loop — then stop building tutorials. **Threshold to advance:** you can explain, from memory, the augmented-LLM loop, why compounding error matters, and the workflow-vs-agent distinction.

**Stage 2 (Months 4–7, core architecture):** Work through agent loops → memory/context → RAG → multi-agent using the papers and production write-ups in the table. Do a close read of SWE-agent and OpenHands source/papers as architecture case studies. **Start an eval discipline now**: set up LangSmith or Langfuse, instrument a project, and practice error analysis on real traces. Take DeepLearning.AI "Agentic AI." **Threshold:** you can design an orchestrator-worker system on paper, justify the coordination pattern, and specify its eval harness and failure modes.

**Stage 3 (Months 8–12, frontier & depth):** Computer-use agents, agentic RL (survey 2509.02547 + post-training course), production deployment economics (Manus posts), and safety. Read one frontier paper per week and one production post-mortem per week. Study Fin/Manus/Anthropic deployments as your target-analog references. **Threshold:** you can critique a frontier agent system's design choices (context strategy, eval, cost, reliability) and propose improvements.

**Ongoing:** Subscribe to Latent Space (+ AINews) and Interconnects; follow Weng, Yao, Husain, Willison; join the Latent Space Discord + Paper Club. Re-read "The Second Half" and Anthropic's context-engineering essay quarterly as the field moves.

**Benchmarks that would change the plan:** If you find fundamentals trivial, compress Stage 1 to ~4 weeks and go straight to the production write-ups. If you struggle to reason about traces, slow down and spend extra weeks purely on eval/observability — it is the highest-leverage skill for the target level. If your goal narrows to coding agents specifically, weight SWE-agent/OpenHands and SWE-bench far more heavily.

## Caveats & Open Questions
- **"Hermes-level" is ambiguous.** There are multiple "Hermes" agent products/models; no single authoritative public architecture write-up was located, so this report treats Manus, Anthropic Research, and Fin as the concrete, well-documented large-scale analogs. *Confidence: Medium on this being the right analog set.*
- **Benchmark numbers move weekly and vendor self-reports vary** (e.g., SWE-bench Verified scores differ by scaffold; OSWorld comparisons are muddied by the OSWorld vs. OSWorld-Verified revision). Treat all leaderboard figures as time-stamped snapshots, and note some third-party vendor blogs (e.g., Coasty's 82% OSWorld claim) are self-promotional and unverified. *Confidence: High that the trajectory is real; Medium on any single figure.*
- **Fin's headline metrics are self-reported by Intercom and inconsistent across its own materials** (76% vs. 67% resolution; 99.97% uptime vs. 99.8% SLA). Treat as directional, not audited. *Confidence: Medium.*
- **Forward-looking "where it's heading" claims** are drawn from current expert writing and are inherently speculative.
- **Shunyu Yao's current employer** is contested in 2025–2026 sources (OpenAI at the time of "The Second Half," where he worked on Operator and Deep Research; later reports of a move to Tencent as Chief AI Scientist). Verify before citing. *Confidence: Medium.*
- **Some course offerings rotate**; confirm current-semester availability and whether videos are posted before committing time. A distinct CMU "11-868 LLM agents" course could not be verified — treat CMU 11-711 "Advanced NLP" as the confirmed option.