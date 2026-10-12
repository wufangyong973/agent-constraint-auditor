# Daily learning — 2026-10-12

**Skill.** `--json` is the machine hire line. Same three decaying numbers as stdout and `--report`; different keys. Monday retarget reads this contract. Do not start a new public repo from this checkout.

**Why.** Sunday locked the human report (`Verdict: DECAY`). A gate consumer reads `decay.n_violations`, `decay.first_violation_index`, `decay.decay_slope`. Stdout still names them `violations` / `first_index` / `slope`.

**Worked example** (this repo).

```bash
constraint-auditor audit --constraints examples/decaying/constraints.yaml --transcript examples/decaying/journal.md --json
# exit 2
# verdict=DECAY  spec_name=decaying-agent
# decay.n_violations=3
# decay.first_violation_index=2
# decay.decay_slope=2.0
# stdout without --json still prints slope=2.000
# violations[].constraint_id = never_skip_lint, no_force_push (event 2 then 3)

constraint-auditor audit --constraints examples/jsonl_decaying/constraints.yaml --transcript examples/jsonl_decaying/events.jsonl --format jsonl --json
# same three decay keys; spec_name=jsonl-decaying-agent

constraint-auditor audit --constraints examples/stable/constraints.yaml --transcript examples/stable/journal.md --json
# verdict=CLEAN exit=0  decay.n_violations=0  first_violation_index=null  violations=[]
```

**Recall probe.** Name the three JSON keys for the decaying freeze field, and the CLEAN index.

Answer: `decay.n_violations`, `decay.first_violation_index`, `decay.decay_slope`. CLEAN index is `null` (stdout prints `None`). Do not pytest-lock this card; it is rewritten each morning.

**Retrieve.** `src/constraintauditor/audit.py` · `src/constraintauditor/cli.py` · `examples/decaying/`
