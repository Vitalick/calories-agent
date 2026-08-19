# Recipe Nutrition Calculator

[Русская версия](README.ru.md)

An open, reusable `SKILL.md` instruction for calculating recipe nutrition:
calories, protein, fat, and carbohydrates for the whole dish and per 100
grams. It works with Codex and other AI agents that support the `SKILL.md`
format.

## What it does

- Accepts recipe text, images, screenshots, and recipe links.
- Calculates the contribution of every ingredient from its weight and
  nutrition values per 100 g.
- Produces one combined calculation when several recipes or dishes are
  provided.
- Uses the final cooked weight for per-100-g values.
- Requests clarification when the input is incomplete instead of guessing.

## Use with an AI agent

Copy the skill directory into the skills directory of a compatible AI agent:

```text
.agents/skills/recipe-nutrition-calculator/
```

Then ask the agent to calculate the nutrition of a recipe. Refer to your
agent's documentation for its exact skills-directory location and activation
method.

## Example

```text
Calculate calories and macros for a dish with 500 g chicken breast (110 kcal, 23 g protein,
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
.agents/skills/recipe-nutrition-calculator/
├── SKILL.md          # Skill instructions
└── evals/evals.json  # Evaluation cases
```

## Contributing

Contributions that improve calculation accuracy, input handling, or evaluation
coverage are welcome. Keep the output template stable unless a change is
intentional and covered by evaluation cases.

## License

This project is licensed under the [MIT License](LICENSE).
