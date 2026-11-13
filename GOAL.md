# Goal

**Goal:** Static HTML and CSS pages in `design/` that show the agreed dashboard in every state
listed in R27, so that every check in `docs/PERSONAS.md` is a yes.

Status is tracked in `PROGRESS.md`, not here. This file changes only when the plan changes.

## Pages

| Page | Shows | Size |
|---|---|---|
| `design/a-chat.html` | Layout A. Fable 5.2 chosen, its chat, a doc open in the output center | 1440 by 900 |
| `design/a-warp.html` | Layout A. Warp chosen, a terminal in place of the chat | 1440 by 900 |
| `design/a-empty.html` | Layout A. No output open | 1440 by 900 |
| `design/a-repo.html` | Layout A. The repository tab open in the output center | 1440 by 900 |
| `design/b-chat.html` | Layout B. The repository as its own column, always on screen | 1440 by 900 |
| `design/wide.html` | Large monitor. Repository, an output, the chat, agents and phases together | 2560 by 1440 |

Layout A, left to right: output center, chat, then a right column with the agents pane above
the phases pane. Layout B adds a repository column at the far left.

## Order

Round 1, done:

- S01 to S05 run one after another. Each builds on the one before.
- S06, S07 and S08 run in parallel after S05.
- S09 and S10 run in parallel after S08.

Round 2, added 2026-11-13 after the user saw round 1 (see "Changes after agreement" in
`docs/REQUIREMENTS.md`). The agents move to the left, one pane holds either an output or the
repository, and three ideas for switching branches are each shown in purple and in red:

- S11 runs first.
- S12, S13 and S14 run in parallel after S11.
- S15 runs after S12, S13 and S14.

Round 2 pages, all at 1440 by 900:

| Page | Shows |
|---|---|
| `design/base.html` | Agents on the left with the team label, the chat, a doc open in the output pane |
| `design/idea-1.html` | Repository open. Branches as a row of chips |
| `design/idea-2.html` | Repository open. Branches in a switcher in the tab row |
| `design/idea-3.html` | Repository open. Branches as a live list that replaces the commit list |
| `design/base-red.html`, `design/idea-1-red.html`, `design/idea-2-red.html`, `design/idea-3-red.html` | The same four pages in the red theme |

The six round 1 pages have the agents on the right and are superseded. Do not copy their
layout. Round 2 steps may copy content from them where a step says so.

## Rules for every step

The agent doing a step is given these rules and that step's text, and nothing else.

- Write static HTML and CSS only. No `<script>`, no images, no icon fonts, no frameworks.
- Create or change only the files on the step's Write line.
- In CSS, never write a color, a font family or a font size directly. Use the named values
  from `design/style.css`, for example `var(--pane)`. The only exception is step S01, which
  defines them.
- Use only what the step asks for. Do not add panes, icons, charts, badges or decoration.
- The page itself never scrolls at its stated size. A pane may scroll inside itself.
- Check your own work with a screenshot at the step's size before finishing. Chromium and
  Playwright are installed: `require('playwright')` works from any directory. Save screenshots
  outside the repository.
- Do not commit. Do not edit `PROGRESS.md`, `GOAL.md` or anything in `docs/`.
- Finish by listing the files you wrote and anything in the step you could not do.

## Rules for checking a step

A different agent checks each step. It is given these rules and the step's text.

- Change no files in the repository.
- Answer every "Done when" question yes or no, with one line of evidence each. Read the files
  and take a screenshot at the step's size to decide.
- Also answer: did the step change any file not on its Write line? Run `git status --short`.
- Report PASS only if every answer is yes and no other file changed. Otherwise report FAIL and
  say exactly what is wrong.

## Placeholder content

Use this wherever a step needs content, so every page tells the same story.

- **Agents, in this order, with states:** Fable 5.2 (working), Warp (idle), Deep Seek (waiting
  for you), GLM (working), Kimi (idle).
- **Project:** `atlas`, a small API service.
- **Branches:** `main` (no agent), `fable/api-routes` (Fable 5.2), `deepseek/auth` (Deep Seek),
  `glm/web-client` (GLM), `kimi/cli` (Kimi).
- **Outputs:** `api-design.md`, a doc; `schema diagram`, an artifact.
- **Phases:** 1 Scaffold, 4 of 4. 2 Data model, 6 of 6. 3 API routes, 5 of 8, in parallel with
  4 Auth, 2 of 6. 5 Web client, 1 of 9, in parallel with 6 CLI, 0 of 5. 7 Tests and release,
  0 of 7.

## Steps

