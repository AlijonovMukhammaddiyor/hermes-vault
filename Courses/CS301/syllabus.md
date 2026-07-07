# CS301 — System Design

> Drive an unseen senior-level system-design interview: clarify scope, do capacity BOTEC, propose a high-level design, and defend real trade-offs and failure modes under time pressure.

**Credits:** 4  ·  **Domain:** system-design  ·  **Prereqs:** none

## Enduring understandings
- Every design is a set of trade-offs; naming them is the senior signal.
- Numbers first (BOTEC) — capacity math drives the design, not the reverse.
- There is no "correct" architecture, only one justified against stated requirements.

## Grading policy
hw 40% · quiz 15% · exam 10% · midterm 15% · finals 20%

## Units & outcomes (the schedule)

### Sem 1 · Unit 1: Fundamentals — delivery framework, BOTEC, CAP, storage, caching, consistency
- **apply** — Apply the 6-step delivery framework (requirements→entities→API→HLD→deep dive) to scope a prompt in time.
  - *proof:* Applies the 6-step delivery framework to scope an assigned prompt within time
- **analyze** — Perform a back-of-envelope capacity estimate (QPS, storage, bandwidth) for a system.
  - *proof:* Produces a correct BOTEC (QPS, storage, bandwidth) for an assigned system
- **evaluate** — Justify a CAP/PACELC + consistency choice for a given workload.
  - *proof:* Justifies a CAP/PACELC + consistency choice for a given workload, defended

### Sem 1 · Unit 2: Core Components — LB, queues, DBs, sharding, replication, CDN
- **evaluate** — Select and justify core components (SQL/NoSQL, cache, queue, sharding, replication) for a scenario.
  - *proof:* Selects DB type/cache/queue/sharding for a scenario and defends the trade-off

### Sem 1 · Unit 3: Key Technologies — Redis, Kafka, Cassandra, Elasticsearch, API Gateway
- **analyze** — Map a technology (Redis/Kafka/Cassandra/ES/API-gateway) to the problem it solves and its trade-offs.
  - *proof:* Maps a technology (Redis/Kafka/Cassandra/ES) to when-and-why it fits

### Sem 1 · Unit 4: Case Studies I — design real systems end-to-end
- **create** — Produce a full HLD for a case-study system (URL shortener, rate limiter, news feed, chat) with BOTEC + a defended trade-off + failure modes.
  - *proof:* Full design doc: requirements + BOTEC + HLD + >=1 defended trade-off + failure modes

### Sem 1 · Unit 5: Semester 1 Finals (cumulative)
- **create** — Design an unseen system end-to-end under time, defended on trade-offs with a correct BOTEC, closed-book.
  - *proof:* 1 timed full design of an unseen system, defended on trade-offs with BOTEC (closed-book)
