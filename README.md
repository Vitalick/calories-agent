# KBJU Recipe Nutrition Calculator

[Русская версия](README.ru.md)

An open Codex skill for calculating recipe nutrition: calories, protein,
fat, and carbohydrates (KBJU) for the whole dish and per 100 grams.

## What it does

- Accepts recipe text, images, screenshots, and recipe links.
- Calculates the contribution of every ingredient from its weight and
  nutrition values per 100 g.
- Produces one combined calculation when several recipes or dishes are
  provided.
- Uses the final cooked weight for per-100-g values.
- Requests clarification when the input is incomplete instead of guessing.

## Install

Copy the skill directory into your Codex skills directory:

```text
.agents/skills/podschet-kbzhu-po-receptu/
```

After installation, ask Codex to calculate the nutrition of a recipe. The
skill is selected automatically for KBJU-related requests.

## Example

```text
Calculate KBJU for a dish with 500 g chicken breast (110 kcal, 23 g protein,
1.5 g fat, 0 g carbs per 100 g) and 200 g rice (350 kcal, 7 g protein,
0.7 g fat, 78 g carbs per 100 g). The finished dish weighs 600 g.
```

The result includes an ingredient table, totals for the whole dish, and
nutrition per 100 g.

## Calculation rules

For each nutrient:

```text
ingredient contribution = value per 100 g × ingredient weight / 100
dish total = sum of ingredient contributions
per 100 g = dish total / finished dish weight × 100
```

Intermediate values are kept precise; only displayed results are rounded.
Unknown nutrition values or final dish weight require your confirmation before
the calculation is completed.

## Project layout

```text
.agents/skills/podschet-kbzhu-po-receptu/
├── SKILL.md          # Skill instructions
└── evals/evals.json  # Evaluation cases
```

## Contributing

Contributions that improve calculation accuracy, input handling, or evaluation
coverage are welcome. Keep the output template stable unless a change is
intentional and covered by evaluation cases.

## License

This project is licensed under the [MIT License](LICENSE).