### S01: Named values
- Do: Write `design/style.css` containing only: one `@import` of Inter (400, 500, 600) and
  JetBrains Mono (400, 500) from Google Fonts; a `:root` block defining every name in the
  "Named values" table with exactly its value; and base rules for `*` (box-sizing), `html` and
  `body` (no margin, full height, `--bg` background, `--text` color, `--sans` at `--fs-m`,
  `overflow: hidden`).
- Read: `docs/INSPIRATION.md`, the "Named values" table only.
- Write: `design/style.css`
- Covers: R19, R20, R21, P2.4
- Size: none. There is no page yet; skip the screenshot.
- Done when:
  1. Does `:root` define all 19 names from the table, each with exactly the table's value?
  2. Outside `:root`, is every color, font family and font size given as `var(...)`?
  3. Are the only selectors in the file `:root`, `*`, `html` and `body`?
  4. Is the Google Fonts import the only external reference in the file?

### S02: Page shell and agents pane
- Do: Create `design/a-chat.html` and add the layout, pane and agent-card rules to
  `design/style.css`.
  - The page links `style.css` and has `<title>atlas</title>`.
  - `body` is a grid filling the window: three columns `minmax(0, 1.15fr) minmax(0, 1fr) 300px`,
    `--gap` between them and `--gap` padding around the edge.
  - Column 1 is `<section id="output" class="pane">`. Column 2 is
    `<section id="chat" class="pane">`. Leave both empty.
  - Column 3 is a `<div class="side">` holding `<section id="agents" class="pane">` and, below
    it, `<section id="phases" class="pane">`. Agents takes the height it needs; phases fills
    the rest. Leave `#phases` empty.
  - A `.pane` has the `--pane` background, a 1px `--line` border and `--radius` corners.
  - `#agents` holds five cards stacked `--gap` apart, in the placeholder order. Each card is
    an `<a class="agent">`, about 72px tall, with the `--raised` background, a 1px `--line`
    border and `--radius-s` corners. Inside: the agent's name at `--fs-l`, weight 600, and
    under it the state at `--fs-s` in `--text-2` with a dot before it.
  - Dots: working is an 8px solid `--accent` circle with the `--glow` shadow. Waiting for you
    is an 8px solid `--text` circle. Idle is an 8px ring, 1px `--text-3`, empty inside.
  - The Fable 5.2 card also has the class `is-chosen`: an `--accent` border and the `--glow`
    shadow. No other card has it.
  - Links: Fable 5.2 goes to `a-chat.html`, Warp to `a-warp.html`, the other three to `#`.
    Links are not underlined and keep the text colors above.
- Read: `design/style.css`
- Write: `design/a-chat.html`, `design/style.css`
- Covers: R1, R2, R3, R4, R23
- Size: 1440 by 900
- Done when:
  1. Are there exactly five agent cards, reading Fable 5.2, Warp, Deep Seek, GLM, Kimi from
     top to bottom, in a pane at the right edge?
  2. Does each card show only a name and one state, with the states working, idle, waiting
     for you, working, idle?
  3. Do the three kinds of dot look different from each other as described?
  4. Is Fable 5.2 the only card with a purple border and glow?
  5. Do `#output`, `#chat` and `#phases` exist as empty panes, each visible as a dark rounded
     rectangle?
  6. Does the page fit 1440 by 900 with no scrollbar in either direction?
  7. Does the `:root` block still hold exactly the 19 named values, unchanged?
  8. Are the new CSS rules free of directly written colors, font families and font sizes?
  9. Is the page free of `<script>` and of images?

### S03: Chat
- Do: Fill `#chat` in `design/a-chat.html` and add its rules to `design/style.css`.
  - A header row: "Fable 5.2" at `--fs-l`, weight 600, and beside it the working dot and the
    word "working" at `--fs-s` in `--text-2`. A 1px `--line` divider below.
  - A conversation that fills the middle and scrolls inside the pane if it is too long. Five
    messages about adding the API routes for users and orders. The operator's messages sit in
    a `--raised` box with `--radius-s` corners, aligned right, at most 80% wide. The agent's
    messages are plain text, aligned left, full width, with no box.
  - One agent message contains inline code in `--mono`, and one is followed by a single quiet
    line in `--fs-s` `--text-3` reading "Edited api-design.md".
  - At the bottom, pinned: an input box with the `--raised` background, a 1px `--line` border
    and `--radius-s` corners, showing the placeholder "Message Fable 5.2" in `--text-3`, with
    a small "Send" button at its right in `--text-2`. Use a `<textarea>` or `<input>` and a
    `<button>`.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/a-chat.html`, `design/style.css`
- Covers: R5
- Size: 1440 by 900
- Done when:
  1. Does the chat pane show a header naming Fable 5.2 with its working state?
  2. Are there five messages, with the operator's in boxes on the right and the agent's as
     plain text on the left?
  3. Is there an input box pinned to the bottom of the pane with the placeholder
     "Message Fable 5.2" and a Send button?
  4. Is the only purple in the chat pane the working dot?
  5. Are `#agents`, `#output` and `#phases` unchanged from before this step, and does the page
     still fit 1440 by 900 with no scrollbar?
  6. Are the new CSS rules free of directly written colors, font families and font sizes, and
     is the page still free of `<script>` and images?

