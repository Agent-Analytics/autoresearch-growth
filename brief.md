# Growth Loop Brief

Copy this template into a project-specific brief before running the loop.

## Target

- Project:
- Surface:
- Public URL:
- Local source file or copy source:
- Primary metric:
- Proxy metric:
- Guardrail metrics:
- Recommended experiment name:
- Variant shape:

Example variant shape:

```text
variants: control,candidate_1,candidate_2
goal: <primary_event>
proxy: <proxy_event>
```

## Product Truth

Describe what the product is, who it serves, and what must remain true in every candidate.

Include:

- core promise
- target audience
- strongest differentiator
- language the product should own
- claims the product can support
- claims the product should not make

## Audience

Primary audience:

-

Pain:

-

Desired action:

-

## Current Control

Paste the current copy that candidates must beat.

Headline:

```text

```

Subheadline:

```text

```

Primary CTA:

```text

```

Supporting copy:

```text

```

## Analytics Commands Or Data

List the commands, API calls, reports, SQL queries, exports, or pasted data the agent should use before generating variants.

Example command placeholders:

```bash
<analytics-command> summary --project <project> --period 7d
<analytics-command> pages --project <project> --period 7d
<analytics-command> events --project <project> --event <proxy_event> --period 7d
<analytics-command> events --project <project> --event <primary_event> --period 7d
<analytics-command> count --project <project> --event <primary_event> --period 7d
<analytics-command> count --project <project> --event <proxy_event> --period 7d
```

Optional, if available:

```bash
<analytics-command> funnel --project <project> --steps "page_view,<proxy_event>,<primary_event>"
<analytics-command> experiments --project <project> list
```

## Live Data Snapshot

Fill this in after running the data commands.

Summary:

-

Primary event:

-

Proxy event:

-

Guardrails:

-

Data limitations:

-

## Drift Constraints

Candidates must not:

-

Candidates should:

-

## Judging Rubric

Rank candidates by:

- specificity to this product
- clarity for the target audience
- likely primary-event intent
- preservation of product truth
- low competitor-sayable language
- fit with available analytics data
