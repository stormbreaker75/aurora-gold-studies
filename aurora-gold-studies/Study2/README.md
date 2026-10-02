# Study 2 — Experimental Scenario Stimuli (Aurora Gold Membership)

Illustrative stimulus materials for **Study 2** of a research project examining how **loyalty-program membership acquisition** and **the type of service failure** jointly shape customer responses.

This repository contains self-contained, browser-based experimental scenarios built for the **Credamo** online survey platform. Participants complete the questionnaire externally; the stimulus pages present a realistic membership scenario and return participants to the survey when finished.

## Overview

Study 2 uses a fictional hospitality context — **Aurora Hotels' Gold Membership Program** — to test customer reactions to service failures in loyalty programs. Two between-subjects factors are manipulated:

| Factor | Levels |
|---|---|
| **Membership acquisition** | Paid (annual membership fee) vs. Earned (accumulated qualifying stays) |
| **Service failure type** | Monetary failure vs. Recognition failure |

The complete design is therefore a **2 × 2 between-subjects experiment** with four randomized cells:

- Paid × Monetary
- Paid × Recognition
- Earned × Monetary
- Earned × Recognition

> **Note:** The files in this repository are **complete illustrative stimulus paths only** and contain **no questionnaire items**. They demonstrate two of the four cells as working end-to-end examples (see below). If Study 2 is fielded as a full 2 × 2 experiment, formal data collection still requires all four randomized cells.

## Illustrative Stimulus Paths

Two complete stimulus paths are provided as runnable examples:

1. **Paid Membership → Monetary Failure** — Membership obtained by paying the annual fee; the promised Gold-member **15% discount** was **not applied** to the booking.
2. **Earned Membership → Recognition Failure** — Membership earned by accumulating qualifying stays; the promised Gold-member **priority check-in** service was **unavailable**.

Each path walks participants through two stages: (1) reading the membership scenario and a Gold membership card, and (2) entering a Gold Member Service Portal where the corresponding service failure is described. On completion, the participant is prompted to return to the Credamo questionnaire.

## File Structure

```
.
├── index.html                        # Scenario index page (entry point)
├── study2_paid_monetary.html         # Condition A: Paid + Monetary failure
├── study2_earned_recognition.html    # Condition B: Earned + Recognition failure
└── README.md                         # This file
```

## Getting Started

The scenarios are static HTML/CSS/JS files with **no build step or external dependencies**. To preview them locally:

1. Clone or download this repository.
2. Open `index.html` in any modern browser.
3. Click either scenario card to enter a stimulus path.

Each stimulus page reads an optional `return` query parameter (e.g. `?return=https://www.credamo.com/...`). When provided, the page redirects the participant back to the survey shortly after they complete the scenario.

### Optional: Redirecting back to the survey

To link participants back to a Credamo questionnaire, append the return URL to the stimulus page:

```
study2_paid_monetary.html?return=<your-credamo-questionnaire-url>
study2_earned_recognition.html?return=<your-credamo-questionnaire-url>
```

## Usage in the 2 × 2 Design

To field the full experiment, create the two additional cells by pairing the two membership-acquisition framings with the complementary failure type (e.g. **Paid × Recognition** and **Earned × Monetary**), following the same page structure as the examples provided here. Randomize participants across all four cells in Credamo and pass each participant's assigned condition URL (with the appropriate `return` parameter).

## Customization

The pages are plain HTML with inline CSS. To rebrand or adjust the materials:

- **Hotel / program name:** edit the `AURORA HOTELS` brand text and the Gold Membership card copy.
- **Failure descriptions:** modify the text inside the `<div class="status">` and the adjacent `<p>` block in the portal section.
- **Styling:** colors and layout are controlled by the CSS custom properties in the `:root` block (e.g. `--navy`, `--gold`).

## Disclaimer

These materials are experimental stimuli for academic research. They do not represent any real hotel, loyalty program, or commercial offer, and they are provided as-is without warranty.

## License

For research and educational use. Please contact the authors for any commercial use or reproduction.
