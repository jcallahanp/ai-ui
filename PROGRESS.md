# Progress

The only record of where the project stands. Update it the moment something changes.

## Now

- **Phase:** 6, Build and verify. Round 2 is done: S11 to S15 all passed an independent check.
- **Next action:** The user picks one branch idea (`design/idea-1.html`, `idea-2.html` or
  `idea-3.html`) and one theme (purple, or the `-red` pages), and says whether the "John's Red
  Team" label is in the right place. Record the choice in `docs/REQUIREMENTS.md` under "Changes
  after agreement". Then plan round 3 in `GOAL.md`: redo the Warp, empty and large-monitor
  pages in the chosen style and remove the pages that were not chosen, including the six
  round 1 pages (`a-*.html`, `b-chat.html`, `wide.html`).
- **Blocked on:** the user's choice of idea and theme.
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
| 6 | Build and verify | in progress | Round 2 done. Round 3 follows the user's choice |

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
| S11 Agents on the left, with the team label | done | pass, 2026-11-13 |  |
| S12 Idea 1, branch chips | done | pass, 2026-11-13 |  |
| S13 Idea 2, branch switcher in the tab row | done | pass, 2026-11-13 |  |
| S14 Idea 3, branches as the live list | done | pass, 2026-11-13 |  |
| S15 Red theme | done | pass, 2026-11-13 | Checker's note: in red, PHASES is bolder than IN PARALLEL, and pane titles such as the chat header are not restyled. |
