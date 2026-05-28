---
name: lesson-archiver
description: Use after teaching content that should be preserved in this repository. Saves the lesson as a Markdown file, updates the lesson index and LEARNING_STATE.md, and keeps sources, exercises, handoff notes, and next-lesson plans attached for future GitHub sharing.
---

# Lesson Archiver

Use this skill whenever a teaching session should be permanently saved for this project.

## Save Workflow

1. Create one Markdown lesson under `lessons/` named `YYYY-MM-DD-topic-slug.md`.
2. Use `templates/lesson-note.md` unless another lesson template fits better.
3. Include date, data cutoff, topic, learning goal, verified sources, core concept, keyword dictionary, review prompts, case study, conclusion boundaries, and exercises.
4. Include at least one realtime news item, historical event, or real market mechanism case. If the lesson is mostly theoretical, add a concrete historical anchor that makes the theory observable.
5. Update `lessons/INDEX.md` with the new lesson date, topic, and relative link.
6. Add a `学习交接` section to the lesson: completed content, most important takeaway, terms to review, unstable concepts, and the file to open next time.
7. Add a `下节课安排` section to the lesson: next topic, learning goal, suggested cases, required keywords, and data to verify before the next class.
8. Update `LEARNING_STATE.md` so another computer or Codex can continue with minimal context loss.
9. If the lesson introduces a reusable workflow, update or add a skill under `skills/`.

## Source Rules

- Preserve source names, dates, and links inside the lesson.
- Prefer source links near the facts they support.
- Label uncertain items as `待确认` or `市场推测`.
- Do not archive unsupported claims as facts.
- Market facts, current events, historical cases, company data, fund data, and commodity data must trace back to official, regulatory, exchange, issuer, or otherwise authoritative sources.

## Continuity Rules

- `LEARNING_STATE.md` is the first file to read when resuming on another computer.
- Keep the next lesson concrete enough that another agent can continue without asking what to teach.
- Every next-lesson plan should name the topic, goal, suggested cases, keywords, and realtime data that must be verified.
- Add `可回顾第 X 课` prompts when a concept depends on earlier lessons, so later professional content can be understood through accumulated foundations.

## Style

- Chinese by default.
- Clear, practical, and suitable for public learning.
- Keep investment language educational and avoid direct buy/sell instructions.
