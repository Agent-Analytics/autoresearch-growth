# Autoresearch Growth Loop

You are running an instruction-driven growth loop. Your job is to produce two high-quality variants that can be tested against the current control for the project described in `brief.md`.

Do not change product code while running the loop. Produce reviewable copy artifacts first.

## Setup

1. Read `README.md`.
2. Read `brief.md` fully.
3. Treat `brief.md` as the source of truth for:
   - project
   - audience
   - surface
   - current control
   - metrics
   - analytics commands
   - drift constraints
4. If `results.tsv` does not exist, create it with the header:

```tsv
round	candidate_a	candidate_b	candidate_ab	winner	borda_a	borda_b	borda_ab	status	rationale
```

5. If `final_variants.md` already exists, overwrite it only at the end of a completed loop.

## Data Brief

Before generating copy, refresh the data described in `brief.md`.

Use the project's analytics commands exactly as written in the brief. The data source can be a CLI, API, SQL query, exported report, analytics dashboard export, or manually supplied data.

Rules:

- Never invent numbers.
- If a command fails because of auth, missing scope, sparse data, or product limitations, record the failure.
- Treat missing data as missing data, not zero data.
- Separate primary outcome data from proxy and guardrail data.

## Scope

During the loop, edit only:

- `results.tsv`
- `final_variants.md`
- optional scratch notes if needed

Do not edit the live site, app, product code, or experiment setup until the variants have been reviewed.

## Product Truth

Every candidate must preserve the product truth from `brief.md`.

Penalize:

- generic category language
- copy a competitor could say word for word
- unsupported claims
- drift away from the real product value
- clickbait that weakens the primary conversion event
- changes that ignore the current control's strengths

Reward:

- specificity
- clear audience fit
- concrete user outcome
- stronger primary-event intent
- honest use of the available data
- language that only this product could credibly say

## Metrics

Use the metric config in `brief.md`.

Typical shape:

```text
primary_event: signup
proxy_events: cta_click
guardrails: bounce rate, scroll depth, time on page, errors, performance
```

The proxy can help pick candidates faster. The primary event decides whether a shipped experiment wins.

## Loop

Run at least 5 rounds unless `brief.md` specifies a different count.

Each round has four phases.

### 1. Candidate A

For round 1, candidate A is your first new hypothesis based on the brief, control, and data.

For later rounds, candidate A is the previous round winner.

Candidate A should include the editable parts named in the brief, usually:

- headline
- subheadline
- primary CTA label
- supporting bullets or proof
- short hypothesis

### 2. Critique

Critique candidate A harshly.

Focus on:

- what is generic
- what a competitor could say
- where the value is unclear
- where the copy drifts from the product truth
- whether primary-event intent is strong enough
- whether the current control is clearer

Do not protect the candidate. The critique exists to improve the loop.

### 3. Candidate B And Synthesis AB

Write candidate B from the critique as if starting fresh. It may use the brief and critique, but it should not be a mild rewrite of A.

Then write candidate AB by combining the strongest parts of A and B. Do not average them into bland middle copy.

### 4. Blind Borda Ranking

Blind-rank A, B, and AB. To simulate blind judging in this simple repo, anonymize them as `option_1`, `option_2`, and `option_3` in a different order each round before scoring.

Score:

- first place: 2 points
- second place: 1 point
- third place: 0 points

Use the rubric in `brief.md`. If the brief does not define one, use:

- specificity to the product
- clarity for the target audience
- likely primary-event intent
- preservation of product truth
- low competitor-sayable language
- fit with available analytics data

Append one row to `results.tsv` after each round. Keep the rationale short and TSV-safe.

Winner becomes candidate A for the next round.

## Final Selection

After the final round, choose the two strongest distinct candidates. They should not be tiny wording variations of each other.

Write `final_variants.md` with:

- candidate_1
- candidate_2
- exact changed copy
- rationale
- risks
- recommended experiment name
- experiment shape
- data limitations

End with a clear note that the experiment has not been wired yet.
