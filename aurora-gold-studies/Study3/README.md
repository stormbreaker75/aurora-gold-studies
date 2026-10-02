# Study 3 — Experimental Stimuli (Aurora Gold Membership)

Experimental stimulus materials for **Study 3** of a research project examining how **loyalty-program membership acquisition** and **the type of service failure** shape customer responses.

This repository contains self-contained, browser-based experimental sessions built for the **Prolific** online participant platform. Each stimulus page presents a multi-stage scenario and returns the participant to the survey when finished.

## Overview

Study 3 uses a fictional hospitality context — **Aurora Hotels' Gold Membership Program** — and extends the prior studies with an **obligation-focus manipulation** delivered through an initial writing task. Each session runs through four stages:

1. **Obligation-focus writing task** — primes either provider-focused or self-focused expectations in an ongoing service relationship.
2. **Neutral filler task** — a brief, unrelated figure-comparison task.
3. **Gold membership acquisition** — membership is either **paid** (annual membership fee) or **earned** (accumulated qualifying stays).
4. **Service failure** — a **monetary** failure (15% discount not applied) or a **recognition** failure (priority check-in unavailable).

### Complete Stimulus Paths

Two complete, end-to-end stimulus paths are provided:

| Session | Path | Stage 1: Obligation focus | Stage 3: Acquisition | Stage 4: Failure |
|---|---|---|---|---|
| Session 1 | `study3_provider_paid_monetary.html` | Provider-focused | Paid | Monetary (discount not applied) |
| Session 2 | `study3_self_earned_recognition.html` | Self-focused | Earned | Recognition (priority check-in unavailable) |

> **Note:** These pages include **no questionnaire items** — they are complete stimulus paths only.

## File Structure

```
.
├── index.html                              # Session chooser (entry point)
├── study3_provider_paid_monetary.html      # Session 1: Provider · Paid · Monetary
├── study3_self_earned_recognition.html     # Session 2: Self · Earned · Recognition
└── README.md                               # This file
```

## Getting Started

The sessions are static HTML/CSS/JS files with **no build step or external dependencies**. To preview them locally:

1. Clone or download this repository.
2. Open `index.html` in any modern browser.
3. Choose a session to begin.

## Prolific Integration

The pages are built to work with **Prolific**. They accept the standard Prolific URL parameters — `PROLIFIC_PID`, `STUDY_ID`, and `SESSION_ID` — which are read from the URL and forwarded between pages.

### Query parameter forwarding

The session-chooser (`index.html`) forwards the full query string from its own URL to whichever session the participant selects. For example:

```
index.html?PROLIFIC_PID=xxx&STUDY_ID=yyy&SESSION_ID=zzz
```

appends those parameters to the target session page automatically, and the chosen session's `Continue` redirect carries them on to the survey.

### Redirecting back to the survey

Each stimulus page reads the optional `return` query parameter:

```
?return=YOUR_RETURN_URL
```

After the participant clicks the final `Continue` button, the page redirects to the return URL (after a short delay). If the participant's `PROLIFIC_PID`, `STUDY_ID`, or `SESSION_ID` are present and the return URL is a valid URL, they are appended to the return URL (when not already present) so the survey receives the participant identifiers.

## Fielding the Experiment

To field a session, point participants at the corresponding session page (or the index chooser) with the appropriate Prolific parameters and a `return` URL:

| Session | Stimulus URL |
|---|---|
| 1 | `study3_provider_paid_monetary.html?PROLIFIC_PID=<pid>&STUDY_ID=<sid>&SESSION_ID=<ssid>&return=<survey-url>` |
| 2 | `study3_self_earned_recognition.html?PROLIFIC_PID=<pid>&STUDY_ID=<sid>&SESSION_ID=<ssid>&return=<survey-url>` |

## Customization

The pages are plain HTML with inline CSS. To rebrand or adjust the materials:

- **Hotel / program name:** edit the `AURORA HOTELS` brand text and the Gold Membership card copy.
- **Obligation-focus task:** modify the prompt and placeholder text in the first stage (e.g. "A service provider should ____" vs. "As a customer, I should ____").
- **Failure descriptions:** modify the text inside the `<div class="status">` and the adjacent `<p>` block in the portal section.
- **Styling:** colors and layout are controlled by the CSS custom properties in the `:root` block (e.g. `--navy`, `--gold`).

## Disclaimer

These materials are experimental stimuli for academic research. They do not represent any real hotel, loyalty program, or commercial offer, and they are provided as-is without warranty.

## License

For research and educational use. Please contact the authors for any commercial use or reproduction.
