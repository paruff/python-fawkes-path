# Security Policy — python-fawkes-path

## Supported versions

| Version         | Supported                                    |
| --------------- | -------------------------------------------- |
| `main` branch   | ✅ Active — patches applied here first       |
| Tagged releases | ✅ Critical fixes backported where practical |
| Older releases  | ❌ No active support                         |

---

## Reporting a vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Report privately using one of these channels, in order of preference:

1. **GitHub private vulnerability reporting** (preferred):
   [Security → Report a vulnerability](https://github.com/paruff/python-fawkes-path/security/advisories/new)
   — this keeps the report confidential until a fix is published.

2. **Email**: Contact the maintainer via the email address on the
   [paruff GitHub profile](https://github.com/paruff). Use the subject line
   `[python-fawkes-path] Security report`.

Include in your report:

- Affected component (e.g. FastAPI route, pinned Python dependency, Dockerfile)
- Steps to reproduce or a minimal proof of concept
- Your assessment of severity and impact
- Whether you have already disclosed this elsewhere

---

## Response timeline

| Stage                                  | Target                                            |
| -------------------------------------- | ------------------------------------------------- |
| Acknowledgement                        | Within 72 hours of receipt                        |
| Initial triage and severity assessment | Within 5 business days                            |
| Fix or mitigation published            | Depends on severity (see below)                   |
| Public disclosure                      | After fix is available, coordinated with reporter |

**Severity guidelines:**

- **Critical** (CVSS ≥ 9.0): fix targeted within 7 days
- **High** (CVSS 7.0–8.9): fix targeted within 14 days
- **Medium / Low**: addressed in the next scheduled release

We will credit reporters in release notes unless you request anonymity.

---

## Scope

This policy covers the python-fawkes-path repository and its default
configuration. It does not cover:

- **Third-party components** — FastAPI, Uvicorn, OpenTelemetry, Python base
  images. Report upstream vulnerabilities to those projects; we update pinned
  versions when upstream patches are available.
- **Deployments built from modified configuration.**
- **[paruff/python-fawkes-path-gitops](https://github.com/paruff/python-fawkes-path-gitops)**
  — the desired-state manifests for this service live there and carry their
  own security policy.
- **The rest of the Fawkes suite** — each repo carries its own security policy.

---

## Known constraints

**This service exists to be run through the pipeline, not to be trusted.** It
is a deliberately minimal, disposable example with no authentication layer:
`/`, `/health`, `/ready`, `/info` and `/metrics` are served without authn.
Do not expose it beyond localhost, and do not treat it as a security baseline
to copy from.

**Deployment is driven from outside this repo.** CI opens a PR against the
companion GitOps repo to bump the deployed image tag; ArgoCD applies it.
Review those PRs like any other change with cluster reach.
