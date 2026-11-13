# ai-ui

Design a UI from the user's Pinterest inspiration and their real interaction goals.
**UI design only. No functioning software.** Someone else builds the working system from it.
Static mockups with placeholder content are fine. No backend, real data, auth or working logic.

## State lives in files, never in session memory

Read these at the start of every session. If it is not written in one of them, it is not known.

| File | Holds |
|---|---|
| `PROGRESS.md` | Current phase, next action and the status of every step. Read it first |
| `GOAL.md` | The goal, broken into atomic steps that can each be checked |
| `docs/INTERVIEW.md` | What the user said and why they want it |
| `docs/REQUIREMENTS.md` | The requirements the user has agreed to |
| `docs/PERSONAS.md` | Who uses the UI, each with "done when" checks |
| `docs/INSPIRATION.md` | The Pinterest pins and the design direction drawn from them |

Nothing important goes in project memory or stays only in the conversation.
Update `PROGRESS.md` the moment something changes, not at the end of the session.

## Process: one phase at a time, in order

1. **Interview.** Find out why the user wants this before asking what it looks like. Do not
   assume they have thought of everything: ask about what they left out. Ask one or two
   questions at a time and record the answers in `docs/INTERVIEW.md`. Keep going until you can
   explain their vision back to them and they agree with it.
2. **Requirements.** Turn the interview into numbered requirements in `docs/REQUIREMENTS.md`.
   Nothing later starts until the user has agreed to them.
3. **Personas.** Write each persona with "done when" checks that can be tested against a screen.
4. **Inspiration.** Turn the pins into one design direction in `docs/INSPIRATION.md`.
5. **Plan.** Write the steps in `GOAL.md`. Always plan before writing code or running tests.
6. **Build and verify.** Run the steps under the rules below. Design files go in `design/`.

## Engineering

- Fable orchestrates: it plans, delegates and updates `PROGRESS.md`. It does not do step work.
- One step, one agent: Opus 5.5 (`model: opus`) at `medium` or `high` effort.
- The agent gets only its step's text and the files that step names. It does that step and
  nothing else, then retires. Agents are disposable and carry nothing between steps.
- A separate agent checks the step against its "done when". The agent that did the work
  never verifies it.
- A step is done only when that check passes and `PROGRESS.md` says so. If the check fails,
  mark the step `failed` with the reason and give it to a new agent.
- A step that cannot be judged done or not done is too big or too vague. Split it.
- No abstractions. Build the simplest thing that gives the user what they asked for.
