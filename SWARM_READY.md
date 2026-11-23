# Swarm-ready handoff

Repository: `Kitkitkittt/jevlike`. Contract: `swarm-ready/v1`. Source inspection: 2026-11-23.
Default branch: `main`. Inspected base: [94f5fd1b0b11](https://github.com/Kitkitkittt/jevlike/commit/94f5fd1b0b11d52bbdfdf4e0ee6aa96b568f8452).

**Status: documented; runtime qualification is unverified.** This file defines an agent workflow. It does not install a shell command, enroll the repository in a scheduler, certify test success, or activate VMs. Follow the current user task and existing repository instructions; retain prior authorization within its actual scope.

## Invoke

Give the working agent this prompt:

```text
swarm ready: <one measurable repository objective>
Read SWARM_READY.md and the applicable AGENTS.md. Continue the current owned
work or ready issue, establish the baseline and acceptance check, then prepare
a bounded worker handoff. Use existing authorized tools and capacity. Report
what is documented, implemented, tested, and observed separately.
```

If a `swarm-ready` skill is installed, load it. Otherwise execute the documented workflow directly. Treat the phrase as an agent instruction unless the installed CLI explicitly advertises it. Inspect help/version before using optional command adapters.

## Repository starting point

Read the [repository instructions](AGENTS.md), [README](README.md) and [package declaration](pyproject.toml).

For separately scoped model or environment work, select one reproducible experiment under the existing README and AGENTS contract.

Hold dataset, seed and evaluation budget fixed. Report raw task outcomes alongside shaped rewards; preserve the documented failure cases and negative controls.

The base above is an inspection snapshot, not a permanent working branch. Refresh the actual target branch, current issues, incumbent worker and applicable nested instructions before editing. Preserve unrelated changes and upstream/fork boundaries.

## Execution logic

1. **Recover context.** Read the current issue, work order and last evidence-backed handoff. Keep useful work and the active worker. Record source commit, unresolved criteria and the next action; avoid repeating completed investigation.
2. **Define success.** State one outcome, baseline, target, changed paths, verification command and expected result. Keep acceptance criteria and reference data fixed unless the user changes the requirement.
3. **Bound the attempt.** Reuse the existing owner/task/attempt identities, action scope, resource limits, time/cost budget and retry allowance. Do not demand a new user-written permission receipt for already authorized work. If a real capability or grant is missing, name the exact blocked action and continue independent work.
4. **Partition only useful work.** Use one writer per branch/worktree and non-overlapping change scope. Reuse the existing task ledger and dependency graph. Reserve verification capacity before adding workers; avoid recursive worker growth and duplicate coordinators.
5. **Implement and measure.** Make the smallest coherent change. Use differential checks when a trusted reference exists, and deterministic failure simulation when it materially improves reproduction. Record the seed/configuration and counterexamples. Do not weaken tests, rewrite baselines or hide pre-existing failures to claim success.
6. **Verify and integrate.** Verify the exact returned commit independently in a clean environment. Recheck the final integrated revision when changes interact. Follow existing review, merge and deployment rules; a green worker report alone cannot override them. Use the narrowest checks that resolve a concrete risk.
7. **Checkpoint and finish.** Save candidate SHA, evidence, measured outcome, remaining blockers and a precise next action before context/lease expiry. Reconcile lost or duplicate completions before retrying. Release only the run's owned resources after preserving evidence. Stop when the requested outcome is met or a concrete blocker prevents the next required action.

## Verification starting point

For documentation-only changes, run from the repository root with Git:

```sh
git --no-lazy-fetch -c core.fsmonitor=false ls-files --error-unmatch -- \
  AGENTS.md SWARM_READY.md README.md pyproject.toml \
  jevlike/data.py jevlike/train.py jevlike/eval.py jevlike/predict.py jevlike/vision.py \
  examples/doom/README.md examples/chess/README.md &&
  git --no-lazy-fetch -c core.fsmonitor=false diff --no-ext-diff --no-textconv --check HEAD -- \
    AGENTS.md SWARM_READY.md
```

Expect eleven tracked paths and no whitespace diagnostics. An unmatched path
or a whitespace error fails the check. For a committed patch, replace `HEAD`
with the review base and candidate SHAs. Read the linked headings and compare
the README CLI names with `[project.scripts]` in `pyproject.toml`. The Git
checks do not validate links or import the CLI modules.

The [README quickstart](README.md#quickstart) installs the package and runs the
text model, generating data and a checkpoint. It remains the release test for
quickstart command changes. The [installation and tests](AGENTS.md#install-and-verify)
are separate; the package's default pytest discovery points to `tests`, not the
separate game smoke checks documented there. Keep the docs review offline: no
dependencies, data or model downloads, checkpoint loads, training, inference,
game runs, or film rendering.

Preserve the [text experiment limits](README.md#what-to-expect), the
[Doom screen-dependence controls](examples/doom/README.md#audit-screen-dependence),
and the [chess checkpoint limitations](examples/chess/README.md#results).
Passing a docs check does not reproduce those results or qualify the models.

## Required handoff result

Return a concise record with `repository`, `objective`, `issue_or_work_order`, `base_sha`, `candidate_sha`, `owner`, `task_id`, `attempt_id`, `worker/session`, `branch/worktree`, `changed_paths`, `environment`, `resource/budget limits`, `acceptance`, `commands_and_results`, `evidence_refs`, `known_failures`, `blocker_owner`, `next_action`, and `cleanup_status`. Use null/unknown when a field is unavailable; never manufacture evidence or authority.

Keep documentation readiness, command availability, source tests, live environment qualification and accepted outcome as separate states. Count verified outcomes, regressions, elapsed time, cost and human interventions. Commits, lines, tokens and worker count describe activity only.