### S04: Output center
- Do: Fill `#output` in `design/a-chat.html` and add its rules to `design/style.css`.
  - A row of three tabs at the top: "Repository" linking to `a-repo.html`, "api-design.md"
    linking to `a-chat.html`, and "schema diagram" linking to `#`. Tabs are `<a class="tab">`
    at `--fs-m` in `--text-2`. The "api-design.md" tab has the class `is-chosen`: `--raised`
    background, `--text` color, `--radius-s` corners. A 1px `--line` divider under the row.
  - Under the tabs, one quiet line with the class `editing`: the working dot, then
    "Fable 5.2 is editing" at `--fs-s` in `--text-2`.
  - Below that, the doc, scrolling inside the pane if needed, with comfortable reading width
    and line height: a title "API design"; a short paragraph; a heading "Routes"; a table of
    five routes with the columns Method, Path and Purpose, with methods and paths in `--mono`;
    a heading "Errors"; a short paragraph; and one code block in `--mono` on a `--raised`
    background showing a small JSON error body.
  - Headings use `--fs-l`, weight 600. The title may be larger only by weight and spacing, not
    by a new font size.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/a-chat.html`, `design/style.css`
- Covers: R7, R9, R10
- Size: 1440 by 900
- Done when:
  1. Are there three tabs reading Repository, api-design.md and schema diagram, with only
     api-design.md marked as chosen?
  2. Is there a line under the tabs saying Fable 5.2 is editing, with a working dot?
  3. Does the pane show a readable doc with a title, a routes table of five rows and a code
     block?
  4. Is the only purple in the output pane the working dot?
  5. Are `#agents`, `#chat` and `#phases` unchanged from before this step, and does the page
     still fit 1440 by 900 with no scrollbar?
  6. Are the new CSS rules free of directly written colors, font families and font sizes, and
     is the page still free of `<script>` and images?

### S05: Phases pane
- Do: Fill `#phases` in `design/a-chat.html` and add its rules to `design/style.css`.
  - A title "Phases" at `--fs-l`, weight 600.
  - The seven placeholder phases in order, top to bottom. A phase that runs alone takes the
    full width of its row. Two phases that run in parallel share one row, side by side, each
    half the width, with the words "in parallel" above the pair at `--fs-s` in `--text-3`.
    So the rows are: Scaffold; Data model; API routes beside Auth; Web client beside CLI;
    Tests and release.
  - Each phase shows its name at `--fs-m`, its count such as "5/8" at `--fs-s` in `--text-2`
    on the same line at the right, and under them a bar 2px tall: a `--line` track with an
    `--accent` fill as wide as the fraction done.
  - A finished phase has its name in `--text-2`. A phase at 0 has an empty track.
  - No boxes or borders around phases. No glow in this pane.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/a-chat.html`, `design/style.css`
- Covers: R15, R16, R17, R18, R24
- Size: 1440 by 900
- Done when:
  1. Does the pane show all seven phases by name, in the placeholder order, each with its
     count and a thin bar?
  2. Do the bar fills match the counts: full for Scaffold and Data model, empty for CLI and
     for Tests and release, partial for the rest?
  3. Are API routes and Auth side by side on one row, and Web client and CLI side by side on
     another, each pair labelled "in parallel", while the other three phases have a row each?
  4. Is the whole pane visible without scrolling, below the agents pane, at 1440 by 900?
  5. Are `#agents`, `#chat` and `#output` unchanged from before this step, and does the page
     still fit 1440 by 900 with no scrollbar?
  6. Are the new CSS rules free of directly written colors, font families and font sizes, and
     is the page still free of `<script>` and images?

