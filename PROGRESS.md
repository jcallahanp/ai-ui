# Progress

The only record of where the project stands. Update it the moment something changes.

## Now

- **Phase:** 6, Build and verify. Round 2 in progress.
- **Why a round 2:** on 2026-11-13 the user saw the six round 1 pages and asked for changes:
  agents on the left, one pane that holds either an output or the repository, a few ideas for
  switching branches without a column, a red theme beside the purple one for every option, and
  a "John's Red Team" label. Recorded in `docs/REQUIREMENTS.md` under "Changes after agreement".
- **Next action:** Run the first step from S11 on that is not `done`, in the order `GOAL.md`
  gives. One Opus 5.5 agent does the step; a different one checks it.
- **Blocked on:** nothing
- **Still to come from the user:** which idea and which theme. Then the Warp, empty and
  large-monitor pages are redone in that style, and the round 1 pages are removed.
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
| 6 | Build and verify | in progress | Every step below is `done` |

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
| S11 Agents on the left, with the team label | doing |  |  |
| S12 Idea 1, branch chips | todo | | |
| S13 Idea 2, branch switcher in the tab row | todo | | |
| S14 Idea 3, branches as the live list | todo | | |
| S15 Red theme | todo | | |
