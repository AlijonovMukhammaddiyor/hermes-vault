---
course: AI Agent Engineering
code: AG201
type: placement
unit: u1-llm-foundations
title: "Placement: LLM Foundations"
date: 2026-07-19
proof: u1.transformer
time_limit: "No strict limit — aim for 45–60 minutes total"
grading: "≥ B (≥ 80%) to skip the unit; below that, the unit is kept in your plan"
---

# Placement Exam: LLM Foundations

This checks whether you already have conceptual fluency in the transformer architecture —
not implementation skills, but the ability to explain how these systems work from first
principles and connect architecture to agent design constraints.

**If you pass at ≥ B, the u1-llm-foundations unit is skipped and you move straight to
Prompt Engineering. If not, no problem — the unit is already in your plan and we'll work
through it together.**

Answer in this file (edit it in Obsidian), then reply **done**.

---

## Question 1: Attention from First Principles (30 pts)

Without looking anything up, explain the attention mechanism as if teaching a peer:

(a) What are Q, K, and V? Where do they come from, and what does each represent? (10 pts)

(b) Walk through the softmax attention formula step by step. What does each operation do
and why? (10 pts)

(c) What problem does multi-head attention solve that single-head attention cannot? (10 pts)

*Your answer:*

---

## Question 2: The Full Architecture (30 pts)

(a) Draw (describe in text) the complete transformer decoder block. Include and explain:
layer norm, masked self-attention, residual connections, and the feed-forward network.
What is the purpose of each component? (15 pts)

(b) Walk through what happens during a single inference forward pass — from token in to
next-token probability out. Be specific about what's cached and what's recomputed. (15 pts)

*Your answer:*

---

## Question 3: Architecture → Agent Design (25 pts)

(a) Why does decoder-only dominate modern LLMs? What does "decoder-only" actually mean
architecturally, and what advantages does it have over encoder-decoder for the tasks
agents need? (10 pts)

(b) The Bitter Lesson (Sutton, 2019) states that general methods leveraging computation
beat hand-crafted domain knowledge in the long run. How does this principle apply at
the agent-engineering level? Give one concrete example of scaffolding that might become
obsolete as models improve. (10 pts)

(c) How does the context window constrain agent design? Name two specific constraints
and how engineers work around them. (5 pts)

*Your answer:*

---

## Question 4: Self-Assessment (15 pts)

What's your honest confidence level on each sub-topic (1–5)?
- Attention (Q/K/V, softmax): _/5
- Multi-head attention and why it matters: _/5
- Layer norm + residual connections: _/5
- Decoder-only vs encoder-decoder: _/5
- Inference forward pass (KV cache): _/5
- The Bitter Lesson and its implications: _/5

Which of these do you feel WEAKEST on? (One sentence — this helps me teach better.)

*Your answer:*

---

**When done:** reply **done** (or **done** in Telegram) and I'll grade it.
The exam is in your vault at `Exams/AG201/placement-u1.md` — edit it right in Obsidian.