### S06: Warp chosen
- Do: Create `design/a-warp.html` as a copy of `design/a-chat.html` with two changes.
  - In `#agents`, the `is-chosen` class moves from the Fable 5.2 card to the Warp card.
    States stay as they are.
  - `#chat` holds a terminal in place of the chat: the same header row, reading "Warp" with
    the idle dot and the word "terminal"; then the terminal, all in `--mono` at `--fs-m`. Show
    three commands with their output, run in `~/atlas` on `main`: `git status`,
    `git log --oneline -3` and `npm test`. Prompts are in `--text-2`, commands in `--text`,
    output in `--text-2`. End with an empty prompt followed by a solid `--text` block cursor.
    There is no input box and no Send button.
  - Put the terminal's rules in a `<style>` block in this page's `<head>`. Do not change
    `style.css`.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/a-warp.html`
- Covers: R4, R6, R8
- Size: 1440 by 900
- Done when:
  1. Is Warp the only card with the purple border and glow, with all five states unchanged?
  2. Does the middle pane show a terminal in a monospace face with three commands, their
     output and a final prompt with a block cursor, and no message input box?
  3. Is the `#output` element identical, character for character, to the one in
     `a-chat.html`?
  4. Is the `#phases` element identical to the one in `a-chat.html`?
  5. Does the page fit 1440 by 900 with no scrollbar?
  6. Is the `<style>` block free of directly written colors, font families and font sizes,
     and is the page free of `<script>` and images?

### S07: Empty output center
- Do: Create `design/a-empty.html` as a copy of `design/a-chat.html` with one change: no
  output is open.
  - In `#output`, the tab row holds only the "Repository" tab, not chosen. There is no
    "is editing" line and no doc.
  - In the middle of the pane, centered both ways: "No output open" at `--fs-l` in `--text-2`,
    and under it "Outputs your agents create appear here and stay open while you switch
    agents." at `--fs-m` in `--text-3`, no wider than 320px.
  - Put any rules this needs in a `<style>` block in this page's `<head>`. Do not change
    `style.css`.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/a-empty.html`
- Covers: R7, R27
- Size: 1440 by 900
- Done when:
  1. Does the output pane show only a Repository tab and the two centered lines of text?
  2. Is there no purple anywhere in the output pane?
  3. Are the `#agents`, `#chat` and `#phases` elements identical to those in `a-chat.html`?
  4. Does the page fit 1440 by 900 with no scrollbar?
  5. Is the `<style>` block free of directly written colors, font families and font sizes,
     and is the page free of `<script>` and images?

### S08: Repository view
- Do: Create `design/a-repo.html` as a copy of `design/a-chat.html` with the repository open
  in the output center, and create `design/repo.css` holding all the repository rules. The
  page links `repo.css` after `style.css`. Do not change `style.css`.
  - In the tab row, "Repository" has `is-chosen` and "api-design.md" does not. Remove the
    "is editing" line and the doc.
  - Below the tabs put `<div class="repo">` with four parts, each a direct child with the
    class shown: `repo-branches`, `repo-tree`, `repo-code`, `repo-commits`. Lay `.repo` out as
    a grid: a left column 210px wide holding branches above the tree, and a right column
    holding the code above the commits. The commits part is about 190px tall.
  - `repo-branches`: a small label "Branches" at `--fs-s` in `--text-3`, then all five
    placeholder branches listed at once, one per row: the branch name in `--mono`, and the
    agent's name at `--fs-s` in `--text-2` at the right. `main` shows no agent. The row for
    `fable/api-routes` has `is-chosen`: a `--raised` background and `--text` color.
  - `repo-tree`: a label "Files", then an indented tree in `--mono`: `src/` open, holding
    `routes/` open with `index.ts`, `orders.ts` and `users.ts`, then `models/` and `auth/`
    closed; then `docs/` and `tests/` closed; then `package.json` and `README.md`. Folders end
    with `/` and are in `--text-2`; files are in `--text`. The row for `users.ts` has
    `is-chosen`.
  - `repo-code`: one line at the top giving the path `src/routes/users.ts` in `--mono` and
    "on fable/api-routes" in `--text-3`. Then about 24 lines of plausible TypeScript for a
    users route, in `--mono`, with line numbers in `--text-3`. Keywords are in `--accent`,
    comments in `--text-3`, everything else in `--text`. It scrolls inside itself if needed.
  - `repo-commits`: a label "Commits", then five commits, newest first. Each row has the
    message, then the branch in `--mono`, the agent's name and a relative time, the last three
    in `--text-2` at `--fs-s`. Use these: "Add users route handlers", fable/api-routes,
    Fable 5.2, just now. "Merge deepseek/auth into main", main, Deep Seek, 4m. "Add session
    middleware", deepseek/auth, Deep Seek, 9m. "Scaffold web client shell", glm/web-client,
    GLM, 21m. "Add order model", main, Fable 5.2, 1h. The merge row starts with the word
    "merge" at `--fs-s` in `--text-3`.
  - Parts are separated by 1px `--line` dividers, not by boxes. No glow in this view.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/a-repo.html`, `design/repo.css`
- Covers: R11, R12, R13, R14
- Size: 1440 by 900
- Done when:
  1. Is Repository the chosen tab, with api-design.md and schema diagram still present?
  2. Are all five branches visible at once, each with its agent's name except `main`, and is
     `fable/api-routes` the only one marked as chosen?
  3. Is there a file tree with `users.ts` marked as chosen, and beside it the code of
     `src/routes/users.ts` with line numbers, readable at this size?
  4. Are there five commits, newest first, each showing a message, a branch, an agent and a
     time, with the merge marked as a merge?
  5. Are all four parts visible at once inside the output pane at 1440 by 900?
  6. Is purple used in this pane only for keywords in the code?
  7. Are the `#agents`, `#chat` and `#phases` elements identical to those in `a-chat.html`,
     and does the page fit 1440 by 900 with no scrollbar?
  8. Is `repo.css` free of directly written colors, font families and font sizes, is
     `style.css` unchanged, and is the page free of `<script>` and images?

