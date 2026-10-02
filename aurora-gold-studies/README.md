# Aurora Gold Membership — Studies 1–3

Experimental stimulus materials for a research project examining how **loyalty-program membership acquisition** and **the type of service failure** jointly shape customer responses, using the fictional **Aurora Hotels' Gold Membership Program**.

This repository consolidates three related studies into a single project. Each study lives in its own folder and is self-contained — a browser-based, multi-stage scenario with **no build step and no external dependencies**.

## Repository Structure

```
.
├── index.html          # Root entry page linking to all three studies
├── README.md           # This file
├── GITHUB_UPLOAD_GUIDE.md   # Step-by-step guide for uploading to GitHub + GitHub Pages
├── Study1/             # Full 2 × 2 between-subjects design (Credamo)
│   ├── index.html      # Scenario index (four conditions)
│   ├── paid_monetary.html        # Paid × Monetary
│   ├── paid_recognition.html     # Paid × Recognition
│   ├── earned_monetary.html      # Earned × Monetary
│   ├── earned_recognition.html   # Earned × Recognition
│   └── README.md
├── Study2/             # Illustrative stimulus paths (Credamo)
│   ├── index.html      # Scenario index (two conditions)
│   ├── study2_paid_monetary.html        # Paid × Monetary
│   ├── study2_earned_recognition.html   # Earned × Recognition
│   ├── README.md
│   └── README.txt
└── Study3/             # Obligation-focus sessions (Prolific)
    ├── index.html      # Session chooser (two sessions)
    ├── study3_provider_paid_monetary.html   # Provider · Paid · Monetary
    ├── study3_self_earned_recognition.html  # Self · Earned · Recognition
    ├── README.md
    └── README.txt
```

## Study Summaries

| Study | Design | Manipulated factors | Platform |
|---|---|---|---|
| **Study 1** | Full 2 × 2, four complete cells | Membership acquisition (Paid vs. Earned) × Service failure type (Monetary vs. Recognition) | Credamo |
| **Study 2** | Two illustrative stimulus paths | Same two factors, shown as two end-to-end examples | Credamo |
| **Study 3** | Two complete sessions, four stages each | Obligation focus (Provider vs. Self) + Acquisition × Failure | Prolific |

> **Note:** These pages are **complete stimulus paths only** and contain **no questionnaire items**. The questionnaires are administered on the external survey platforms (Credamo / Prolific).

## Viewing the Pages

Open `index.html` in any browser to navigate to all three studies. Each study's own `index.html` links to its condition/session pages.

- **Query forwarding:** the root `index.html` and the Study 1 / Study 3 index pages forward any query string from their own URL to the page you select, so parameters such as a `return` URL or `PROLIFIC_PID` can be passed from a single entry link down to the scenario pages.
- **Return to survey:** scenario pages read an optional `return` query parameter and redirect participants back to the survey (Credamo or Prolific) when they finish.

### GitHub Pages (recommended for online hosting)

After uploading to GitHub and enabling **GitHub Pages** on the repository, the site is accessible at:

```
https://<your-username>.github.io/<repository-name>/
```

and each study at:

```
.../Study1/index.html
.../Study2/index.html
.../Study3/index.html
```

Full setup instructions are in [`GITHUB_UPLOAD_GUIDE.md`](GITHUB_UPLOAD_GUIDE.md).

## Disclaimer

These materials are experimental stimuli for academic research. They do not represent any real hotel, loyalty program, or commercial offer, and they are provided as-is without warranty.

## License

For research and educational use. Please contact the authors for any commercial use or reproduction.
