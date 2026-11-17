# CI Benchmark

An Agent Skill for diagnosing slow CI and measuring changes to workflow wall time on local or hosted runners. It guides a baseline, a controlled experiment, and a comparison of the required checks and artifacts.

## Install

```sh
npx skills add superjackche/ci-benchmark --skill ci-benchmark
```

Then ask your agent to use `ci-benchmark` to find what slows down a workflow and test a change against a comparable baseline.

[Read the skill](skills/ci-benchmark/SKILL.md).
