# Requirements

**Status:** agreed by the user on 2026-11-13, proposals included.

A requirement says what a person must be able to see or do in the UI. Each one traces back to
something the user said in `docs/INTERVIEW.md`. Nothing is built from a requirement the user
has not agreed to.

"Proposed" in the last column means the user did not say it: Claude chose it to fill a gap,
and the user should change it if it is wrong.

## Agents

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R1 | A pane on the right shows five agent cards: Fable 5.2, Warp, Deep Seek, GLM and Kimi. | To manage all of them in one spot. | User |
| R2 | Each card is large and shows the agent's name and one state. Nothing else. | Few persistent agents, so cards can be "bigger and more visually robust and neat as opposed to tiny text". | User |
| R3 | The state is one of three: working, waiting for you, idle. | To see who needs attention without clicking each agent. The user's condition: "if it can be kept simple". | Proposed: the three states |
| R4 | The chosen agent's card is clearly marked. One click on another card switches to that agent, and nothing else on screen changes. | To toggle between agents quickly, as in Grokbot. | User |

## Chat

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R5 | The main area shows the chosen agent's chat: the conversation and a box to type in, arranged like a Claude Code web session. | "Operation just as seamless as Claude Code web." | User |
| R6 | When the chosen agent is Warp, the main area shows a terminal in place of the chat. | "I want my terminal and my agents in one clean spot." | User |

## Output center

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R7 | An output center beside the chat shows one output at a time, such as an artifact or a doc. | To chat about an output while looking at it. | User |
| R8 | Switching agents does not close or change the output center. | "I can switch without the output closing." Reopening it in Claude Code is what annoys the user. | User |
| R9 | The output center shows which agent is changing the output at the moment. | "It's like the whole team is working on the output area." | Proposed: how it is shown |
| R10 | A row of tabs lists the open outputs, and the user switches between them with one click. | There can be more than one output. | Proposed |

## Repository

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R11 | The user can browse the repository's folders and files and read a file's code, inside the dashboard. | "I really just want to read the code in my same dashboard." This is the first priority. | User |
| R12 | The user can see commits and merges as they arrive, newest first. Each shows its message, its branch and which agent made it. | To "watch commits and merges live" without leaving to check git. Who did what is secondary, so it is one name on the line and no more. | User |
| R13 | The user can see all branches at once, each with the agent working on it, and can choose which branch to read. | "Agents will work on different branches, so I want to see branches at once if possible." | User |
| R14 | The layout is designed two ways. In layout A the repository is one of the tabs in the output center. In layout B it is a separate column that is always on screen. The user picks one after seeing both. | "Let's see both ideas in a UI. Separate would be cool but could be too much clutter." | User |

## Phases

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R15 | One pane shows the project's phases in order. Each shows its name and how far along it is. | "We want to see the phases and how far they are." The phases are written by an AI, not the user. | User |
| R16 | Progress on a phase is shown as steps done out of steps total, with a thin bar. | A phase needs some measure of "how far". | Proposed |
| R17 | Phases that run in parallel are drawn side by side. Phases that run one after another are drawn one below the other. | To see "which would run in parallel". | Proposed: how it is drawn |
| R18 | The phases pane is one compact pane. It is not a board of columns. | A kanban "became too complex and space consuming". | User |

## Look

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R19 | Every surface is black or very dark. | "I like dark more than anything, probably black or very dark." | User |
| R20 | There is one accent color, purple, used very subtly. Glow appears only on the chosen agent's card and on a working state. | "Accents should be very subtle. Purple or red is alright." The glow gives the "futuristic and rogue vibe"; too much of it the user dislikes. | Proposed: purple over red, and where the glow goes |
| R21 | The interface uses a plain sans typeface. Code and the terminal use monospace. | Not answered by the user. | Proposed |
| R22 | Nothing is on screen that R1 to R18 do not call for. No charts, no decorative panels. | "I don't want abstractions." Over-engineered screens "make me ADHD". | User |

## Screen

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R23 | On a laptop, at 1440 by 900, the agent cards, the chat and the output center are all visible at once with no sideways scrolling. | "A laptop mostly." | Proposed: the size |
| R24 | On a laptop the phases pane is either visible or opens with one click, and opening it closes neither the chat nor the output center. | The user wants the phases "somewhere", without clutter. | Proposed |
| R25 | On a large monitor, at 2560 by 1440, the extra room is used to show more at once. The laptop layout is not simply stretched. | "Large monitor flexibility be nice." | Proposed: the size |

## What gets delivered

| ID | Requirement | Why the user wants it | Source |
|---|---|---|---|
| R26 | The design is delivered as static HTML and CSS pages in `design/`, with placeholder content and no working logic. | UI design only. Someone else builds the working system from it. | Proposed: the format |
| R27 | The pages cover: layout A on a laptop; layout B on a laptop; a chat agent chosen; Warp chosen; the repository view; an empty output center; and the large-monitor layout. | So the builder has every main state, and the user can compare the two layouts. | Proposed |

## Out of scope

- Functioning software: no backend, real data, auth or working logic.
- Issue tracking of the kind Paperclip does.
- A kanban board.
- Proposed, not discussed: a phone layout, and screens for settings, login or first-time setup.

## Agreement

**Agreed by the user:** yes, 2026-11-13. "Agreed proceed." This covers R1 to R27, the twelve
proposals among them, and the out-of-scope list.

## Changes after agreement

Record any change here with the date and the user's agreement, then update the tables.

| Date | Change | Agreed |
|---|---|---|
| | | |
