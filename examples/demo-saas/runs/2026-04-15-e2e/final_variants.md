# Final Variants For Human Review

Date: 2026-04-15

Target experiment:

```text
experiment: autoresearch_home_20260415
variants: control,candidate_1,candidate_2
goal: trial_started
proxy: hero_cta_click
```

The experiment has not been wired.

## Control

Headline:

```text
AI changelogs for fast product teams.
```

Subheadline:

```text
ChangelogPilot turns your shipped work into polished release notes so your team can keep customers in the loop.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Connect GitHub and Linear
- Review AI-drafted entries
- Publish when ready
```

## Candidate 1

Direction: direct transformation.

Headline:

```text
Turn merged PRs into customer updates.
```

Subheadline:

```text
ChangelogPilot drafts customer-facing changelog entries from GitHub pull requests, Linear issues, and shipped feature context so weekly SaaS teams can review and publish faster.
```

Primary CTA:

```text
Draft your first changelog
```

Supporting copy:

```text
- Connect GitHub and Linear
- Use the context your team already wrote
- Review every entry before publishing
```

Hypothesis:

This should beat the control because it replaces generic "AI changelogs" with a specific transformation: merged PRs become customer updates. The demo data shows visitors are deciding quickly, so the headline must explain the value before they scroll.

Risks:

- It may underplay the weekly publishing cadence.
- "Merged PRs" is precise for product engineers but may be slightly less accessible to non-technical founders.
- The CTA is more action-specific than "Start free trial," which could either improve intent or reduce broad clicks.

## Candidate 2

Direction: safety and review.

Headline:

```text
Review-ready changelogs from the PRs you already merged.
```

Subheadline:

```text
ChangelogPilot turns GitHub pull requests, Linear issues, and shipped feature context into customer-facing drafts your team can review and publish every week.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Connect GitHub and Linear
- Use context engineers already wrote
- Publish only after review
```

Hypothesis:

This should appeal to teams worried about accuracy. It keeps the review-before-publish guardrail explicit while still making the source material specific. It may produce fewer curiosity clicks but better `trial_started` intent.

Risks:

- The headline is longer than candidate 1 and may be weaker on mobile.
- "Review-ready" is useful but slightly more common than the direct PR-to-customer-update framing.
- It may sound more workflow-oriented than pain-oriented.

## Why These Two

The loop produced two meaningfully different bets:

- Candidate 1 is sharper and transformation-led.
- Candidate 2 is safer and trust-led.

Both avoid the demo's main drift risks:

- They do not sound like generic AI writing software.
- They do not imply automatic publishing.
- They stay focused on customer-facing changelogs rather than internal sprint summaries.
- They use the actual source material: GitHub PRs, Linear issues, labels, and shipped feature context.

## Data Notes

The fake demo snapshot suggests the first hero decision is the largest leak:

- 1,410 sessions.
- 71% homepage bounce.
- Median time on page: 22s.
- Only 18% of sessions reach 75% scroll depth.
- `page_view` to `hero_cta_click`: 11.2%.
- `hero_cta_click` to `trial_started`: 24.6%.
- Overall `page_view` to `trial_started`: 2.7%.

Interpretation:

The copy needs to make the job clear above the fold. The proxy is `hero_cta_click`, but the primary decision signal should remain `trial_started`.

## Recommended Experiment Shape

```text
experiment: autoresearch_home_20260415
variants: control,candidate_1,candidate_2
goal: trial_started
proxy: hero_cta_click
guardrails: bounce rate, scroll depth, time on page, page errors
```

## Human Judge Notes

Questions to judge:

- Does candidate 1 explain the value fast enough?
- Does candidate 2 preserve enough urgency despite being safer?
- Is "merged PRs" too narrow for founders, or exactly specific enough for the target audience?
- Which variant is more likely to start a qualified trial, not just earn a click?