### S09: Layout B
- Do: Create `design/b-chat.html` as a copy of `design/a-chat.html` with the repository as its
  own column. The page links `repo.css` after `style.css`. Do not change `style.css` or
  `repo.css`.
  - Add `<section id="repo" class="pane">` as a new first column, 260px wide. The grid becomes
    `260px minmax(0, 1.1fr) minmax(0, 1fr) 280px`.
  - `#repo` holds three parts stacked top to bottom, copied from `a-repo.html` with the same
    classes and content: `repo-branches`, `repo-tree`, `repo-commits`. The tree takes the
    spare height. In this narrow column a commit's branch, agent and time go on a second line
    under its message.
  - In `#output`, remove the "Repository" tab. The tabs are "api-design.md" (chosen),
    "schema diagram" and "users.ts", the last in `--mono`, linking to `#`. Keep the
    "is editing" line and the doc.
  - `#chat`, `#agents` and `#phases` keep their content.
  - Put the rules this page needs in a `<style>` block in its `<head>`.
- Read: `design/a-chat.html`, `design/a-repo.html`, `design/style.css`, `design/repo.css`
- Write: `design/b-chat.html`
- Covers: R14, R23, R24
- Size: 1440 by 900
- Done when:
  1. Are there four columns, left to right: repository, output center, chat, and agents above
     phases?
  2. Does the repository column show all five branches, the file tree and the five commits,
     all visible without scrolling the page?
  3. Does the output center have no Repository tab, and show the doc with api-design.md
     chosen and a users.ts tab present?
  4. Are all five agent cards and all seven phases still fully visible?
  5. Is all text in every column readable, with nothing cut off or overlapping?
  6. Does the page fit 1440 by 900 with no scrollbar?
  7. Is the `<style>` block free of directly written colors, font families and font sizes,
     are `style.css` and `repo.css` unchanged, and is the page free of `<script>` and images?

### S10: Large monitor
- Do: Create `design/wide.html` for a 2560 by 1440 window. It shows the whole repository view
  and an output at the same time. The page links `repo.css` after `style.css`. Do not change
  `style.css` or `repo.css`.
  - Four columns: `860px minmax(0, 1.05fr) minmax(0, 1fr) 360px`.
  - Column 1 is `<section id="repo" class="pane">` holding the full `<div class="repo">` from
    `a-repo.html`: branches, tree, code and commits, with the same content.
  - Column 2 is `#output` as in `a-chat.html`, but without the "Repository" tab: the tabs are
    "api-design.md" (chosen) and "schema diagram". Keep the "is editing" line and the doc.
  - Column 3 is `#chat` and column 4 is the side column with `#agents` and `#phases`, all
    copied from `a-chat.html` unchanged.
  - Text stays at the named sizes. Do not scale anything up; the extra room shows more.
  - Put the rules this page needs in a `<style>` block in its `<head>`.
- Read: `design/a-chat.html`, `design/a-repo.html`, `design/style.css`, `design/repo.css`
- Write: `design/wide.html`
- Covers: R25, R27
- Size: 2560 by 1440
- Done when:
  1. Are the repository view (branches, tree, code and commits), the doc in the output
     center, the chat, the five agent cards and the seven phases all visible at once?
  2. Does the output center have no Repository tab?
  3. Is the text the same size as on the laptop pages, not scaled up?
  4. Does the page fit 2560 by 1440 with no scrollbar and no large empty area inside a pane
     other than below short content?
  5. Is the `<style>` block free of directly written colors, font families and font sizes,
     are `style.css` and `repo.css` unchanged, and is the page free of `<script>` and images?

