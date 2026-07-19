---
course: AI Agent Engineering
code: AG201
type: quiz
semester: 1
week: 1
unit: u1-llm-foundations
title: "Week 1 Quiz — LLM Foundations: The Mental Model"
date: 2026-07-19
grading: Ungated formative check. Scored A/B/C/F against the source.
source: Week 1 readings — Yao "The Second Half", 3Blue1Brown Transformers, Huyen ch. 1–2
---

# Week 1 Quiz: LLM Foundations — The Mental Model

This is a retrieval-and-understanding check on the Week 1 material. Answer in this file,
then reply **done**. No research during the quiz — from memory. Your coding agent should
*not* be used; this is a check on what's in your head.

---

## Q1: What the model actually sees (12 pts)

When you type "Hello, world!" into a chat interface, the model never sees those characters.
(a) What does the model *actually* receive? Walk through the transformation from raw text to
model input. (6 pts)

(b) Why does this transformation matter for agent design? Give one concrete example of
how tokenization can affect agent behavior. (6 pts)

*Your answer:*

---

## Q2: The Q, K, V of attention (15 pts)

Without looking anything up:

(a) Where do Q, K, and V come from? What is the relationship between the input embeddings
and Q/K/V? (5 pts)

(b) Walk through the softmax attention computation in words — no formulas needed.
What does each step do and why? (5 pts)

(c) What would happen if Q and K came from completely different projections (no shared
origin)? Why is the shared origin important? (5 pts)

*Your answer:*

---

## Q3: Multi-head attention (10 pts)

What specific problem does multi-head attention solve that a single attention head cannot?
Give a concrete example of something one head might attend to that another head would miss.
Why is "just make the head bigger" not the answer?

*Your answer:*

---

## Q4: Causal masking (10 pts)

What is causal masking, and where exactly in the attention computation does it happen?
Why is it necessary for autoregressive generation? What would go wrong without it?

*Your answer:*

---

## Q5: Context windows and agent constraints (15 pts)

(a) A model has a 128K-token context window. Your agent's conversation has accumulated:
- 8K tokens of system prompt + tool schemas
- 45K tokens of conversation history (tool calls, observations, reasoning)
- A 20K-token document the agent needs to analyze

The agent needs to make 5 more tool calls before producing a final answer. Roughly
how much "working room" remains, and what happens if you exceed the limit? (8 pts)

(b) Name two strategies engineers use to manage context window pressure in long-running
agent sessions. (7 pts)

*Your answer:*

---

## Q6: Yao's "The Second Half" (8 pts)

Shunyu Yao argues we've entered "the second half" of AI. In one paragraph:

(a) What changed — what defines the shift from "first half" to "second half"? (4 pts)

(b) Why is this framing specifically important for *agent* engineering (as opposed to
model training)? (4 pts)

*Your answer:*

---

## Q7: Self-assessment (ungraded — for my teaching)

How confident are you on each, 1–5?
- Tokenization and what models actually see: _/5
- Q/K/V and the attention computation: _/5
- Multi-head attention: _/5
- Causal masking: _/5
- Context window constraints: _/5
- Yao's "The Second Half" argument: _/5

Which ONE of these do you feel weakest on? (One sentence.)

*Your answer:*

---

**When done:** reply **done** in Telegram. I'll grade this within 24 hours.
This is a *quiz* (formative) — it won't gate your advancement, but it feeds your
grade and tells me what to reinforce.

*Total: 70 pts. Scoring: A ≥ 85% (60 pts), B ≥ 70% (49 pts), C ≥ 55% (39 pts), F < 55%.*
