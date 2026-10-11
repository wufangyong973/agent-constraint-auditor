# Daily learning — 2026-10-11

**Skill.** Sunday usefulness gate is decaying `--report`, not only the nine-exit string. Stdout is the hire line; `--report` is the third-person artifact a reviewer reads.

**Why.** MATRIX recites `0/2/0/2/1/1/0/2/1`. The freeze field is still `3 / first_index=2 / slope=2.000` on the markdown report. Interview pack: the report opens with `Verdict: DECAY`.

**Worked example** (this repo). Same three numbers on journal and JSONL.

```bash
constraint-auditor audit --constraints examples/decaying/constraints.yaml --transcript examples/decaying/journal.md --report /tmp/decay.md
# stdout: verdict=DECAY exit=2 violations=3 first_index=2 slope=2.000
# report title then:
# Verdict: DECAY
# The transcript records 3 constraint violations, first at event 2.
# Events: 4 · Violations: 3
# First violation index: 2
# Decay slope (Q4-Q1 rate): 2.000
# quartile row 0.00 | 0.00 | 1.00 | 2.00

constraint-auditor audit --constraints examples/jsonl_decaying/constraints.yaml --transcript examples/jsonl_decaying/events.jsonl --format jsonl --report /tmp/jsonl-decay.md
# same Verdict: DECAY + same 3 / first at event 2 / slope 2.000

constraint-auditor audit --constraints examples/stable/constraints.yaml --transcript examples/stable/journal.md --report /tmp/clean.md
# Verdict: CLEAN — The transcript holds all declared constraints across 4 events.
```

**Recall probe.** After the report title, what is the first line, and which three numbers must still match decaying?

Answer: `Verdict: DECAY`. Violations 3, first at event 2, slope 2.000. Same on `examples/jsonl_decaying`. Do not pytest-lock this card; it is rewritten each morning.

**Retrieve.** `src/constraintauditor/decay.py` · `examples/decaying/` · `docs/INTERVIEW.md`
