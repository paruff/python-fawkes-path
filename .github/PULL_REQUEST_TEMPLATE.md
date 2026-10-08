## What This PR Does

<!-- One sentence. -->

## Closes

<!-- Issue number(s): Closes #N -->

---

## AI-Assisted Review Block

<!-- REQUIRED. Complete before requesting review. Use Copilot or your AI agent to help fill this in. -->
<!-- DORA 2025 (REVIEW-01): Structured review blocks reduce review time by making context explicit. -->

**What does this PR do in one sentence?**

<!-- Ask Copilot: "Summarise this diff in one sentence for a PR description" -->

**What are the top 2–3 failure modes?**

<!-- Ask Copilot: "What are the most likely ways this diff could fail in production?" -->

**What tests cover this change?**

<!-- List test files under tests/. If none: explain why, or add tests before requesting review. -->

**Architecture check:**

<!-- Ask Copilot: "Does this diff break the health/metrics/trace contract or the pipeline wiring?" -->

- [ ] No secrets or credentials in any changed file
- [ ] No `--no-verify` or hook bypasses
- [ ] `pytest tests/unit` passes locally before requesting review
- [ ] `/health`, `/ready`, `/metrics` and `/info` response shapes are unchanged (the GitOps repo and dashboards depend on them)
- [ ] Dependency pins in `pyproject.toml` and `requirements*.txt` were changed together

**What I was NOT sure about (flag for human review):**

<!-- Any judgment call, ambiguous requirement, or edge case you deferred to the reviewer. -->

---

## Checklist

- [ ] `pytest tests/unit` passes
- [ ] PR is < 400 changed lines, OR `large-pr-approved` label has been applied by a human
- [ ] No secrets or credentials in any changed file
- [ ] `docs/` / `README.md` updated if an endpoint or its contract changed
