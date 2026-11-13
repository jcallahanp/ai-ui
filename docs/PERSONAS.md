# Personas

**Status:** written 2026-11-13 from the agreed requirements. Not shown to the user separately:
every check below restates a requirement the user agreed to, and the user said to proceed.

A persona is a real kind of person from the interview, not an invented one. Each has "done
when" checks: questions that someone looking at the design can answer yes or no. The design is
finished when every check is a yes.

## P1: The operator

- **Who they are:** the user. One person running five agents on their own projects: Fable 5.2,
  Warp, Deep Seek, GLM and Kimi.
- **What they are trying to get done:** work with all five from one place and switch between
  them quickly, while watching what they produce and what lands in the repository.
- **Where and how they use it:** mostly a laptop, sometimes a large monitor. Open for long
  stretches while the agents work.
- **What gets in their way today:** switching between Warp and separate agent tools. Paperclip
  was too complex and made issues for everything. In Claude Code, an artifact has to be
  reopened after moving to another chat. Crowded screens are hard for them to use.
- **Done when:**
  - P1.1: On a laptop page, are all five agents' names and states visible without clicking or
    scrolling? (R1, R2, R3)
  - P1.2: Is it obvious at a glance which agent is chosen? (R4)
  - P1.3: Is the chosen agent's chat visible, with a box to type in? (R5)
  - P1.4: With Warp chosen, is there a terminal where the chat was? (R6)
  - P1.5: Is an output visible beside the chat, with tabs for the other open outputs? (R7, R10)
  - P1.6: Is the output center the same on the page where Fable 5.2 is chosen and the page
    where Warp is chosen? (R8)
  - P1.7: Does the output center say which agent is changing the output? (R9)
  - P1.8: In the repository view, can you see the folder tree and read a file's code? (R11)
  - P1.9: Are commits and merges listed newest first, each with its message, branch and
    agent? (R12)
  - P1.10: Is every branch visible at once, each with its agent, and is the chosen branch
    marked? (R13)
  - P1.11: Are there two layouts to compare: one with the repository as a tab in the output
    center, one with it as a separate column? (R14)
  - P1.12: Does one compact pane show the phases in order, how far along each is as a count
    and a thin bar, and which phases run in parallel? (R15, R16, R17, R18)
  - P1.13: Is every surface black or very dark, with purple the only color, and glow only on
    the chosen card and on working states? (R19, R20)
  - P1.14: Is there nothing on screen besides agents, the chat or terminal, the output
    center, the repository and the phases? (R22)
  - P1.15: At 1440 by 900, are the agent cards, the chat, the output center and the phases
    all visible with no sideways scrolling? (R23, R24)
  - P1.16: At 2560 by 1440, does the page show more at once than the laptop page does? (R25)

## P2: The builder

- **Who they are:** whoever turns this design into the working system. The user said the
  design "will then be built into a functioning system".
- **What they are trying to get done:** build exactly what was designed without guessing.
- **Where and how they use it:** they open the design files in a browser and read the HTML
  and CSS.
- **What gets in their way:** a design that leaves states out, or that hides its colors and
  sizes in scattered one-off values.
- **Done when:**
  - P2.1: Does every page in `design/` open in a browser straight from the file, with no build
    step and no server? (R26)
  - P2.2: Do the pages contain no script? (R26)
  - P2.3: Is there a page for each state in R27?
  - P2.4: Are the colors, typefaces and sizes defined once, as named values in
    `design/style.css`, and used by name everywhere else? (R21, R26)
