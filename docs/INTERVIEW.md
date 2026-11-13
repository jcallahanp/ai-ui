# Interview

**Status:** done. The user agreed with the summary on 2026-11-13.

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

Written 2026-11-13. The user agreed with it the same day and added one thing in the same
message: branches, now part of point 4.

The user runs five agents: Fable 5.2, Warp (their terminal), Deep Seek, GLM and Kimi. Today
they lose time switching between tools to work with them. They want one dark, minimal
dashboard where the terminal and the agents sit together and they can toggle between them
without leaving. It is used mostly on a laptop and should also make good use of a large monitor.

The dashboard has five parts:

1. **Agents pane, on the right.** Five large cards, one per agent, each showing the agent's
   name and a simple state. Clicking a card switches to that agent at once.
2. **Chat, in the main area.** The chosen agent's chat, as smooth to use as a Claude Code web
   session. For Warp it is a terminal.
3. **Output center.** One area that stays open while the user switches agents. It shows what
   the agents are producing, such as an artifact or a doc, and all the agents work on the same
   output. The user watches it change and chooses whom to talk to.
4. **Repository.** The active git repository, readable inside the dashboard: browse folders,
   read code, and watch commits and merges arrive live. Agents work on different branches, so
   the user wants to see the branches at once if possible. Who did what is secondary. To be
   designed two ways for the user to choose: as one of the things the output center shows, and
   as a separate column that is always on screen.
5. **Phases pane.** The project broken into phases by an AI, showing which phases run in
   parallel and how far along each is. One simple pane, not a kanban.

The look: black or very dark, futuristic, minimalist and rogue, with glow used sparingly.
Accents are very subtle; purple or red is acceptable. Nothing crowded or over-engineered.

Out of scope: functioning software, and issue tracking of the kind Paperclip does.

**Agreed by the user:** yes, 2026-11-13

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
- **State on the card:** a card may show what its agent is doing (working, waiting for the
  user, idle), on one condition from the user: "if it can be kept simple".
- **Screen:** "A laptop mostly. But large monitor flexibility be nice." Design for a laptop
  first. A large monitor should get a good layout too, not a stretched laptop one.

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
  An AI breaks the project into phases; the user does not write them. The pane shows the
  phases, which of them run in parallel, and how far along each one is.
- **Repository placement, to be shown both ways:** the user wants to see two versions of the
  layout and choose. In one the repository is one of the things the output center shows. In
  the other it is a separate column that is always on screen. The user's lean: separate "would
  be cool but could be too much clutter".

## Open questions

The interview is over. These were not answered. Each is settled by a proposal in
`docs/REQUIREMENTS.md` that the user agrees to or changes, or by the user choosing between
designs.

- Which of the two repository placements the user picks, once they have seen both designed.
- How the user moves between outputs in the output center.
- How progress on a phase is measured and shown.
- The typeface. The user answered the accent color but not the type.

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
| 2026-11-13 | Is the repository one of the things the output center shows, or a separate column that is always on screen? | "Let's see both ideas in a UI. Separate would be cool but could be too much clutter." |
| 2026-11-13 | For the steps pane, where do the steps come from and what do you want to see at a glance? | "Probably have an AI break it into phases. We want to see the phases and then which would run in parallel and how far they are." |
| 2026-11-13 | What screen will you use this on? | "A laptop mostly. But large monitor flexibility be nice." |
| 2026-11-13 | Should an agent's card show what the agent is doing (working, waiting for you, idle)? | "If it can be kept simple." |
| 2026-11-13 | Is the summary right? | "Yes." |
| 2026-11-13 | What color is the glow, and what kind of type? | "Accents should be very subtle. Mostly a dark theme. Purple or red is alright." The type was not answered. |
| 2026-11-13 | None. The user added this unprompted. | "Agents will work on different branches, not just files in git, so I want to see branches at once if possible." |
