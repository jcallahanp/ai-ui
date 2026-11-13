# Progress

The only record of where the project stands. Update it the moment something changes.

## Now

- **Phase:** 6, Build and verify (done). All ten steps passed an independent check.
- **Next action:** The user compares `design/a-repo.html` (layout A) with `design/b-chat.html`
  (layout B) and picks one (R14). Then record the choice in `docs/REQUIREMENTS.md` under
  "Changes after agreement" and plan any follow-up steps in `GOAL.md`.
- **Blocked on:** the user's choice between layout A and layout B.
- **Not merged:** everything since the first commit is on `claude/festive-volta-u6qury`, not
  `main`. The user has not asked for a merge.

## Phases

| # | Phase | Status | Finished when |
|---|---|---|---|
| 1 | Interview | done | The user agreed with the summary in `docs/INTERVIEW.md` on 2026-11-13 |
| 2 | Requirements | done | The user agreed to R1 to R27 on 2026-11-13 |
| 3 | Personas | done | Written from the agreed requirements. Not shown to the user separately; they said to proceed |
| 4 | Inspiration | done | Design direction final. It follows R19 to R22. Not shown to the user separately |
| 5 | Plan | done | `GOAL.md` has ten steps, each with yes-or-no checks |
| 6 | Build and verify | done | Every step below is `done` |

Phase statuses: `not started`, `in progress`, `done`.

## Steps

Step statuses: `todo`, `doing`, `to verify`, `done`, `failed`.

| Step | Status | Check result | Note |
|---|---|---|---|
| S01 Named values | done | pass, 2026-11-13 |  |
| S02 Page shell and agents pane | done | pass, 2026-11-13 |  |
| S03 Chat | done | pass on second check, 2026-11-13 | First check failed: a screenshot was left in design/shots/. A new agent removed it. |
| S04 Output center | done | pass, 2026-11-13 |  |
| S05 Phases pane | done | pass, 2026-11-13 |  |
| S06 Warp chosen | done | pass, 2026-11-13 |  |
| S07 Empty output center | done | pass, 2026-11-13 |  |
| S08 Repository view | done | pass, 2026-11-13 |  |
| S09 Layout B | done | pass, 2026-11-13 | The agent shrank commit text to 12px and tightened spacing to fit the 260px column. |
| S10 Large monitor | done | pass, 2026-11-13 |  |