### S11: Agents on the left, with the team label
- Do: Create `design/base.html` as a copy of `design/a-chat.html` with the agents on the left
  and a team label, and add the rules it needs to the end of `design/style.css`. Do not change
  or remove any existing rule in `style.css`, and do not change `a-chat.html`.
  - `<body class="left">`. The children of `body` are in this order: the `<div class="side">`
    holding `#agents` above `#phases`, then `#chat`, then `#output`.
  - New rule: `body.left { grid-template-columns: 300px minmax(0, 1fr) minmax(0, 1.15fr); }`.
  - The first child of `#agents` is `<h1 class="team">John's Red Team</h1>`, above the five
    cards: `--fs-l`, weight 600, `--text`, left-aligned with the cards, with no top margin and
    a small space below it. It reads as the title of the agents pane.
  - Links: the Fable 5.2 card goes to `base.html` and the Warp card to `#`. The "Repository"
    tab goes to `idea-1.html` and the "api-design.md" tab to `base.html`.
  - Nothing else changes. The chat, the output pane, the cards and the phases keep their
    content.
- Read: `design/a-chat.html`, `design/style.css`
- Write: `design/base.html`, `design/style.css`
- Covers: R1 as changed, R28
- Size: 1440 by 900
- Done when:
  1. Left to right, are the columns: agents above phases, then the chat, then the output pane?
  2. Does "John's Red Team" sit at the top of the agents pane, above five cards, looking like
     the pane's title?
  3. Are all five cards and all seven phases fully visible without scrolling?
  4. Do the chat and the output pane show the same content as in `a-chat.html`?
  5. Does the page fit 1440 by 900 with no scrollbar?
  6. Is `a-chat.html` unchanged, and does the `style.css` diff only add lines at the end?
  7. Are the new CSS rules free of directly written colors, font families and font sizes, and
     is the page free of `<script>` and images?

### S12: Idea 1, branch chips
- Do: Create `design/idea-1.html` as a copy of `design/base.html` with the repository open in
  the output pane, and `design/idea-1.css` holding the rules this idea needs. The page links
  `style.css`, then `repo.css`, then `idea-1.css`. Do not change `style.css` or `repo.css`.
  - Tabs: "Repository" has `is-chosen` and goes to `idea-1.html`. "api-design.md" is not
    chosen and goes to `base.html`. Remove the "is editing" line and the doc.
  - Below the tabs put `<div class="r1">` filling the rest of the pane, in three rows.
  - Row 1, `r1-branches`: all five placeholder branches as chips in one row, with no wrapping
    and no scrolling. Each chip is an `<a class="r1-chip">` with two lines: the branch name in
    `--mono` at `--fs-s`, and under it the agent's name at `--fs-s` in `--text-3`. Under
    `main` the second line reads "default". The chip for `fable/api-routes` has `is-chosen`:
    `--raised` background and its name in `--text`. The other chips have no background and
    their names are in `--text-2`. Chips have `--radius-s` corners.
  - Row 2 fills the spare height: the `repo-tree` part, 190px wide, at the left, and the
    `repo-code` part beside it. Copy both from `design/a-repo.html` with the same classes and
    content.
  - Row 3, about 170px tall: the `repo-commits` part across the full width, with the label
    "Commits" and the same five commits as in `a-repo.html`. Each commit is on one line: the
    message at the left, and at the right its branch in `--mono`, the agent and the time, in
    `--text-2` at `--fs-s`. The merge still starts with the word "merge".
  - 1px `--line` dividers separate the rows and separate the tree from the code. No glow.
- Read: `design/base.html`, `design/a-repo.html`, `design/style.css`, `design/repo.css`
- Write: `design/idea-1.html`, `design/idea-1.css`
- Covers: R11, R12, R13 as changed, R14 as changed
- Size: 1440 by 900
- Done when:
  1. Is "Repository" the chosen tab, with the repository filling the output pane on the right?
  2. Are all five branches visible as chips in a single row, each with its agent's name under
     it ("default" under `main`), with only `fable/api-routes` marked as chosen?
  3. Are the file tree and the code of `src/routes/users.ts` visible below the chips, with
     the code readable?
  4. Are there five commits across the full width, one line each, with message, branch,
     agent and time, and the merge marked?
  5. Is all text readable, with nothing cut off, overlapping or wrapped?
  6. Are the side column and `#chat` identical to those in `base.html`, and does the page fit
     1440 by 900 with no scrollbar?
  7. Is `idea-1.css` free of directly written colors, font families and font sizes, are
     `style.css` and `repo.css` unchanged, and is the page free of `<script>` and images?

