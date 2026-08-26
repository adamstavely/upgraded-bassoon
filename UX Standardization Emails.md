# UX Standardization Initiative: Communications

Four emails. Send the first to everyone once. Send each tasking email when its phase opens, with the corresponding template attached. Placeholders are in [brackets].

---

## Email 1: Initiative introduction (to all engineering, product, and design)

**Subject:** UX Standardization Initiative: what we are doing and why it matters

Team,

Over the coming months we are running a structured effort to standardize the user experience across our application suite. This note explains what that means, why it is worth your time, and what to expect. Three short tasking emails will follow, one per phase.

**The situation**

We are one organization built from several. Our applications were designed and built by different teams, at different times, against different libraries and conventions. Individually, most of them are good. Together, they are inconsistent: different buttons, different spinners, different ways of telling a user that a search found nothing, different date formats on adjacent screens. Our users do not experience our applications one at a time. They move between them, often within a single task, and every inconsistency is a small tax on their attention.

**Why this matters to users**

The case for consistency is not aesthetic preference; it is grounded in how people actually work with interfaces. A few of the better-established principles, drawn from the Laws of UX collection and from Nielsen Norman Group's usability heuristics:

- Jakob's Law: users spend most of their time in other interfaces and bring those expectations with them. Within a suite, the "other interfaces" are ours. Every application that behaves differently from its neighbors forces relearning.
- Consistency and Standards (Nielsen's fourth heuristic): users should not have to wonder whether different words, situations, or actions mean the same thing. When Delete means one thing in one app and Remove means the same thing in another, we are creating that doubt.
- The Doherty Threshold: productivity rises sharply when the system responds within about 400 milliseconds, and when it cannot, the interface must show that it is working. A silent freeze during a load is worse than a slow load with a visible indicator. We currently have no picture of how our applications behave while they wait.
- Hick's Law and Miller's Law: decision time grows with the number of options, and working memory is limited. Inconsistent navigation and controls increase the effective number of things a user has to hold in mind.
- Fitts's Law: the time to reach a target depends on its size and distance. Standardizing control sizes, placement, and spacing is a measurable ergonomic improvement, not decoration.
- Aesthetic-Usability Effect: users perceive a coherent, well-crafted interface as easier to use, and are more tolerant of minor problems in it. Incoherence has the opposite effect: it lowers trust in the software and, by extension, in the data it presents.
- Peak-End Rule: users judge an experience by its most intense moment and its end. Error states, empty states, and confirmations are disproportionately those moments. They are also the places our applications diverge the most.
- Tesler's Law: every system has an irreducible amount of complexity. The question is who carries it. Right now, our users carry complexity that we could absorb once, centrally, in a shared design system.

**Why this matters to us**

Beyond the user, standardization is an engineering economy. Organizations that have consolidated onto a shared design system consistently report that duplicated component work drops, accessibility fixes land once instead of per application, onboarding is faster because engineers move between codebases without relearning conventions, and design and engineering spend less time renegotiating decisions that have already been made. We also have obligations under our accessibility target that are far cheaper to meet in one shared component library than in a dozen separate ones. Trenchcoat, our design system, exists for this reason. This initiative is how we find out how far each application is from it and plan the path.

**What we are going to do**

We cannot standardize what we have not measured. The initiative runs in three phases, each a structured inventory completed by the team that owns each application:

1. Phase 1, Interface Inventory: the visual foundations. Framework, iconography, typography, color, spacing, and where each is defined.
2. Phase 2, Component Inventory: what those foundations are attached to. Which components each application uses, whether they come from a library or are custom, how far they have drifted, and roughly what it would cost to converge.
3. Phase 3, Patterns Inventory: how the application behaves. Loading and empty states, loaders and spinners, error handling, motion, microcopy, form behavior, and charting conventions.

Each phase is a spreadsheet template with instructions, a column guide, and dropdowns to keep answers comparable. Each takes a few hours per application. The output is a suite-wide picture that lets us make consolidation decisions on evidence rather than opinion, and sequence the work so that the highest-value, lowest-effort convergence happens first.

**What this is not**

This is not an audit of teams and it is not a judgment of past decisions. Every application was built under real constraints, and the inconsistency we are measuring is the natural result of parallel work. A messy inventory is a good inventory. Please report what exists, not what you wish existed.

**What I need from you**

When the tasking emails arrive, assign a front end engineer who knows the codebase, give them the time the template asks for, and return it by the date in the email. Questions and pushback are welcome; send them to me directly.

Thank you for taking this seriously. Consistency is the least visible feature we can ship and one of the most valuable.

Build well,

Adam

---

## Email 2: Phase 1 tasking

**Subject:** UX Standardization Phase 1: Interface Inventory due [date]

Team,

Phase 1 of the UX Standardization Initiative is open. The attached workbook, Phase1_Interface_Inventory_Template.xlsx, is the mechanism. Please complete one copy per application your team owns and return it by [date].

**What Phase 1 captures**

A factual baseline of each application's front end: framework and version, styling mechanism, published documentation links, and four inventories covering iconography, typography, color, and spacing and layout, each in both light and dark mode where applicable. It also asks a small number of profile questions about design tokens, theme support, and accessibility targets.

**Who should complete it**

A front end engineer who works in the codebase. Design input is helpful for the "design system equivalent" columns but is not required. Plan for two to four hours, up to a day if styles are scattered across the codebase.

**How to complete it**

1. Read the Instructions sheet first. It is short and answers most questions.
2. Fill the pale yellow cells. Row 2 of each inventory sheet is a grey example of the expected format.
3. Use the dropdowns where they exist. Hover over any column header for a definition, an example, and where to find the value, or use the Column Guide sheet.
4. Inventory every distinct value in use, not just the intended ones. Fourteen shades of grey is a legitimate answer.
5. Enter Unknown rather than leaving a cell blank when a value cannot be determined.
6. Save as [ApplicationName]_Phase1_Inventory.xlsx and return it to [contact].

Please do not add, remove, or rename columns or sheets; submissions are consolidated by script. Add rows freely.

**Ground rules**

Report production, not the design file. Partial and on time beats complete and late. There is no wrong answer except a guessed one.

Questions to [contact]. Thank you.

Build well,

Adam

---

## Email 3: Phase 2 tasking

**Subject:** UX Standardization Phase 2: Component Inventory due [date]

Team,

Thank you for the Phase 1 submissions. Phase 2 is now open. The attached workbook, Phase2_Component_Inventory_Template.xlsx, is the mechanism. One copy per application, same application names as Phase 1 so the two can be joined, due [date].

**What Phase 2 captures**

Phase 1 told us what values exist. Phase 2 tells us what they are attached to. The workbook is pre-populated with 46 canonical components (buttons, inputs, navigation, containers, data display, feedback, and data visualization). For each one you answer the same set of questions: does it exist in your app, what is it called locally, how is it implemented relative to your UI library, how many distinct implementations exist, roughly how often it is used, which variants and states are built, how accessible it is, whether it uses the tokens you inventoried in Phase 1, what its Trenchcoat equivalent is, and a rough replace effort.

**Why this phase is the important one**

Standardization happens at the component level, because components are what teams actually replace. The single most valuable column is Implementation: a library component that has been heavily overridden is, for migration purposes, closer to a custom component than to the library, and Phase 1 cannot see that distinction. Please answer it honestly. Three different button components in one application is a finding, not a failure.

**How to complete it**

1. Read the Instructions sheet.
2. Work down the Component Inventory sheet. Answer "Exists in this app?" first on every row; if No, leave the rest of the row blank and move on.
3. Match what you use to the closest canonical row even if your name differs, and record your name in "Local name in code." Add anything genuinely missing in the blank rows at the bottom.
4. Paste a screenshot of the most common variant where asked, or link to Storybook or Figma.
5. Save as [ApplicationName]_Phase2_Inventory.xlsx and return it to [contact].

Plan for three to five hours. Grey cells are pre-filled; please do not edit them, and do not change columns or sheets.

Questions to [contact]. Thank you.

Build well,

Adam

---

## Email 4: Phase 3 tasking

**Subject:** UX Standardization Phase 3: Patterns Inventory due [date]

Team,

Phase 3 is the final inventory. The attached workbook, Phase3_Patterns_Inventory_Template.xlsx, is the mechanism. One copy per application, same application names as before, due [date].

**What Phase 3 captures**

Phases 1 and 2 recorded what the applications are made of. Phase 3 records how they behave, which is what users notice most. Six sheets:

- States and Feedback: 32 canonical situations, including ten loading states and seven empty states, plus error, confirmation, and session states. For each: what the user sees, the exact copy, delay and timeout behavior, whether interaction is blocked, whether a recovery action is offered, and whether assistive technology is told.
- Loaders and Spinners: one row per distinct loader asset in the codebase. Spinners, skeletons, progress bars, shimmers, branded animations, including the legacy ones.
- Motion and Animation: one row per transition, with duration, easing, and whether the reduced motion preference is honored.
- Content and Microcopy: 27 content types with verbatim examples and case style.
- Form Patterns: 20 form behaviors, from validation timing to unsaved-changes handling.
- Data Viz Conventions: palettes, formatting, and chart states.

**A note on the states sheet**

This is the core of Phase 3 and it requires you to use the application rather than read it. Throttle the network in dev tools to see loading states, go offline to see network errors, search for nonsense to see empty results. "Nothing shown" is a valid and important answer: a screen that silently freezes during a load is exactly what we need to know about. Give every loader a short identifier (L-1, L-2) on the Loaders sheet so the states sheet can say which one appears where.

**How to complete it**

1. Read the Instructions sheet.
2. Start with Loaders and Spinners, then States and Feedback, then the rest.
3. Paste copy verbatim. Do not clean it up; the inconsistencies are the point.
4. Answer No on the Charting library row and skip the rest of Data Viz if the application has no charts.
5. Save as [ApplicationName]_Phase3_Inventory.xlsx and return it to [contact].

Plan for four to six hours. Same rules as before on columns, sheets, and grey cells.

After Phase 3 closes we will consolidate all three datasets and share a suite-wide readout, including where each application sits relative to Trenchcoat and a proposed convergence sequence. You will see the results of your work.

Questions to [contact]. Thank you for seeing this through.

Build well,

Adam
