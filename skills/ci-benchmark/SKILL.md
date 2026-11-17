---
name: ci-benchmark
description: Diagnose slow CI and measure improvements to workflow wall time on local or hosted runners.
---

1. **Baseline.** Use workflow logs to find the jobs and steps that determine when required checks finish. Separate queue time from execution. Reuse the workflow's commands, either locally in an isolated checkout or on a representative runner. Compare runs with the same revision, inputs, and cache conditions. Include setup and artifact handling in the elapsed time.
2. **Experiment.** Change one thing at a time. If setup dominates, test caching or reusing build outputs. If independent checks run in sequence, try running them in parallel and account for queueing, duplicate setup, and resource contention. If a long test suite still dominates, balance shards by measured test duration and verify that each test runs exactly once. Rerun noisy comparisons and measure the final combination.
3. **Verify.** Compare test coverage, required checks, supported platforms, failure reporting, and artifacts. Preserve dependencies between steps and keep full checks at the merge gate if adding a fast path for changed files. Report before and after wall time, where it was measured, and which checks require a different runner.
