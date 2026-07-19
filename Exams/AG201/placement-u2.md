# AG201 Placement Exam — U2: Prompt Engineering & Structured Output

**Instructions:** This exam tests whether you can skip U2. You need ≥ B (80%) to place out.
Use your coding agent to run the prompts — you design them, the agent executes. Answer all parts.

---

## Part 1: Design (40%)

**Task:** Classify customer support tickets by urgency (low/medium/high) and category (billing/technical/account/other).

Design **3 prompts** of escalating quality for this task:

1. **Naive prompt** — the first thing someone might write
2. **Improved prompt** — with system message and output format constraints
3. **Best prompt** — add few-shot examples and chain-of-thought

For each prompt, write the full prompt text and explain *why* it's better than the previous one.

## Part 2: Execute & Score (30%)

Use your coding agent to run all 3 prompts against these **5 test cases**:

| Input | Expected Urgency | Expected Category |
|-------|-----------------|-------------------|
| "I was charged twice for my subscription this month, please fix this immediately" | high | billing |
| "What's the difference between your pro and enterprise plans?" | low | account |
| "Your app keeps crashing when I try to upload a profile photo" | medium | technical |
| "I need to cancel my account and get a refund for the remaining months" | high | billing |
| "Can you add dark mode to your dashboard? The white background hurts my eyes" | low | other |

Report the accuracy (out of 10: 5 urgency + 5 category) for each prompt.

## Part 3: Analyze (30%)

Looking at your results:
- Which prompt performed best? Why?
- Which specific failure mode did each improvement fix?
- If you could add ONE more technique beyond what you used, what would it be and why?

---

**When done:** Reply `done` here. I'll grade it against the rubric. ≥ B and U2 is skipped.
