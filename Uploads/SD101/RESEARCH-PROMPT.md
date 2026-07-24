# System Design Engineering — Deep Research Brief

**Goal:** Design a world-class curriculum in system design for large-scale distributed systems — from fundamentals to staff-level architectural judgment. The learner aims to be among the best in the field.

**Context:** The learner is an AI agent engineer who can already code and reason about systems. They need a rigorous, practically-grounded course. The end goal: design systems like URL shorteners, chat apps, news feeds, and real-time platforms with precise reasoning about tradeoffs, scalability, and reliability. Everything must cite real sources — books, papers, courses, and the engineers who set the standard.

---

## Six Research Targets

### a. Canonical Curriculum
Map the standard system design curriculum across top universities (MIT, Stanford, CMU, Berkeley, Waterloo), top company interview loops (Google, Meta, Amazon, Stripe), and the most recommended online courses. What are the absolute must-cover topics, in what order? Include distributed systems theory courses AND practical system design interview preparation.

### b. The Excellence Bar
What distinguishes a staff-level system designer from a senior? What do the best — people who design systems at Google, Meta, AWS, Stripe, Cloudflare — actually know and do? What does "architectural judgment" mean at the highest level? What gets someone promoted to staff+ in infrastructure/platform roles?

### c. Expert Practices
How do the best system designers actually work? What is their process for:
- Approaching a new design problem cold
- Reasoning about tradeoffs (not just listing pros/cons)
- Estimating capacity, throughput, latency
- Evaluating whether a system design is correct before building
- Communicating designs to peers and leadership

### d. The Frontier
What are the hardest problems in system design today (2025–2026)? What's shifting — AI-native architectures, edge computing, WebAssembly, Rust in infra, serverless evolution, distributed SQL, streaming databases, foundational models as infrastructure? What do new system designers need to know that wasn't standard five years ago?

### e. Staying Current
Who are the people, communities, papers, conferences, blogs, and newsletters that the best system designers follow? Map the ecosystem: Twitter/X accounts, engineering blogs, papers (SOSP, OSDI, NSDI, VLDB, SIGMOD), conferences, Discord/Slack communities, newsletters (e.g., ByteByteGo, Quastor, Designing Data-Intensive Applications reading groups).

### f. Best Materials Per Unit
For each major topic area, identify the single best learning resource regardless of cost — textbook, course (Coursera, edX, MIT OCW, Udemy, etc.), paper, or video series. Include specific chapters/lectures. Be opinionated: if one resource is clearly superior, say so and explain why.

---

**Format:** Return a structured report with one section per target. Every claim must cite a specific source (URL, paper title, book chapter). Flag confidence (high/medium/low) for each major finding. End with an "Open Questions / Couldn't Verify" section.

**Depth:** This should be thorough enough to design a 12-week intensive course from it. Assume the learner will build real systems during the course — the curriculum must balance theory with hands-on practice.
