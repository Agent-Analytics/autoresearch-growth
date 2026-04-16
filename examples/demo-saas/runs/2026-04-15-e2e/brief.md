# Growth Loop Brief

This is fake demo data for a fictional product. Replace it before running a real loop.

## Target

- Project: ChangelogPilot
- Surface: marketing landing-page hero
- Public URL: `https://example.invalid/`
- Local source file or copy source: `src/pages/home.tsx`
- Primary metric: `trial_started`
- Proxy metric: `hero_cta_click`
- Guardrail metrics: bounce rate, scroll depth, time on page, page errors
- Recommended experiment name: `autoresearch_home_20260415`
- Variant shape:

```text
variants: control,candidate_1,candidate_2
goal: trial_started
proxy: hero_cta_click
```

## Product Truth

ChangelogPilot turns merged pull requests, issue labels, and shipped features into draft changelog entries for small product teams.

The product helps founders and product engineers keep customers informed without writing every release note from scratch.

Candidates must preserve:

- ChangelogPilot is about customer-facing changelogs, not internal sprint reports.
- The value is saving release-writing time while staying accurate.
- The audience is small product teams shipping weekly.
- The product drafts changelog entries from existing engineering work.

Candidates must not claim:

- fully automatic publishing without review
- enterprise release governance
- code generation
- analytics or user tracking

## Audience

Primary audience:

- founders and product engineers at small SaaS teams that ship every week

Pain:

- release notes are always delayed
- engineers already wrote useful context in PRs, issues, and commits
- customers miss product improvements because no one turns shipped work into plain English

Desired action:

- start a free trial

## Current Control

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

## Analytics Commands Or Data

This demo uses fake saved Agent Analytics CLI output in `examples/demo-saas/data/2026-04-15/`.

Equivalent live commands for a real project would look like:

```bash
# Run once if this machine or agent runtime is not logged in.
npx @agent-analytics/cli@0.5.14 login

PROJECT_SLUG=changelogpilot
PRIMARY_EVENT=trial_started
PROXY_EVENT=hero_cta_click
RUN_DATE=2026-04-15

mkdir -p "data/$RUN_DATE"

run_snapshot_command() {
  output_file="$1"
  shift
  set +e
  "$@" > "$output_file" 2>&1
  command_status=$?
  set -e
  perl -i -pe 's/\e\[[0-9;]*m//g' "$output_file"
  if [ "$command_status" -ne 0 ]; then
    printf '\ncommand_exit_code: %s\n' "$command_status" >> "$output_file"
  fi
}

run_snapshot_command "data/$RUN_DATE/insights.txt" npx @agent-analytics/cli@0.5.14 insights "$PROJECT_SLUG" --period 7d
run_snapshot_command "data/$RUN_DATE/pages.txt" npx @agent-analytics/cli@0.5.14 pages "$PROJECT_SLUG" --since 7d
run_snapshot_command "data/$RUN_DATE/funnel.txt" npx @agent-analytics/cli@0.5.14 funnel "$PROJECT_SLUG" --steps "page_view,$PROXY_EVENT,$PRIMARY_EVENT" --since 7d
run_snapshot_command "data/$RUN_DATE/${PROXY_EVENT}-events.txt" npx @agent-analytics/cli@0.5.14 events "$PROJECT_SLUG" --event "$PROXY_EVENT" --days 7 --limit 50
run_snapshot_command "data/$RUN_DATE/${PRIMARY_EVENT}-events.txt" npx @agent-analytics/cli@0.5.14 events "$PROJECT_SLUG" --event "$PRIMARY_EVENT" --days 7 --limit 50
run_snapshot_command "data/$RUN_DATE/experiments.txt" npx @agent-analytics/cli@0.5.14 experiments list "$PROJECT_SLUG"
```

## Live Data Snapshot

Summary:

- 7-day page views: 4,820
- 7-day unique visitors: 1,130
- 7-day sessions: 1,410
- bounce rate: 71%
- median time on page: 22s
- 75% scroll depth: 18% of sessions

Primary event:

- `trial_started`: 31 events
- trial conversion from sessions: 2.2%

Proxy event:

- `hero_cta_click`: 126 events
- hero CTA click-through from sessions: 8.9%

Guardrails:

- page error rate: 0.2%
- median page load: 1.8s
- mobile bounce rate: 79%
- desktop bounce rate: 63%

Data limitations:

- no paid conversion data yet
- no source-level breakdown in this demo
- trial quality is unknown

## Drift Constraints

Candidates must not:

- sound like generic AI writing software
- imply customers never review release notes
- focus on internal engineering summaries instead of customer-facing changelogs
- use enterprise release-management language

Candidates should:

- make the weekly shipping pain obvious
- emphasize turning existing PR/issue context into customer-ready updates
- make review-before-publish feel safe
- improve trial intent, not just curiosity clicks

## Judging Rubric

Rank candidates by:

- specificity to customer-facing changelogs
- clarity for small SaaS teams
- likely `trial_started` intent
- preservation of review-before-publish safety
- low generic AI-writing language
- fit with the bounce and shallow-scroll problem
