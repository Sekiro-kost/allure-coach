# allure-coach

*A running coach for COROS, inside Claude. ("Allure" is French for running pace.)*

A running coach that lives inside Claude. It reads your COROS data, sets your heart-rate zones, builds a plan for your race, sends it to your watch, and gives you a dashboard that keeps itself up to date. Move or lighten a session in the dashboard and the watch follows.

<p align="center">
  <img src="docs/img/02-calendrier.png" width="205" alt="Plan calendar, current week first">
  <img src="docs/img/03-fiche-seance.png" width="205" alt="Session card">
  <img src="docs/img/04-deplacer-une-seance.png" width="205" alt="Moving a session, with consistency advice">
  <img src="docs/img/09-mode-sombre.png" width="205" alt="Dark mode">
</p>

> **Independent project.** Not affiliated with COROS or Anthropic. **Not medical advice**: plans are suggestions to adapt to how you feel. If something hurts, stop and see a health professional.

*The dashboard itself is in French for now. The training logic and the instructions for Claude follow the user's language, and the visible texts can be translated on request.*

## Try it with nothing to install

Open [`exemples/demo.html`](exemples/demo.html) in your browser (download the file, then double-click it). It is the real dashboard with a fictional athlete preparing a 10 km. The demo connects to nothing: no data is read or written, and its dates shift to the current week on their own.

## What it does

- **Tailored plan**: zones from your threshold heart rate (Friel), Daniels paces, varied sessions, 80/20 polarisation, tapering.
- **Sends the plan to your watch** through the COROS connector, then syncs after every change.
- **Calendar**: tap a session for its card, long-press to move it or swap it with another one, with warnings when the sequence gets risky.
- **Readiness of the day**: green, orange or red from HRV, sleep, load, recovery and how you felt.
- **Lighten or strengthen** a session in one tap.
- **Session review**: planned versus done, with your notes and any pain you report.
- **Aerobic progress**: your pace at a fixed heart rate, with the effect of heat.
- **Optional**: weather for your runs (Open-Meteo), a strength programme, a race-day sheet with the start forecast, a season timeline, a Sunday review.

## What you need

- Claude with **Cowork** (paid plan).
- A **COROS** watch and the **Coros** connector (claude.ai → Settings → Connectors).
- Optional: the **Open-meteo** connector.

Tested in October 2026. These products change: if a tool name changes, adapt `kit/GUIDE-CLAUDE.md` or open an issue.

## Setup (5 minutes)

1. In Claude, create a project, for example "Running".
2. Add the two files from [`kit/`](kit) to the project files: `GUIDE-CLAUDE.md` and `coach-dashboard-template.html`.
3. Start a Cowork task in that project and write: **"Lance le kit coach course"** (the guide is in French, Claude answers in your language).
4. Answer the questions (race, date, goal, available days). Claude shows your zones, its diagnosis and the plan before sending anything to your watch.

Tips:
- If your watch already holds a plan from another app, remove it in the COROS app: Claude only edits plans it created.
- Always open the dashboard **from Claude**, not in a browser: that is what enables the watch sync.
- The first time, Claude asks you to allow access to COROS (and Open-Meteo) for the page.

## How it works

Everything specific to the athlete lives in **one object**, `COACH`, which Claude fills in and injects into the HTML template. The full schema is in [`kit/GUIDE-CLAUDE.md`](kit/GUIDE-CLAUDE.md), a filled example in [`exemples/exemple-coach.json`](exemples/exemple-coach.json).

## Privacy

- Your COROS data is read by Claude, in your account, through the connector. This kit sends nothing to any other server.
- The dashboard is a **private** artifact until you share it. Its data (moved sessions, notes, reviews) lives in the artifact's database, tied to your account. Don't share its link: it contains your plan, zones and runs.
- External requests from the page: Google Fonts at load time, Open-Meteo through the connector (coordinates rounded to about 1 km), and YouTube links in the strength tab, opened only when you click.
- When you post an issue or an example, remove your name, heart rates, location and dashboard link.

## Known limits

- Strength sessions stay in the dashboard: COROS only accepts running, cycling and trail through the connector.
- A plan imported from another app can't be edited from the dashboard.
- A plan starts within 14 days and lasts 4 to 16 weeks (connector rule); for a later goal, Claude creates the first part and extends it.
- Predictions and advice are estimates. Weekly adaptation depends on how regularly you sync.

## Contributing

Issues and pull requests are welcome: see [`CONTRIBUTING.md`](CONTRIBUTING.md). To rebuild the demo after changing the template: `python3 scripts/build-demo.py`.

## Support

If this kit helps your running, you can buy me a coffee. It is optional and does not entitle you to personal support.

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-YOUR--NAME-FFDD00?logo=buymeacoffee&logoColor=black)](https://www.buymeacoffee.com/YOUR-NAME)

## License

[MIT](LICENSE). Trademarks belong to their owners.
