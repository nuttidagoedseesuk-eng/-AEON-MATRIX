# AEON MATRIX Constitution

This document defines the repository governance baseline for development safety, review quality, and recovery readiness.

## 1) Branch Protection Rules

Apply these rules to `main` (and any long-lived release branch such as `release/*`):

- Require pull request before merge (no direct pushes).
- Require at least **1 approving review** from a code owner or maintainer.
- Dismiss stale approvals when new commits are pushed.
- Require all required status checks to pass before merge.
- Require branches to be up to date before merge.
- Restrict force-push and branch deletion.
- Include administrators in protection (no bypass except emergency procedure below).

## 2) Pull Request Policy

Every PR must:

1. Link the related issue (example: `Closes #<id>`).
2. Use focused, minimal scope (one intent per PR).
3. Include a clear summary of what changed and why.
4. Pass required checks before requesting final review.
5. Receive reviewer approval before merge.

Preferred merge strategy: **Squash and merge** to keep history readable.

## 3) Recovery Procedures

When a bad change reaches `main`:

1. **Stabilize**: Pause new merges until impact is understood.
2. **Assess**: Identify bad commit(s), affected scope, and urgency.
3. **Recover**:
   - Fast path: revert the offending commit(s) with a new PR.
   - Urgent production incident: apply hotfix in a short-lived `hotfix/*` branch and merge via reviewed PR.
4. **Verify**: Confirm checks pass and affected behavior is restored.
5. **Document**: Add a short post-incident note in the linked issue/PR.

Emergency branch protection bypass is allowed only for critical outage recovery and must be documented in the follow-up PR/issue.

## 4) Documentation Structure

Repository governance documents are organized as:

- `README.md` — project overview and entry point.
- `CONSTITUTION.md` — operational governance rules (this file).
- `GOVERNANCE-MANIFESTO.md` — principles and philosophy.
- `LICENSE` — legal terms.

Any governance change must be proposed through PR and reviewed by maintainers.
