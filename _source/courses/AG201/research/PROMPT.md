# Deep Research Brief: AI Agent Engineering — From Scratch to Frontier

**Course:** AG201 — AI Agent Engineering  
**Learner goal:** Design and build large-scale AI agents at the level of Manus, Hermes, Fin.AI.  
**Starting point:** From scratch (no prior agent/LM experience).  
**Time budget:** ~21h/week, steady thorough depth-first mastery.  
**Target bar:** Senior/staff-level agent engineer — able to design, build, and reason about agent systems at the frontier.

---

## Research Target A — Canonical Curriculum

What is the emerging standard curriculum for AI agent engineering? Research:

1. **University courses** — find the best agent/AI-engineering courses from top CS departments (Stanford, MIT, Berkeley, CMU, etc.). Look for syllabi covering LLM agents, tool use, multi-agent systems, autonomous systems.
2. **Industry training** — DeepLearning.AI's agent courses, Anthropic's agent documentation and cookbooks, OpenAI's agent SDK docs, LangChain/LangGraph academy.
3. **Standard textbooks** — what are the canonical books on: LLMs, agent architectures, reinforcement learning for language agents, prompt engineering, evaluation?
4. **What order?** For someone starting from scratch, what's the proven dependency order? (Python fundamentals → LLM basics → prompt engineering → tool calling → agent loops → multi-agent → production systems)

## Research Target B — The Excellence Bar

What distinguishes the *best* AI agent engineers from the competent ones? Research:

1. What do top companies (Anthropic, OpenAI, Google DeepMind, top startups building agents) look for in senior/staff agent engineers?
2. What knowledge gaps separate a "can use LangChain" engineer from one who can design a Hermes-level agent system?
3. What would a Staff-level agent engineer be able to do that a mid-level one cannot?
4. What open-source agent projects (Manus, OpenHands, SWE-Agent, etc.) demonstrate excellence in architecture — and what makes their designs excellent?

## Research Target C — Expert Practices

How do the best agent engineers actually work? Research:

1. What's the development workflow for building a production agent? (local dev → eval → observability → deploy → iterate)
2. How do frontier teams test and evaluate agents? What metrics matter beyond pass/fail?
3. What debugging/observability tools do the best use? (LangSmith, LangFuse, Braintrust, Weave, etc.)
4. How do expert agent engineers think about reliability, safety, and guardrails?
5. What are the common failure modes the best engineers know to preempt?

## Research Target D — The Frontier

What's the current state of the art and where is it heading? Research:

1. **Current SOTA architectures:** What are the dominant paradigms in 2025-2026? (ReAct, Plan-and-Execute, multi-agent orchestration, code-execution agents, computer-use agents)
2. **Key papers (last 12 months):** What are the most important agent papers since mid-2025? (SWE-bench results, agentic reasoning breakthroughs, new frameworks)
3. **Where is it heading?** What are the open problems? What will agent engineering look like in 12-24 months?
4. **Production systems to study:** What are the best documented large-scale agent deployments? How do they handle reliability, latency, cost?

## Research Target E — Staying Current

What are the living sources an agent engineer must follow to stay at the frontier? Research:

1. **People to follow:** Who are the key researchers and engineers shaping agent architectures? (on X/Twitter, blogs, etc.)
2. **Papers venues:** Which conferences, workshops, and arXiv categories consistently publish the best agent work?
3. **Communities:** Discord servers, forums, GitHub orgs where the best agent engineers congregate.
4. **Newsletters / blogs:** Which ones consistently cover agent engineering at depth?
5. **Podcasts / talks:** Best long-form content on agent architecture and engineering.

## Research Target F — Best Materials Per Unit (Regardless of Cost)

For a from-scratch, fundamentals-first curriculum, find the absolute best learning resource for each likely unit area. Sweep every platform: Coursera, edX, Udemy, Udacity, DeepLearning.AI, fast.ai, MIT OCW, YouTube, textbooks, documentation, GitHub repos, and research papers. For EACH, name:
- The specific resource (with locator: chapter, lecture, module)
- The platform / cost
- Why it's the best for that specific topic

**Likely unit areas to cover (research what's actually best — don't be constrained by this list):**

| Area | Best Resource | Platform | Cost | Why Best |
|------|--------------|----------|------|----------|
| Python for AI/ML | | | | |
| LLM fundamentals (transformers, attention) | | | | |
| Prompt engineering (structured, few-shot, CoT) | | | | |
| Structured output / function calling | | | | |
| Tool-use architectures | | | | |
| Agent loops (ReAct, planning, reflection) | | | | |
| Memory & context management | | | | |
| RAG (retrieval-augmented generation) | | | | |
| Multi-agent systems & orchestration | | | | |
| Code execution agents (sandboxes, interpreters) | | | | |
| Computer-use / GUI agents | | | | |
| Agent evaluation & benchmarking | | | | |
| Observability, tracing, debugging | | | | |
| Safety, guardrails, alignment for agents | | | | |
| Production deployment (scaling, reliability, cost) | | | | |
| Agentic workflows & business automation | | | | |
| Fine-tuning for agent tasks | | | | |

---

## Deliverable

A single research report covering all six targets, with:
- Every claim cited to a specific source (URL, paper, course page, etc.)
- Confidence ratings (high/medium/low) for each major finding
- An "open questions" section for anything you couldn't verify
- The completed best-materials table above with real findings

Paste this entire prompt into Claude with **Deep Research** enabled. Upload the resulting report to `Uploads/AG201/` in your Obsidian vault — or paste it back to me here.
