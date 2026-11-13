# Inspiration

**Status:** done on 2026-11-13. The design direction at the end of this file is final for the
build.

## Source

- Board: [AI project ideas](https://www.pinterest.com/jcallahanp/ai-project-ideas/)
- The board opens in a browser without a Pinterest login. No connector or API key is needed.
- It held 13 pins on 2026-11-13. Three images are pinned twice, so there are 10 unique images.
  The user says the duplicates are an accident, so they carry no extra weight.
- The image files are not copied into this repo. The repo is public and the images are other
  designers' work, so each pin links to the full-size image on Pinterest's image host instead.
  Open the link to look at a pin.

## Weighting

The user's instruction, 2026-11-13: simple boards that are dark and have columns with tasks
are more applicable to this project, and count for more than the other pins.

Pins 3 and 7 are the two that fit that description, so they are marked **heavy**. Marking those
two is Claude's reading of the instruction; the user has not confirmed the choice. Where a
heavy pin and another pin disagree, the heavy pin wins.

Later on 2026-11-13 the user said a kanban had become too complex and space-consuming for
showing project steps, and asked for one simple pane instead. So do not copy the four-column
kanban structure from pins 3 and 7. Whether those pins now count for their look only is an
open question in `docs/INTERVIEW.md`.

## Pins

Numbered in board order.

| # | Image | Weight | What it shows |
|---|---|---|---|
| 1 | [Sidebar navigation](https://i.pinimg.com/originals/72/cc/3e/72cc3e5ab9382fdc1b417aca48bc9327.jpg) | normal | One dark sidebar in two states: expanded with labels, and collapsed to an icon rail with a tooltip. Section labels in small caps, an expandable item with colored-dot sub-items, a white count badge. |
| 2 | [Health age report](https://i.pinimg.com/736x/2b/ed/78/2bed7870ed9dc9474c46c146058bde37.jpg) ([original, AVIF](https://i.pinimg.com/originals/2b/ed/78/2bed7870ed9dc9474c46c146058bde37.avif)) | normal | Translucent glass panels over a sunset ocean photo. A large radial gauge in the center, a radar chart, and many small stat panels. |
| 3 | [Project kanban board](https://i.pinimg.com/originals/7e/c9/f3/7ec9f3777cc2688d3467fa93457529d4.jpg) ([pin page](https://www.pinterest.com/pin/934567360199385753/)) | **heavy** | Pinned twice. Near-black with neutral greys and no glow. Sidebar with a team switcher, search, icon nav and folders. Breadcrumb, then Board / List / Timeline / Due Tasks tabs with Filter and Sort. Four columns (To Do, In Progress, In Review, Completed), each with a colored bar, a count, and add and menu buttons. Dense cards: client line, task title, assignee chip, colored tags, and a row of small counts. |
| 4 | [Finance dashboard, lavender](https://i.pinimg.com/originals/8e/5c/9f/8e5c9f0594f60ac42d7daca70eab255b.png) | normal | Near-black with a soft lavender glow. Icon rail, a line chart, a transactions table, balance cards and a transaction list. |
| 5 | [Inbox](https://i.pinimg.com/originals/a0/a1/35/a0a13575b43695fa666203511cb59d00.jpg) | normal | Dark charcoal. Sidebar with a store switcher, grouped nav, and a bright blue active item. Message list with avatars, unread badges and collapsible groups, next to a conversation pane. |
| 6 | [AI agent dashboard](https://i.pinimg.com/originals/34/2d/b0/342db0edaae5a350e094358856c718ef.jpg) | normal | Purple on black, glass panels drawn in perspective. Stat tiles, charts, a list of active agents with percentages, an assistant prompt box, recent activity, and a trigger-to-actions workflow diagram. |
| 7 | [Task board](https://i.pinimg.com/originals/02/a9/c2/02a9c20ef15522908c2f1c2360245f06.png) | **heavy** | Dark navy panels over a dimmed coastal photo. Sidebar with a boards switcher, search with a shortcut hint, and a tree of views. Four columns (Backlog, Planning, Doing, Done) with small uppercase labels and counts. Large sparse cards: an ID, a title, a colored left edge (blue or red), a progress bar and avatars. The Done column is dimmed. A capacity strip runs along the bottom. |
| 8 | [Analytics dashboard, purple](https://i.pinimg.com/originals/cb/ef/a1/cbefa14099e257562bcb757d8b559c24.jpg) | normal | Purple and indigo glass cards on black. Icon rail, area and bar charts, a gauge, a donut and a world map. |
| 9 | [Banking dashboard](https://i.pinimg.com/originals/08/e7/e2/08e7e2d606baf9a7dc2912b3f20c3db3.jpg) | normal | Pinned twice. Dark slate panels with soft raised shadows. Icon rail, a bank card, category tiles, two lists, a ring showing the balance, and thin gradient bars. |
| 10 | [Developer feed](https://i.pinimg.com/originals/5a/4c/13/5a4c13d373fa70c0f78e7d287874cf36.png) | normal | Pinned twice. Warm near-black, monospace type throughout, one orange accent. Sidebar nav, a post composer, Following / Featured / Rising tabs, and a post containing a code block. |

## What the user likes

The user answered for the board as a whole on 2026-11-13, not pin by pin.

- **The dark theme.** "I like that they are dark themed. They have a sort of futuristic yet
  minimalist rogue vibe."
- **How dark:** "I like dark more than anything, probably black or very dark." This was the
  answer to whether pin 3's flat grey or pin 7's navy over a photo is closer. It settles the
  color, toward black. It does not settle dense cards against sparse ones.
- **Glow, in moderation.** "It's the sort of futuristic and rogue vibe that the glow gives
  that draws me, while overengineering of it tends to make me ADHD and I dislike it." So the
  glow is wanted for the mood it gives, and a screen crowded with it is not.

## Observations

These are Claude's, from looking at the pins. The user has not agreed to any of them.

- All ten pins are dark, and all ten have a left sidebar or icon rail.
- The two heavy pins share a structure: a sidebar with a switcher and search at the top, four
  columns with a label and a count, and cards as slightly raised dark rectangles carrying a
  thin colored status marker.
- The two heavy pins disagree on surface and density. Pin 3 is flat neutral grey with dense
  cards full of tags and counts. Pin 7 is navy over a photo with sparse cards that show little
  more than a title.
- Most of the normal-weight pins use purple glow, glass or perspective. That pulls against
  "simple", which is the word the user used for the heavy pins.

## Questions for the user

All answered or settled on 2026-11-13. What the user likes, the duplicate pins, how dark, the
glow and the accent color are recorded above. Type and density were settled by requirements
R2, R21 and R22, which the user agreed to.

## Design direction

Final for the build. It follows requirements R19 to R22, which the user agreed to on
2026-11-13. It was not put to the user separately; the user said to proceed. The mood, the
dark surfaces and the subtle purple accent are the user's. The exact values are Claude's.

- **Mood:** futuristic, minimalist, rogue. Quiet and black, with one small point of light.
- **Color:** near-black surfaces in three steps, hairline borders, and grey text in three
  steps. Purple is the only color. No green, red, blue or orange anywhere, including in code.
- **Glow:** only on the chosen agent's card and on a "working" dot. Nowhere else.
- **Type:** Inter for the interface. JetBrains Mono for code, the terminal, file names and
  branch names. Three sizes only.
- **Layout and spacing:** a few rounded panes on a black page, 8px apart. Generous padding
  inside each pane. Sparse, as in pin 7, not dense, as in pin 3: a row shows a name and one or
  two facts, never a line of tags and counts.
- **Components:** panes, agent cards, tabs, a chat, a terminal, a file tree, a code viewer, a
  commit list, a branch list and phase rows. Nothing else. No sidebar or icon rail, although
  every pin has one: the user did not ask for one. No icons unless a step calls for one.
- **Motion:** none. These are static pages.
- **States without color:** working is a purple dot with glow. Waiting for you is a solid
  white dot. Idle is a hollow grey ring. The state's name is always written next to the dot.
- **Avoid:** over-engineered glow, gradients, glass, photos behind panels, charts, decorative
  panels, and the multi-column kanban structure.

### Named values

`design/style.css` defines exactly these, with these names and values, in a `:root` block.
Every other rule uses them by name.

| Name | Value | Used for |
|---|---|---|
| `--bg` | `#050506` | The page behind the panes |
| `--pane` | `#0b0b0e` | Panes |
| `--raised` | `#121216` | Cards, the chosen tab, input boxes, code blocks |
| `--line` | `#1d1d23` | Hairline borders and dividers |
| `--text` | `#e9e9ee` | Main text |
| `--text-2` | `#9a9aa5` | Secondary text |
| `--text-3` | `#6b6b76` | Muted labels, line numbers, comments in code |
| `--accent` | `#8b5cf6` | The one color: chosen states, working dots, progress bars, keywords in code |
| `--accent-soft` | `rgba(139, 92, 246, 0.14)` | A faint purple fill |
| `--glow` | `0 0 22px rgba(139, 92, 246, 0.28)` | The glow, as a `box-shadow` |
| `--sans` | `"Inter", system-ui, -apple-system, "Segoe UI", sans-serif` | Interface text |
| `--mono` | `"JetBrains Mono", ui-monospace, "SF Mono", Menlo, monospace` | Code, terminal, file and branch names |
| `--fs-s` | `12px` | Labels, states, counts |
| `--fs-m` | `13px` | Body text, code |
| `--fs-l` | `15px` | Agent names, pane titles |
| `--gap` | `8px` | Space between panes and between cards |
| `--pad` | `16px` | Padding inside a pane |
| `--radius` | `12px` | Pane corners |
| `--radius-s` | `8px` | Corners of cards, tabs, inputs |

### Red theme

Added 2026-11-13 at the user's request: "a secondary red themed one with a more rogue vibe".
It is an alternative to the purple theme, not a replacement. The values are Claude's.

The red theme is the same pages with `design/red.css` loaded after the other stylesheets.
It changes four things and nothing else:

- **Color:** red takes the place of purple as the only color. The blacks and greys lose their
  blue tint and become neutral.
- **Corners:** nearly square, where the purple theme is rounded.
- **Labels:** small labels are in the monospace face, in capitals, widely spaced: the team
  label, pane titles, and section labels such as "Branches", "Files" and "in parallel".
- **Team label:** a small solid red square sits before "John's Red Team".

`red.css` redefines exactly these named values. Every other named value keeps its value.

| Name | Value |
|---|---|
| `--bg` | `#040404` |
| `--pane` | `#0a0a0a` |
| `--raised` | `#131313` |
| `--line` | `#222222` |
| `--text` | `#ededed` |
| `--text-2` | `#9b9b9b` |
| `--text-3` | `#6c6c6c` |
| `--accent` | `#dc2f3c` |
| `--accent-soft` | `rgba(220, 47, 60, 0.14)` |
| `--glow` | `0 0 22px rgba(220, 47, 60, 0.3)` |
| `--radius` | `4px` |
| `--radius-s` | `2px` |
