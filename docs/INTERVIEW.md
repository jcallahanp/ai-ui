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

From the user's 2026-11-13 answers. Their words where possible. Not yet agreed as a summary.

- **Why:** today the user has to switch between Warp (their terminal) and their coding agents.
  They want the terminal and the agents in one clean spot, so they can toggle through them
  without leaving the UI. The point is to save time.
- **What they tried:** Paperclip. It was too complex: "it creates issues for everything", and
  it does not let them toggle through agents quickly the way Grokbot does. Keep the quick
  toggling. Leave out the issue-tracking overhead.
- **Engaging an agent:** choosing an agent's card "just spawns its chat". Operation should be
  as seamless as Claude Code on the web: like a regular Claude session, except the agent
  behind it may be an open-weight model or a terminal.
- **Few, persistent agents:** there are only a handful and they are persistent, so their cards
  can be bigger, "more visually robust and neat as opposed to tiny text". Toggling between
  them must be swift.

- **What it is:** one neat, clean, minimalistic dashboard to manage five agents in one spot:
  Fable 5.2, Warp, Deep Seek, GLM and Kimi. No abstractions.
- **Layout the user agreed to** ("I like this", 2026-11-13): the agents pane on the right with
  a few large cards; the main area holds the chosen agent's chat, or a terminal when the agent
  is Warp; the git column and the steps pane sit alongside.
- **Agents pane (right):** a simple pane showing each agent as a card with its name, so the
  user can choose which agent to engage. "Think paperclip or grokbot but more simple."
- **Git column:** one column showing the active git repository, presented as an overlay in a
  beautiful dark format that fits the rest of the UI. The user can click into each folder.
  **First priority:** read the code and watch commits and merges arrive live, without leaving
  the dashboard to check git. **Secondary:** seeing which agent did what. Nice, not essential.
- **Shared output center:** one output area that stays fixed while the user toggles between
  agents. It shows what the agents are producing, "not just the git, like artifacts or a doc
  or something", and all the agents can work on the same output. The user watches it change
  while choosing which agent to talk to. "It's like the whole team is working on the output
  area, but I choose which team member I want to be clicked in, and I can switch without the
  output closing." It comes from Claude Code, where an artifact opens beside a chat and
  several sessions can work on it. What annoys the user there is having to reopen the
  artifact after moving to a different chat.
- **Steps pane:** somewhere, one simple pane showing the project broken into steps with
  progress on them, and maybe which steps are parallel and which are not. The user liked the
  idea of a kanban, but it became too complex and took too much space. Simplest solution wins.

## Open questions

- Whether the repository view is one of the things the output center shows, next to
  artifacts and docs, or a separate column that is always on screen as well. Inference, not
  confirmed: it is one of the things the output center shows.
- How the user moves between outputs in the output center, and how many there are at once.
- How five areas (agent cards, chat, output center, repository, steps) fit on one screen
  without it becoming crowded, which the user dislikes.
- Where the steps come from, and what a step's progress looks like.
- Whether a terminal agent (Warp) looks the same as a chat agent or different.
- What an agent's card shows besides its name, for example whether it is working or idle.
- Device and screen size.
- The two heavy pins are kanban boards, but the user found a kanban too complex for the steps
  pane. Whether those pins now stand for their look only.

## Log

Add each exchange as it happens, newest last.

| Date | Question | Answer |
|---|---|---|
| 2026-11-13 | None. The user said this while sharing their Pinterest board. | Simple boards that are dark and have columns with tasks are more applicable to this project than the other pins. Inference, not confirmed: the UI centers on a board of columns that hold tasks. (Later the same day the user said a kanban had become too complex for showing steps; see the next row.) |
| 2026-11-13 | What are you building, and why? | "I'm trying to create a neat clean dashboard where I manage: Fable 5.2, Warp, Deep Seek, GLM. All in one spot. I don't want abstractions. I want a minimalistic clean dashboard." Right pane: "a simple pane to see each agent so I can choose to engage the agent I want. Think paperclip or grokbot but more simple. You see the name of the agent and card for it. Simple." Git: "one column where I see the active git but represented as an overlay in a beautiful dark screen format that integrates smoothly with the UI. I can go click in each folder and see how agents are interacting with it." Steps: "Somewhere, I can see the project broken into steps and see progress on it. Simplest solution here. I liked the idea of a kanban but it became too complex and space consuming. One simple pane where we can see the project broken into steps in some way and maybe see which are parallel and which are not." The why was not answered. |
| 2026-11-13 | What do you do today to run these four agents, and where does it fall short? | "I have to switch between Warp and my coding agents etc. I can collaborate with them all in one spot. I tried Paperclip but it is complex, it creates issues for everything, and I can't just toggle through agents super quickly like Grokbot. I want my terminal and my agents in one clean spot so I can toggle through them without leaving my UI, to save me time." |
| 2026-11-13 | What happens after you click an agent's card? | "It just spawns its chat for me. The goal is operation just as seamless as Claude Code web. Imagine just a regular Claude session on my side panel, but it was an open-weight model or a terminal, and there's only 5 of them that are persistent agents, so they are bigger and more visually robust and neat as opposed to tiny text. But the idea is toggle through and swift operation, just like a Claude cloud session." |
| 2026-11-13 | Claude described the layout back: agents pane on the right, the chosen agent's chat or terminal in the main area, git column and steps pane alongside. | "I like this." |
| 2026-11-13 | Is it four agents or five? | "Kimi as well." Five: Fable 5.2, Warp, Deep Seek, GLM, Kimi. |
| 2026-11-13 | When you click into a folder in the git column, what do you want to see about the agents? | "The main thing is just see the repo in my dashboard without leaving to check git, so I can just watch commits and merges live. Visibility into who did what is nice but it's actually secondary. I really just want to read the code in my same dashboard." |
| 2026-11-13 | None. The user added this unprompted. | "One thing that is easy about Claude Code is that agents can interact with artifacts, so I can tell different sessions to interact with the same artifact. I like that I can open it beside a chat and feel like I'm chatting about an artifact. What annoys me is that when I go to a different chat I have to reopen it. It would be cool if I could sort of see agents outputting things and they can collaborate on one output center (not just the git, like artifacts or a doc or something), but it stays fixed so that I basically can see agents interacting and changing it while I toggle through them. It's like the whole team is working on the output area, but I choose which team member I want to be clicked in, and I can switch without the output closing." |
