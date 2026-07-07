# CS250 — Data Structures & Algorithms

> Solve an unseen Medium LeetCode problem by recognizing its pattern, implementing an optimal solution within ~30 minutes, and stating its time/space complexity as an interviewer expects.

**Credits:** 4  ·  **Domain:** coding-interview  ·  **Prereqs:** none

## Enduring understandings
- Most interview problems are a small set of recurring patterns in disguise.
- The data structure you reach for determines the achievable complexity.
- Naming the invariant is what turns a trick into a transferable skill.

## Grading policy
hw 30% · quiz 15% · exam 20% · midterm 15% · finals 20%

## Weekly schedule, outcomes & readings

### Sem 1 · Week 1 · Arrays & Hashing
- **apply** — Use a hash map/set to achieve O(n) where a brute force is O(n^2), on an assigned array problem.
  - *proof:* AC on the assigned problem + pattern note
- **analyze** — Derive the time/space complexity of a hashing solution and explain the space-for-time trade.
  - *proof:* Derives time/space complexity and why the hash map removes a nested loop

### Sem 1 · Week 2 · Two Pointers
- **apply** — Solve a sorted-array/palindrome problem with two pointers in O(n) time, O(1) space.
  - *proof:* AC + pattern note
- **analyze** — Explain why a sorted invariant enables the two-pointer sweep over a nested loop.
  - *proof:* Explains why sorted input enables O(n) two-pointer over O(n^2)

### Sem 1 · Week 3 · Stack
- **apply** — Use a stack (incl. monotonic stack) to solve a matching/next-greater problem in O(n).
  - *proof:* AC + pattern note

### Sem 1 · Week 4 · Binary Search
- **apply** — Implement binary search (incl. on the answer space) with correct bounds, O(log n).
  - *proof:* AC + pattern note
- **evaluate** — Justify the loop invariant and boundary updates; produce a bug-free lo/hi implementation.
  - *proof:* Justifies the search space + invariant (why lo/hi move correctly), no off-by-one

### Sem 1 · Week 5 · Sliding Window
- **apply** — Solve a substring/subarray optimum with a variable-size sliding window in O(n).
  - *proof:* AC + pattern note

### Sem 1 · Week 6 · Linked List
- **apply** — Manipulate linked lists (reverse, merge, cycle-detect) with O(1) extra space and correct pointers.
  - *proof:* AC + pattern note

### Sem 1 · Week 7 · Trees
- **apply** — Traverse and transform binary trees via DFS/BFS to solve an assigned tree problem.
  - *proof:* AC + pattern note
- **analyze** — Choose BFS vs DFS for a task and justify the choice by what state each carries.
  - *proof:* Chooses BFS vs DFS for a given tree task and justifies it

### Sem 1 · Week 8 · Tries
- **apply** — Implement a trie and use it for prefix/word-search queries.
  - *proof:* AC + pattern note

### Sem 1 · Week 9 · Backtracking
- **apply** — Enumerate subsets/combinations/permutations via backtracking with correct pruning.
  - *proof:* AC + pattern note

### Sem 1 · Week 10 · Heap / Priority Queue
- **apply** — Use a heap to solve top-K / streaming-median / scheduling problems in O(n log k).
  - *proof:* AC + pattern note

### Sem 1 · Week 11 · Semester 1 Finals (cumulative)
- **evaluate** — Solve 2 unseen timed Mediums (AC) drawn from patterns 1–10 and derive their complexity, closed-book.
  - *proof:* 2 unseen timed Mediums AC + complexity derivation (closed-book)

## Assessment plan
- **a.ah.solve** (summative, open_problem, ≥apply) — AC on the assigned problem + pattern note
- **a.ah.cx** (formative, explain, ≥analyze) — Derives time/space complexity and why the hash map removes a nested loop
- **a.tp.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.tp.cx** (formative, explain, ≥analyze) — Explains why sorted input enables O(n) two-pointer over O(n^2)
- **a.st.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.bs.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.bs.cx** (summative, explain, ≥evaluate) — Justifies the search space + invariant (why lo/hi move correctly), no off-by-one
- **a.sw.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.ll.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.tr.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.tr.cx** (formative, explain, ≥analyze) — Chooses BFS vs DFS for a given tree task and justifies it
- **a.tt.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.hp.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.bt.solve** (summative, open_problem, ≥apply) — AC + pattern note
- **a.s1.final** (summative, open_problem, ≥evaluate) — 2 unseen timed Mediums AC + complexity derivation (closed-book)
