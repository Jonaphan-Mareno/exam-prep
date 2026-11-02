# Project Rules (Always Apply)

## Priority
1. The exam brief / SPEC.md overrides these rules if they conflict (including the stack).
2. Working, complete core features > extra features. Never leave the app in a broken state.

## Default stack (unless the brief says otherwise)
- Next.js (App Router) + TypeScript (strict)
- Tailwind CSS + shadcn/ui
- Prisma + SQLite (file DB, no external DB server)
- Zod for validation
- No external APIs/services that need keys. If unavoidable, add a local mock/fallback so the app runs without keys.

## Must run locally with zero setup
- On a fresh clone: `npm install` then `npm run dev` must work.
- Commit `.env.example` with working defaults; code falls back to defaults if `.env` is missing.
- `npm run setup` (also run on postinstall) = prisma generate + migrate. The app must work on an empty database (first user can sign up, empty states shown).
- Demo data lives in a separate, optional `npm run seed` (never auto-run), unless the brief says otherwise. If the brief says no seed/demo data, don't create one.

## Workflow for every task
- Only work on the tasks I name. Don't refactor unrelated code.
- After changes, run `npm run build` and lint. Fix all errors before saying you're done.
- Tick the task's checkbox in SPEC.md and add one line to PROGRESS.md.
- Keep replies short: files changed + how to test. No long explanations.

## Code quality
- Structure: `app/` routes, `components/` (`components/ui` for shadcn), `lib/` (db, validation, utils), `prisma/`.
- Validate all input with Zod on the server (server actions or route handlers).
- Every data view handles loading, empty, and error states.
- Forms: client + server validation, inline error messages, submit disabled while pending, success toast.
- Auth (if needed): credentials with bcrypt-hashed passwords, protected routes, role checks on the server.
- No `any`, no dead code, no leftover console.logs.
- Responsive (375px mobile to desktop). Accessible: input labels, alt text, keyboard usable, good contrast.

## UI style (apply to every page; never invent a new style)
[PASTE YOUR designprompts.dev STYLE PROMPT HERE]
- Theme shadcn/ui components to match this style.
- One font pairing, one accent colour, consistent spacing.

## README.md must include
- What the app does + features mapped to the brief's requirements
- Exact copy-paste run steps and Node version
- Demo accounts
- Tech stack + short architecture notes
- Known limitations
