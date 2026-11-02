# Exam Prompts

## 1. Planning prompt (strong model, Quest "Code with Spec", attach the brief PDF)

You are a senior full-stack tech lead. Read the attached exam brief carefully, every line. This app will be marked by someone who clones the repo and runs it locally, checking it against the brief.

Do NOT write code yet. Create SPEC.md with:

1. **Summary** (3-5 lines): what we're building and for whom.
2. **Requirements checklist**: every requirement in the brief, numbered R1, R2... Keep the brief's exact wording for anything that sounds marked. Tag each MUST or NICE-TO-HAVE.
3. **Assumptions**: anything ambiguous, with the sensible choice you made.
4. **Stack**: follow the brief if it specifies one; otherwise use the stack in the project rules.
5. **Data model**: draft Prisma schema.
6. **Pages/routes and server actions/API endpoints.**
7. **Task list**: T1..Tn as checkboxes, in build order. Each task small enough for one chat, with: goal, files/areas, acceptance criteria, and which R's it covers. T1 = scaffold + DB + base layout with the UI style. All MUST features before any NICE-TO-HAVE. Polish/README last.
8. **Marker test plan**: a click-through checklist that proves every R works.

Only ask me questions if something is truly blocking (max 3). Otherwise assume and list it under Assumptions.

---

## 2. Build prompt (cheap model, new chat per 1-3 tasks)

Implement T__ to T__ from SPEC.md, following the project rules. When done: build passes, checkboxes ticked, PROGRESS.md updated. Reply with only the files changed and how to test.

---

## 3. Bug-fix prompt

Bug: I [did X] and got [Y], expected [Z].
Error: [paste exact error/terminal output]
Find and fix the root cause only. Don't touch unrelated code. Run the build after.

---

## 4. Final check prompt (strong model, last ~1.5 hours)

Act as the exam marker. Go through every requirement R1..Rn in SPEC.md and verify it in the code. List anything missing, broken, or only partly done, then fix them in order of importance. Finally: make sure README is complete, `.env.example` exists, the app works on an empty DB (and the optional seed works, if there is one), and the setup steps work from a fresh clone.
