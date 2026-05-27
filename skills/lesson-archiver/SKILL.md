---
name: lesson-archiver
description: Use after teaching content that should be preserved in this repository. Saves the lesson as a Markdown file, updates the lesson index, and keeps sources and exercises attached for future GitHub sharing.
---

# Lesson Archiver

Use this skill whenever a teaching session should be permanently saved for this project.

## Save Workflow

1. Create one Markdown lesson under `lessons/` named `YYYY-MM-DD-topic-slug.md`.
2. Use `templates/lesson-note.md` unless another lesson template fits better.
3. Include date, data cutoff, topic, learning goal, verified sources, core concept, case study, conclusion boundaries, and exercises.
4. Update `lessons/INDEX.md` with the new lesson date, topic, and relative link.
5. If the lesson introduces a reusable workflow, update or add a skill under `skills/`.

## Source Rules

- Preserve source names, dates, and links inside the lesson.
- Prefer source links near the facts they support.
- Label uncertain items as `待确认` or `市场推测`.
- Do not archive unsupported claims as facts.

## Style

- Chinese by default.
- Clear, practical, and suitable for public learning.
- Keep investment language educational and avoid direct buy/sell instructions.