### S13: Idea 2, branch switcher in the tab row
- Do: Create `design/idea-2.html` as a copy of `design/base.html` with the repository open in
  the output pane, and `design/idea-2.css` holding the rules this idea needs. The page links
  `style.css`, then `repo.css`, then `idea-2.css`. Do not change `style.css` or `repo.css`.
  - Tabs: "Repository" has `is-chosen` and goes to `idea-2.html`. "api-design.md" is not
    chosen and goes to `base.html`. Remove the "is editing" line and the doc.
  - At the right end of the tab row, on the same line as the tabs, put a branch switcher:
    `<details class="r2-switch" open>`. Its `<summary>` shows the chosen branch,
    `fable/api-routes`, in `--mono` at `--fs-s` in `--text`, followed by the character "▾" in
    `--text-3`. The summary has a 1px `--line` border and `--radius-s` corners, and the
    browser's own disclosure marker is hidden.
  - Inside the `<details>`, after the summary, is `<div class="r2-menu">`: a menu positioned
    over the pane, just under the summary and aligned to its right edge, 260px wide, with the
    `--raised` background, a 1px `--line` border and `--radius-s` corners. It lists all five
    placeholder branches, one per row: the branch name in `--mono` at `--fs-s`, and the
    agent's name at `--fs-s` in `--text-2` at the right. `main` shows no agent. The row for
    `fable/api-routes` has `is-chosen`: a `--bg` background and `--text` color.
  - The menu floats over the content below it and moves nothing. It is shown open. Because it
    is a `<details>`, clicking the summary closes it with no script.
  - Below the tabs put `<div class="r2">` filling the rest of the pane, in two rows. Row 1
    fills the spare height: the `repo-tree` part, 190px wide, at the left, and the `repo-code`
    part beside it, both copied from `design/a-repo.html` with the same classes and content.
    Row 2, about 170px tall: the `repo-commits` part across the full width, with the label
    "Commits" and the same five commits, each on one line: the message at the left, and at
    the right its branch in `--mono`, the agent and the time, in `--text-2` at `--fs-s`. The
    merge still starts with the word "merge".
  - 1px `--line` dividers separate the rows and separate the tree from the code. No glow.
- Read: `design/base.html`, `design/a-repo.html`, `design/style.css`, `design/repo.css`
- Write: `design/idea-2.html`, `design/idea-2.css`
- Covers: R11, R12, R13 as changed, R14 as changed
- Size: 1440 by 900
- Done when:
  1. Is "Repository" the chosen tab, with the repository filling the output pane on the right?
  2. Does the tab row end, at its right, with a control showing `fable/api-routes` and "▾"?
  3. Is a menu open under that control listing all five branches with their agents, with only
     `fable/api-routes` marked as chosen, floating over the code without pushing it down?
  4. Is the control a `<details>` element, so it opens and closes without script?
  5. Are the file tree, the code and five one-line commits visible, with the merge marked?
  6. Is all text readable, with nothing cut off or wrapped, and nothing overlapping other
     than the menu over the code?
  7. Are the side column and `#chat` identical to those in `base.html`, and does the page fit
     1440 by 900 with no scrollbar?
  8. Is `idea-2.css` free of directly written colors, font families and font sizes, are
     `style.css` and `repo.css` unchanged, and is the page free of `<script>` and images?

### S14: Idea 3, branches as the live list
- Do: Create `design/idea-3.html` as a copy of `design/base.html` with the repository open in
  the output pane, and `design/idea-3.css` holding the rules this idea needs. The page links
  `style.css`, then `repo.css`, then `idea-3.css`. Do not change `style.css` or `repo.css`.
  - Tabs: "Repository" has `is-chosen` and goes to `idea-3.html`. "api-design.md" is not
    chosen and goes to `base.html`. Remove the "is editing" line and the doc.
  - Below the tabs put `<div class="r3">` filling the rest of the pane, in two rows. There is
    no separate commit list in this idea.
  - Row 1 fills the spare height: the `repo-tree` part, 190px wide, at the left, and the
    `repo-code` part beside it, both copied from `design/a-repo.html` with the same classes
    and content.
  - Row 2, `r3-branches`, across the full width, as tall as its content: a label "Branches"
    at `--fs-s` in `--text-3`, then one row per branch, most recent first. Each row is an
    `<a class="r3-row">` on one line with five parts in fixed columns so the rows line up: a
    state dot; the branch name in `--mono` at `--fs-s`; the agent's name at `--fs-s` in
    `--text-2`; the branch's latest commit message at `--fs-m`, taking the spare width and
    ending in "…" if it does not fit; and the time at `--fs-s` in `--text-3` at the right.
  - The rows: working dot, `fable/api-routes`, Fable 5.2, "Add users route handlers", just
    now. No dot, `main`, no agent, "Merge deepseek/auth into main" preceded by the word
    "merge" at `--fs-s` in `--text-3`, 4m. Waiting dot, `deepseek/auth`, Deep Seek, "Add
    session middleware", 9m. Working dot, `glm/web-client`, GLM, "Scaffold web client shell",
    21m. Idle dot, `kimi/cli`, Kimi, "Add command parser", 2h.
  - Use the existing `.dot` classes for the dots. The row for `fable/api-routes` has
    `is-chosen`: a `--raised` background with `--radius-s` corners.
  - 1px `--line` dividers separate the two rows and separate the tree from the code.
