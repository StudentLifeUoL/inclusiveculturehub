# Inclusive Culture Hub activities

Interactive activities embedded in the Inclusive Culture Rise 360 course. Each activity is a self-contained web page in its own folder, and all of them share one design system in `assets/`.

| Folder | Activity | What the learner does |
| --- | --- | --- |
| `/` (root `index.html`) | Visions of 2030 | Picks the challenges that matter where they live, rates their influence on five levers of change, writes a reflection with prompt cards, and checks in on how they feel. |
| `page1/` | The Inequality Ladder | Draws a fictional identity and lives four life stages. Some paths are closed to them, with the reason shown, while seven other people climb alongside. Ends with a comparison and a reflection on equity. |
| `page2/` | Diversity Impact Builder | Chooses five workplace practices and watches a 12-person team respond (innovation, retention, trust), then reads a culture report. |
| `page3/` | Reflecting on the UN SDGs | Chooses up to three SDGs and writes a postcard from 2030, then downloads it and emails it for feedback. |
| `page4/` | Cultivating Cultural Intelligence | Reads a virtual-team scenario, builds a Core and Flex model of their leadership, and writes a start / stop / measure plan. |
| `page5/` | My Action Plan | Captures a 3-2-1 of their learning, their core and flex, and three timed actions, then downloads a one-page plan. |
| `page6/` | Diversity, inclusion and belonging | Labels four illustrated party scenes as diversity, inclusion or belonging and gets feedback on each. |
| `page7/` | Equality and equity | Defines both terms in their own words, compares them with an interactive illustration, then explains the difference. |

## Embedding in Rise 360

Use a **Multimedia > Embed** block with iframe code, for example:

```html
<iframe src="https://studentlifeuol.github.io/inclusiveculturehub/page1/" width="100%" height="640" title="The Inequality Ladder"></iframe>
```

(The address assumes the repository is published with GitHub Pages from the `main` branch. Check the repository's Pages settings for the exact address.)

The activities are built to cope with however Rise sizes the frame:

- The Back / Continue bar sticks to the bottom of the frame, so navigation is never cut off, even in a short frame on a phone.
- Nothing is wider than the frame, so edges are never clipped, from 320px phones up to full-width blocks.
- Nothing relies on full-screen heights, pop-up dialogs (`alert`, `confirm`) or fixed overlays, which behave badly inside Rise.
- About 600 to 700px of height suits most activities on desktop. Longer steps scroll inside the frame.

If you move an activity into a Rise **code block** instead, it sends Rise's completion message (`{ type: "complete" }`) when the learner reaches the last step.

## Learners' work

Writing is saved in the learner's own browser only (local storage), so it survives a page refresh but never leaves their device. Each writing activity offers **Download** (a .txt file) and **Copy**. Equality and equity also picks up writing saved by its previous version.

## Changing the design

- `assets/ich.css` holds the colours, fonts, spacing and shared components. Change a token at the top (for example `--brand`) and every activity follows.
- `assets/ich.js` holds the shared behaviour: steps and progress, saving, download and copy, icons and the decorative "crowd" in the header.
- Each activity's own content and interactions live in its `index.html`. Text is plain HTML or a clearly labelled data list near the top of the script.
- Each activity sets its accent colour on `<body>` (`--accent`, `--accent-ink`, `--accent-tint`).

## Accessibility

The activities aim for WCAG 2.2 AA: keyboard operable, visible focus, labelled fields, status messages announced to screen readers, text contrast of at least 4.5:1, touch targets of at least 40px, and reduced motion respected. Body text uses Atkinson Hyperlegible Next, designed by the Braille Institute for readers with low vision.

## Credits

- Fonts: Bricolage Grotesque and Atkinson Hyperlegible Next, both under the SIL Open Font License (see `assets/fonts/`).
- Icons: a subset of [Lucide](https://lucide.dev) (ISC licence).
