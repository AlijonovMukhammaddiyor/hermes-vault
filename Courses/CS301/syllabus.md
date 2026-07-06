# CS301 — System Design (4 credits)

## Outcomes
Drive an unseen system-design interview at FAANG-senior bar: clarify scope, do back-of-envelope
capacity math (BOTEC), propose a high-level design, defend real trade-offs, and reason about
failure modes.

## Sources (blend)
- Spine: **Hello Interview** (delivery framework).
- Breadth: **Alex Xu / ByteByteGo**, **Grokking the System Design Interview**.
- Depth: **DDIA** (Designing Data-Intensive Applications).
- Talks: **Jordan Has No Life**, **Gaurav Sen**.

## Units (unlock in order)
1. Fundamentals — the delivery framework, BOTEC, CAP/PACELC, storage models, caching, consistency.
2. Core components — load balancers, queues, databases (SQL/NoSQL), sharding, replication, CDNs.
3. Case studies — design real systems (URL shortener, rate limiter, news feed, chat, etc.).
4. Timed mocks — full designs under interview time pressure.

## Grade weights
Designs 50 · Quiz 20 · Midterm 30.

## Rubric (4 × 3 pt)
- Problem Navigation — clarifying questions, scoping, requirements (functional + non-functional).
- Solution Design — HLD, component choices, data model, API.
- Technical Excellence — BOTEC correctness, bottleneck analysis, scaling, consistency/availability calls.
- Communication — structured narration, trade-off articulation as in an interview.

## Proof of work
A **design doc** in `Courses/CS301/designs/<topic>.md` containing an explicit **BOTEC** and at
least **one real trade-off** (option A vs B, why chosen). No BOTEC or no trade-off ⇒ not proven.
