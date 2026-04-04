# CLAUDE.md — AI Assistant Guide for my-diet-first-app

## Project Overview

**my-diet-first-app** is a diet tracking application. The project is in its initial stage — the repository currently contains only a README placeholder. This file documents the expected conventions and guidelines for AI assistants helping to build and maintain this codebase.

---

## Repository State (as of 2026-04-04)

- **Status:** Initial scaffold — no source code yet
- **Main branch:** `main`
- **Active dev branch:** `claude/add-claude-documentation-GhbsQ`
- **Remote:** `wii4021/my-diet-first-app`

When the project is initialized with a tech stack, update the sections below accordingly.

---

## Tech Stack (TBD)

The technology stack has not yet been chosen. When it is, document it here. Common choices for a diet app might include:

- **Frontend:** React / Next.js / Vue / React Native
- **Backend:** Node.js (Express/Fastify) / Python (FastAPI/Django) / Ruby on Rails
- **Database:** PostgreSQL / SQLite / MongoDB
- **Auth:** NextAuth / Auth0 / Firebase Auth
- **Package manager:** npm / pnpm / yarn / pip

Once decided, add:
- The exact framework and version
- The package manager and lockfile to commit
- Any ORM or query builder used

---

## Project Structure (TBD)

Document the directory layout once source code exists. Example for a Next.js project:

```
my-diet-first-app/
├── src/
│   ├── app/           # Next.js App Router pages and layouts
│   ├── components/    # Reusable UI components
│   ├── lib/           # Utilities, helpers, API clients
│   ├── hooks/         # Custom React hooks
│   └── types/         # TypeScript type definitions
├── public/            # Static assets
├── prisma/            # DB schema and migrations (if using Prisma)
├── .env.example       # Environment variable template
├── package.json
└── CLAUDE.md
```

---

## Development Workflow

### Branch Strategy

- `main` — stable, production-ready code only
- Feature branches use the pattern: `feature/<short-description>`
- Bug fixes: `fix/<short-description>`
- Claude-initiated branches: `claude/<task-description>`

Always develop on a feature branch, never directly on `main`.

### Git Commit Convention

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add calorie entry form
fix: correct macro calculation rounding
docs: update README with setup steps
refactor: extract nutrition API into lib/nutrition.ts
test: add unit tests for calorie calculator
```

### Pushing Changes

```bash
git push -u origin <branch-name>
```

Retry up to 4 times with exponential backoff on network failure (2s, 4s, 8s, 16s).

---

## Development Commands (TBD)

Document these once the project is initialized:

| Command | Description |
|---------|-------------|
| `npm install` | Install dependencies |
| `npm run dev` | Start local development server |
| `npm run build` | Production build |
| `npm run test` | Run tests |
| `npm run lint` | Run linter |
| `npm run format` | Run code formatter |

---

## Environment Variables

Create a `.env.local` file from `.env.example` (once it exists). Never commit secrets. Document required variables in `.env.example` with placeholder values and comments explaining each.

---

## Coding Conventions

### General

- Prefer explicit over clever code
- Keep functions small and single-purpose
- No unused imports, variables, or dead code
- Validate user input at system boundaries; trust internal code
- Do not add speculative abstractions — build for what is needed now

### Naming

- **Files:** kebab-case (`calorie-tracker.ts`, `food-search.tsx`)
- **Components:** PascalCase (`CalorieEntry`, `FoodSearch`)
- **Functions/variables:** camelCase (`calculateMacros`, `dailyGoal`)
- **Constants:** UPPER_SNAKE_CASE (`MAX_CALORIES_PER_DAY`)
- **Types/Interfaces:** PascalCase (`FoodItem`, `NutritionFacts`)

### Comments

Only comment where logic is non-obvious. Do not add docstrings or JSDoc to straightforward code.

---

## Domain Concepts

Key domain concepts for a diet tracking app:

- **Food item:** A single food with nutrition information (calories, protein, carbs, fat)
- **Meal:** A collection of food items consumed at one sitting
- **Daily log:** All meals logged for a given date
- **Macro:** Macronutrient (protein, carbohydrates, fat) quantities in grams
- **Goal:** User-defined daily targets for calories and/or macros
- **Serving size:** A unit of measurement for a food item (g, oz, cup, etc.)

---

## Security Considerations

- Never expose API keys or secrets in client-side code
- Validate and sanitize all user-provided food/nutrition data
- Use parameterized queries; never interpolate user input into SQL
- Scope data access per authenticated user — users must only see their own food logs

---

## Testing Guidelines (TBD)

Document testing approach once framework is chosen. Aim for:

- Unit tests for pure calculation logic (calorie math, macro summation)
- Integration tests for API routes
- Minimal E2E tests for critical user flows (logging a meal, viewing daily summary)

---

## AI Assistant Instructions

When working in this repository:

1. **Read before editing** — always read existing files before modifying them
2. **Stay on the designated branch** — do not push to `main` without explicit permission
3. **Minimal changes** — make only the changes required by the task; no scope creep
4. **No speculative features** — do not add features that were not requested
5. **Commit and push** when implementation is complete
6. **Update this file** when the tech stack, structure, or conventions are established
7. **Keep `.env.example` current** whenever new environment variables are added
8. **Do not commit secrets** — check for `.env`, credentials, or API keys before committing
