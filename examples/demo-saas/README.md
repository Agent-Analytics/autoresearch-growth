# Demo SaaS: ChangelogPilot

ChangelogPilot is a fictional product used to make the autoresearch loop runnable without private data.

It turns merged pull requests, issue labels, and shipped feature context into customer-facing changelog drafts that a small SaaS team can review before publishing.

![ChangelogPilot generated homepage section](assets/changelogpilot-homepage-section.jpg)

## What The Fake Data Represents

The saved data under `data/2026-04-15/` is a fake 7-day Agent Analytics snapshot for the ChangelogPilot homepage.

- Primary metric: `trial_started`
- Proxy metric: `hero_cta_click`
- Surface: marketing landing-page hero
- Main problem: high homepage bounce and shallow scroll depth
- Experiment shape: `control,candidate_1,candidate_2`

The demo gives an agent enough context to practice the loop:

- product truth in `brief.md`
- saved analytics output in `data/2026-04-15/`
- empty output templates in `results.tsv` and `final_variants.md`
- one completed example run in `runs/2026-04-15-e2e/`

## Completed Example Run

Read this first if you want to see the expected output shape:

- [`runs/2026-04-15-e2e/README.md`](runs/2026-04-15-e2e/README.md) - run report
- [`runs/2026-04-15-e2e/results.tsv`](runs/2026-04-15-e2e/results.tsv) - five judged rounds
- [`runs/2026-04-15-e2e/final_variants.md`](runs/2026-04-15-e2e/final_variants.md) - two review-ready winners

The completed run shows the important pattern: the LLM loop produces candidate variants, but the next loop should start from measured experiment evidence.

## How To Use It

From the repo root:

```bash
cp examples/demo-saas/brief.md brief.md
cp examples/demo-saas/results.tsv results.tsv
cp examples/demo-saas/final_variants.md final_variants.md
cp -R examples/demo-saas/data data
```

Then ask your coding agent:

```text
Read program.md and brief.md. Use data/2026-04-15/ as the latest 7-day snapshot. Run 5 rounds. Append one row per round to results.tsv and write final_variants.md with two distinct variants.
```

Replace this demo with your own project before using the output for a real experiment.
