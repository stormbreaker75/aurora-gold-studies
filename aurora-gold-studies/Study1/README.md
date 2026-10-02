# Study 1 — Experimental Scenario Stimuli (Aurora Gold Membership)

Experimental stimulus materials for **Study 1** of a research project examining how **loyalty-program membership acquisition** and **the type of service failure** jointly shape customer responses.

This repository contains self-contained, browser-based experimental scenarios built for the **Credamo** online survey platform. Participants complete the questionnaire externally; the stimulus pages present a realistic membership scenario and return participants to the survey when finished.

## Overview

Study 1 uses a fictional hospitality context — **Aurora Hotels' Gold Membership Program** — to test customer reactions to service failures in loyalty programs. Two between-subjects factors are manipulated in a full **2 × 2 between-subjects design**:

| Factor | Levels |
|---|---|
| **Membership acquisition** | Paid (annual membership fee) vs. Earned (accumulated qualifying stays) |
| **Service failure type** | Monetary failure (15% discount not applied) vs. Recognition failure (priority check-in unavailable) |

All four randomized cells are provided as complete, ready-to-field stimulus paths:

| Condition | File | Acquisition | Failure |
|---|---|---|---|
| A | `paid_monetary.html` | Paid | Monetary (discount not applied) |
| B | `paid_recognition.html` | Paid | Recognition (priority check-in unavailable) |
| C | `earned_monetary.html` | Earned | Monetary (discount not applied) |
| D | `earned_recognition.html` | Earned | Recognition (priority check-in unavailable) |

Each stimulus page walks participants through two stages: (1) reading the membership scenario and a Gold membership card, and (2) entering a Gold Member Service Portal where the corresponding service failure is described. On completion, the participant is prompted to return to the Credamo questionnaire.

## File Structure

```
.
├── index.html                 # Scenario index page (entry point)
├── paid_monetary.html         # Condition A: Paid × Monetary failure
├── paid_recognition.html      # Condition B: Paid × Recognition failure
├── earned_monetary.html       # Condition C: Earned × Monetary failure
├── earned_recognition.html    # Condition D: Earned × Recognition failure
└── README.md                  # This file
```

## Getting Started

The scenarios are static HTML/CSS/JS files with **no build step or external dependencies**. To preview them locally:

1. Clone or download this repository.
2. Open `index.html` in any modern browser.
3. Click any scenario card to enter a stimulus path.

### Passing query parameters through the index

`index.html` forwards any query string in its own URL to every scenario link automatically. For example, opening

```
index.html?return=https://www.credamo.com/...
```

appends `?return=...` to all four condition pages, so whatever parameter you pass to the index is carried through to whichever scenario a participant enters. This is convenient for embedding a single survey link.

### Redirecting back to the survey

Each stimulus page reads the optional `return` query parameter (e.g. `?return=https://www.credamo.com/...`). When provided, the page redirects the participant back to the survey shortly after they complete the scenario. You may link a condition page directly:

```
paid_monetary.html?return=<your-credamo-questionnaire-url>
```

## Fielding the Experiment in Credamo

To field the full 2 × 2 design, randomize participants across the four condition URLs in Credamo, each with the appropriate `return` parameter pointing back to the corresponding survey branch:

| Condition | Stimulus URL |
|---|---|
| A | `paid_monetary.html?return=<survey-url>` |
| B | `paid_recognition.html?return=<survey-url>` |
| C | `earned_monetary.html?return=<survey-url>` |
| D | `earned_recognition.html?return=<survey-url>` |

## Customization

The pages are plain HTML with inline CSS. To rebrand or adjust the materials:

- **Hotel / program name:** edit the `AURORA HOTELS` brand text and the Gold Membership card copy.
- **Failure descriptions:** modify the text inside the `<div class="status">` and the adjacent `<p>` block in the portal section.
- **Styling:** colors and layout are controlled by the CSS custom properties in the `:root` block (e.g. `--navy`, `--gold`).

## Disclaimer

These materials are experimental stimuli for academic research. They do not represent any real hotel, loyalty program, or commercial offer, and they are provided as-is without warranty.

## License

For research and educational use. Please contact the authors for any commercial use or reproduction.
