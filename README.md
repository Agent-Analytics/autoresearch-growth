# autoresearch-growth

Autoresearch-style growth loops for positioning, landing-page copy, onboarding copy, and experiment candidates.

This is a fork of [karpathy/autoresearch](https://github.com/karpathy/autoresearch), adapted for growth work. The repo is intentionally Markdown-first: a coding agent reads `program.md`, fills in a project brief, runs several critique/revision/judging rounds, and outputs two variants that can be tested against the current control.

## The Loop

1. Define the surface, audience, control, and metric.
2. Pull the latest analytics data for that surface.
3. Generate a candidate.
4. Critique it for genericness, drift, and weak conversion intent.
5. Write a fresh alternative from the critique.
6. Synthesize the strongest parts.
7. Blind-rank the options with Borda scoring.
8. Repeat for several rounds.
9. Ship the two strongest distinct variants into an A/B test.
10. Feed experiment data into the next run.

## Files

- `program.md` - operating manual for the loop.
- `brief.md` - project brief template.
- `results.tsv` - append-only round log template.
- `final_variants.md` - final output template.

## Quick Start

1. Fill in `brief.md` with the project, surface, control copy, metrics, and data commands.
2. Start Claude Code, Codex, Cursor, or another coding agent in this repo.
3. Prompt:

```text
Read program.md and run the growth loop. Use brief.md as the source of truth. Produce final_variants.md with two variants for review.
```

## Try The Demo

The repo includes a fake SaaS example with sample analytics data:

```bash
cp examples/demo-saas/brief.md brief.md
cp examples/demo-saas/results.tsv results.tsv
cp examples/demo-saas/final_variants.md final_variants.md
```

Then run the quick-start prompt above. The demo is intentionally fake; replace it with your own product, control copy, events, and data commands before making real decisions.

## Good First Targets

- Landing-page hero copy.
- Pricing-page positioning.
- Signup/onboarding page copy.
- CTA labels and supporting proof.
- Docs or blog CTAs that lead to signup or activation.

## Metrics

Pick one primary event and use other signals as proxy or guardrails.

Examples:

- Primary: `signup`, proxy: `cta_click`.
- Primary: `checkout`, proxy: `pricing_cta_click`.
- Primary: `project_created`, proxy: `install_command_copied`.
- Primary: `activation_completed`, proxy: `onboarding_step_completed`.

The proxy helps move quickly. The primary event decides real winners.