- Read: `design/base.html`, `design/a-repo.html`, `design/style.css`, `design/repo.css`
- Write: `design/idea-3.html`, `design/idea-3.css`
- Covers: R11, R12, R13 as changed, R14 as changed
- Size: 1440 by 900
- Done when:
  1. Is "Repository" the chosen tab, with the repository filling the output pane on the right?
  2. Are the file tree and the code of `src/routes/users.ts` visible, with the code readable?
  3. Is there a "Branches" list across the bottom with five rows in the order given, each
     showing a branch, its agent, its latest commit message and a time, in aligned columns?
  4. Do the dots match: working for `fable/api-routes` and `glm/web-client`, waiting for
     `deepseek/auth`, idle for `kimi/cli`, none for `main`?
  5. Is `fable/api-routes` the only row marked as chosen, and is there no separate commit list?
  6. Is all text readable, with nothing cut off (other than a message ending in "…"),
     overlapping or wrapped?
  7. Are the side column and `#chat` identical to those in `base.html`, and does the page fit
     1440 by 900 with no scrollbar?
  8. Is `idea-3.css` free of directly written colors, font families and font sizes, are
     `style.css` and `repo.css` unchanged, and is the page free of `<script>` and images?

### S15: Red theme
- Do: Create `design/red.css` and four red pages: `design/base-red.html`,
  `design/idea-1-red.html`, `design/idea-2-red.html` and `design/idea-3-red.html`. Change no
  other file.
  - `red.css` has a `:root` block that redefines exactly the twelve named values in the "Red
    theme" table, with exactly those values. This is the one place besides `style.css` where
    colors are written directly.
  - `red.css` also makes the small labels monospace capitals: the team label `.team`, the
    phases title, the "in parallel" labels, the repository section labels such as "Files" and
    "Commits", and the "Branches" label in idea 3. Find their class names in the files you
    read. Each gets `--mono`, `--fs-s`, capitals, letter spacing of `0.12em`, and `--text-2`.
  - `red.css` puts a solid `--accent` square, 6px by 6px, before the team label's text, on the
    same line, with a small gap.
  - `red.css` contains nothing else.
  - Each red page is a copy of its purple page (`base.html` for `base-red.html`, and so on)
    with exactly two kinds of change: one `<link rel="stylesheet" href="red.css">` added as
    the last stylesheet link in the `<head>`; and every link to `base.html`, `idea-1.html`,
    `idea-2.html` or `idea-3.html` pointed at the matching `-red` page.
- Read: `docs/INSPIRATION.md` (the "Red theme" section only), `design/base.html`,
  `design/idea-1.html`, `design/idea-2.html`, `design/idea-3.html`, `design/style.css`,
  `design/repo.css`, `design/idea-1.css`, `design/idea-2.css`, `design/idea-3.css`
- Write: `design/red.css`, `design/base-red.html`, `design/idea-1-red.html`,
  `design/idea-2-red.html`, `design/idea-3-red.html`
- Covers: R20 as changed, R28
- Size: 1440 by 900, for each of the four red pages
- Done when:
  1. Does `red.css` redefine exactly the twelve named values from the "Red theme" table, with
     exactly the table's values, and are those the only directly written colors in it?
  2. Does each red page differ from its purple page only by the added `red.css` link and by
     links pointing at `-red` pages?
  3. On all four red pages, is red the only color, with no purple anywhere?
  4. Are the corners of panes and cards nearly square on the red pages?
  5. Does the team label read "John's Red Team" in monospace capitals with a small red square
     before it, on one line, fully visible?
  6. Are the other small labels in monospace capitals, each fully visible with nothing cut
     off, overlapping or wrapped because of the wider lettering?
  7. Does each red page fit 1440 by 900 with no scrollbar, with all five cards and all seven
     phases visible?
  8. Are the four purple pages and the other stylesheets unchanged, and are the red pages
     free of `<script>` and images?

