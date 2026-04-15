# Agent Analytics Snapshot

Use this when you want a reproducible dated data snapshot for an autoresearch growth run.

`npx` collects the evidence for the run. It does not directly create `results.tsv`; the autoresearch loop creates `results.tsv` as it judges rounds.

The usual flow is:

1. collect a dated 7-day data snapshot
2. summarize the snapshot in `brief.md`
3. initialize `results.tsv` with the header if this is a new run
4. run the agent loop
5. let the loop append one row to `results.tsv` after each judging round

Use placeholders for your own project and events:

```bash
# Run once if this machine or agent runtime is not logged in.
npx @agent-analytics/cli@0.5.12 login

PROJECT_SLUG=my-site
PRIMARY_EVENT=signup
PROXY_EVENT=cta_click
RUN_DATE=$(date +%F)

mkdir -p "data/$RUN_DATE"

# Keep collecting the full snapshot even if one analytics command fails.
# Failed commands write their error output and exit code into the saved file.
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

run_snapshot_command "data/$RUN_DATE/insights.txt" \
  npx @agent-analytics/cli@0.5.12 insights "$PROJECT_SLUG" --period 7d
run_snapshot_command "data/$RUN_DATE/pages.txt" \
  npx @agent-analytics/cli@0.5.12 pages "$PROJECT_SLUG" --since 7d
run_snapshot_command "data/$RUN_DATE/funnel.txt" \
  npx @agent-analytics/cli@0.5.12 funnel "$PROJECT_SLUG" \
  --steps "page_view,$PROXY_EVENT,$PRIMARY_EVENT" \
  --since 7d
run_snapshot_command "data/$RUN_DATE/${PROXY_EVENT}-events.txt" \
  npx @agent-analytics/cli@0.5.12 events "$PROJECT_SLUG" \
  --event "$PROXY_EVENT" \
  --days 7 \
  --limit 50
run_snapshot_command "data/$RUN_DATE/${PRIMARY_EVENT}-events.txt" \
  npx @agent-analytics/cli@0.5.12 events "$PROJECT_SLUG" \
  --event "$PRIMARY_EVENT" \
  --days 7 \
  --limit 50
run_snapshot_command "data/$RUN_DATE/experiments.txt" \
  npx @agent-analytics/cli@0.5.12 experiments list "$PROJECT_SLUG"
```

Then update `brief.md`:

- set the project, surface, current control, primary metric, proxy metric, and guardrails
- paste the same commands into `Analytics Commands Or Data`
- summarize the files under `Live Data Snapshot`
- mention sparse data, auth failures, missing events, or uncertain attribution under `Data limitations`

For a new run, initialize `results.tsv` with only the header:

```bash
printf 'round\tcandidate_a\tcandidate_b\tcandidate_ab\twinner\tborda_a\tborda_b\tborda_ab\tstatus\trationale\n' > results.tsv
```

Then prompt the agent:

```text
Read program.md and brief.md. Use data/<RUN_DATE>/ as the latest 7-day snapshot. Run 5 rounds. Append one row per round to results.tsv and write final_variants.md with two distinct variants.
```
