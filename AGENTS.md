# Agent Instructions

## Project Purpose

- This repository provides a Codex skill for calculating recipe calories, protein, fat, and carbohydrates (KBJU).

## Key Files

| Need | File |
|---|---|
| Skill behavior and response template | `.agents/skills/recipe-nutrition-calculator/SKILL.md` |
| Evaluation scenarios | `.agents/skills/recipe-nutrition-calculator/evals/evals.json` |
| Russian project documentation | `README.ru.md` |
| English project documentation | `README.md` |

## Conventions

- Keep nutrition calculations based on values per 100 g and actual ingredient weights.
- Do not substitute missing nutrition data or finished dish weight without explicit user consent.
- Preserve the single combined-result format for multiple recipes or dishes.
- Keep Russian and English README files consistent when changing public behavior.
- Add or update `evals/evals.json` when changing skill behavior or its response format.
- Keep `docs/superpowers/` local only; do not add it to Git.
