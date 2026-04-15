# Demo Autoresearch Scratch Notes

Run date: 2026-04-15

Input data:

- `brief.md`
- `data/2026-04-15/insights.txt`
- `data/2026-04-15/pages.txt`
- `data/2026-04-15/funnel.txt`
- `data/2026-04-15/hero_cta_click-events.txt`
- `data/2026-04-15/trial_started-events.txt`
- `data/2026-04-15/experiments.txt`

## Data Read

The fake demo data points to one main problem: the homepage hero is not earning enough qualified first clicks.

- 1,410 sessions.
- 71% homepage bounce.
- Median time on page: 22s.
- 75% scroll depth reached by only 18% of sessions.
- `page_view` to `hero_cta_click`: 11.2%.
- `hero_cta_click` to `trial_started`: 24.6%.
- `page_view` to `trial_started`: 2.7%.

Interpretation:

- The largest drop is before the hero CTA.
- The copy must work above the fold.
- It should make the weekly release-note pain obvious fast.
- It should avoid generic "AI writing" language.
- It must keep review-before-publish safety clear.

## Round 1

### Candidate A

Headline:

```text
Turn shipped PRs into customer-ready changelogs.
```

Subheadline:

```text
ChangelogPilot drafts release notes from GitHub pull requests and Linear issues so small SaaS teams can publish accurate updates every week.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Connect GitHub and Linear
- Review every drafted entry
- Publish customer-facing updates when ready
```

Critique:

- Strong product specificity.
- "Customer-ready" is good, but the weekly pain could be sharper.
- It does not directly attack the high bounce problem with urgency.
- The CTA is familiar but not tied to the workflow.

### Candidate B

Headline:

```text
Release notes from the work you already shipped.
```

Subheadline:

```text
ChangelogPilot turns merged PRs, issue labels, and feature context into draft changelog entries your team can review before customers see them.
```

Primary CTA:

```text
Draft your first changelog
```

Supporting copy:

```text
- Pull context from GitHub and Linear
- Keep review before publish
- Stop rewriting shipped work from memory
```

### Candidate AB

Headline:

```text
Weekly changelogs from the PRs you already shipped.
```

Subheadline:

```text
ChangelogPilot turns merged pull requests, Linear issues, and shipped feature context into customer-facing changelog drafts your team reviews before publishing.
```

Primary CTA:

```text
Start your first draft
```

Supporting copy:

```text
- Connect GitHub and Linear
- Review AI-drafted entries
- Publish when the update is ready
```

Blind ranking:

- Judge 1: AB, A, B
- Judge 2: AB, B, A
- Judge 3: A, AB, B
- Winner: AB

## Round 2

### Candidate A

Round 1 AB.

Critique:

- "Weekly changelogs" fits the audience well.
- "AI-drafted" in supporting copy is still a little generic.
- The headline is clear but not emotionally sharp.
- The largest data problem is bounce, so the first line should punch harder.

### Candidate B

Headline:

```text
Stop shipping features customers never hear about.
```

Subheadline:

```text
ChangelogPilot turns merged PRs and Linear issues into customer-facing release-note drafts, so weekly product updates do not wait on a blank page.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Pull context from shipped work
- Review every entry before publishing
- Keep customers in the loop each week
```

### Candidate AB

Headline:

```text
Ship every week without late release notes.
```

Subheadline:

```text
ChangelogPilot turns merged PRs, Linear issues, and shipped feature context into customer-ready changelog drafts your team reviews before publishing.
```

Primary CTA:

```text
Draft your next changelog
```

Supporting copy:

```text
- Connect GitHub and Linear
- Turn shipped work into plain English
- Review and publish when ready
```

Blind ranking:

- Judge 1: AB, B, A
- Judge 2: B, AB, A
- Judge 3: AB, A, B
- Winner: AB

## Round 3

### Candidate A

Round 2 AB.

Critique:

- "Late release notes" is clear pain.
- The subheadline is accurate but still sounds a little polished and generic.
- It can be more specific about GitHub/Linear context.
- It should make "customer-facing" unavoidable.

### Candidate B

Headline:

```text
Customer-ready changelogs from your GitHub and Linear work.
```

Subheadline:

```text
ChangelogPilot drafts entries from merged pull requests, issue labels, and shipped features so small SaaS teams can review and publish updates every week.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Use the context engineers already wrote
- Review every draft before publishing
- Keep customers current without chasing notes
```

### Candidate AB

Headline:

```text
Draft changelogs from the PR context you already have.
```

Subheadline:

```text
ChangelogPilot turns GitHub pull requests and Linear issues into customer-facing release-note drafts for weekly SaaS teams.
```

Primary CTA:

```text
Draft your first update
```

Supporting copy:

```text
- Connect GitHub and Linear
- Review the generated entries
- Publish when ready
```

Blind ranking:

- Judge 1: B, AB, A
- Judge 2: B, A, AB
- Judge 3: B, AB, A
- Winner: B

## Round 4

### Candidate A

Round 3 B.

Critique:

- This is very clear and safe.
- It may be too long for a fast-bounce hero.
- "Customer-ready" is useful but common.
- The strongest differentiator is review-ready customer-facing changelog drafts from merged work.

### Candidate B

Headline:

```text
Review-ready release notes from merged PRs.
```

Subheadline:

```text
ChangelogPilot uses GitHub and Linear context to draft customer-facing updates for small SaaS teams that ship every week.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Pull from PRs, issues, and labels
- Keep review before publish
- Turn shipped work into customer updates
```

### Candidate AB

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
Draft your first changelog
```

Supporting copy:

```text
- Connect GitHub and Linear
- Use context engineers already wrote
- Publish only after review
```

Blind ranking:

- Judge 1: AB, A, B
- Judge 2: AB, B, A
- Judge 3: A, AB, B
- Winner: AB

## Round 5

### Candidate A

Round 4 AB.

Critique:

- Strong but still a bit long.
- "Review-ready" is safe but less direct than the transformation from merged PR to customer update.
- The final version should keep the customer-facing contrast in the headline or first subheadline.

### Candidate B

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

### Candidate AB

Headline:

```text
Customer updates from the PRs you already merged.
```

Subheadline:

```text
ChangelogPilot turns shipped work into reviewable changelog drafts for small SaaS teams that need to publish every week.
```

Primary CTA:

```text
Start free trial
```

Supporting copy:

```text
- Pull from GitHub and Linear
- Review every drafted entry
- Publish customer-facing updates when ready
```

Blind ranking:

- Judge 1: B, AB, A
- Judge 2: B, A, AB
- Judge 3: B, A, AB
- Winner: B

## Final Choice

Two variants should test distinct hypotheses:

- Candidate 1 tests a direct transformation message: "merged PRs" to "customer updates."
- Candidate 2 tests a safety and review message: "review-ready changelogs."

Both preserve the product truth and avoid drifting into generic AI writing software.
