# Hermes University — Vault

Source of truth for the personal-university program (records + proof + notes).
Owned by the `hermes` user so the agent can read/write it.

- `Registrar/` — program, curriculum, state.json, transcript, learner-model (Registrar-owned data).
- `Courses/<C>/` — syllabus, lessons/, per course. CS250 active (MVP); others activate later.
- `Uploads/<C>/` — parsed book chapters for DeepSeek long-context grounding.
- `Concepts/patterns|behavioral/` — pattern notes / STAR stories (proof artifacts).
- `Daily/YYYY-MM-DD.md` — append-only daily notes (## Assigned / ## Proof / ## Log).
- `Exams/` — quiz & exam records. `SRS/pending.jsonl` — queued Anki cards (Anki deferred).

**Behavior** (registrar / examiner / cs250-professor skills) lives in Hermes skills at
`~/.hermes/skills/hermes-university/`, NOT in this vault. This vault is data only.

After any write: `git -C /home/hermes/vault add -A && git commit -m "<what>" && git push`.
