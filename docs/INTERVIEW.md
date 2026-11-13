# Interview

**Status:** in progress. Started 2026-11-13.

The aim is to understand why the user wants this, not only what they asked for. Record what
they say in their own words. Mark anything you inferred as an inference.

## What to find out

- Why they want this, and why now. What happens if it never gets built.
- Who will use it, and what those people are trying to get done.
- What they do today instead, and where that falls short.
- The few things a person must be able to do in the UI, in order of importance.
- Where it will be used: device, screen size, setting, how often and for how long.
- How it should feel to use, and what they have seen that feels like that.
- What they have not thought about yet: empty states, errors, first use, edge cases.
- What is out of scope.

## Summary

Not written yet. A short account of the user's vision, in plain words. The interview is over
when the user reads this and agrees with it.

**Agreed by the user:** no

## What the user has described so far

From the user's 2026-11-13 answer. Their words where possible. Not yet agreed as a summary.

- **What it is:** one neat, clean, minimalistic dashboard to manage four agents in one spot:
  Fable 5.2, Warp, Deep Seek and GLM. No abstractions.
- **Agents pane (right):** a simple pane showing each agent as a card with its name, so the
  user can choose which agent to engage. "Think paperclip or grokbot but more simple."
- **Git column:** one column showing the active git repository, presented as an overlay in a
  beautiful dark format that fits the rest of the UI. The user can click into each folder and
  see how agents are interacting with it.
- **Steps pane:** somewhere, one simple pane showing the project broken into steps with
  progress on them, and maybe which steps are parallel and which are not. The user liked the
  idea of a kanban, but it became too complex and took too much space. Simplest solution wins.

## Open questions

- Why now: what the user does today to manage the four agents, and where that falls short.
- What "engage" means: what the user sees and does after choosing an agent's card.
- What fills the rest of the screen besides the agents pane, the git column and the steps pane.
- What "see how agents are interacting with it" should show for a folder or file.
- Whether the git column is always visible or an overlay that opens over something else. The
  user used both words.
- Where the steps come from, and what a step's progress looks like.
- Which products "paperclip" and "grokbot" are, and what about them to keep or simplify.
- The four agents are different kinds of thing. What the user means by each one, and whether
  the list is fixed at four.
- Device and screen size.
- The two heavy pins are kanban boards, but the user found a kanban too complex for the steps
  pane. Whether those pins now stand for their look only.

## Log

Add each exchange as it happens, newest last.

| Date | Question | Answer |
|---|---|---|
| 2026-11-13 | None. The user said this while sharing their Pinterest board. | Simple boards that are dark and have columns with tasks are more applicable to this project than the other pins. Inference, not confirmed: the UI centers on a board of columns that hold tasks. (Later the same day the user said a kanban had become too complex for showing steps; see the next row.) |
| 2026-11-13 | What are you building, and why? | "I'm trying to create a neat clean dashboard where I manage: Fable 5.2, Warp, Deep Seek, GLM. All in one spot. I don't want abstractions. I want a minimalistic clean dashboard." Right pane: "a simple pane to see each agent so I can choose to engage the agent I want. Think paperclip or grokbot but more simple. You see the name of the agent and card for it. Simple." Git: "one column where I see the active git but represented as an overlay in a beautiful dark screen format that integrates smoothly with the UI. I can go click in each folder and see how agents are interacting with it." Steps: "Somewhere, I can see the project broken into steps and see progress on it. Simplest solution here. I liked the idea of a kanban but it became too complex and space consuming. One simple pane where we can see the project broken into steps in some way and maybe see which are parallel and which are not." The why was not answered. |
