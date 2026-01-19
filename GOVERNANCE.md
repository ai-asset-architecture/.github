# ai-asset-architecture — Governance Baseline (v0.1)

This document defines the minimum governance baseline for all repositories under the GitHub Organization.

## 1. Scope
Applies to all repositories unless explicitly documented as an exception.

## 2. Branch Protection (v0.1 Baseline)

### 2.1 Default Branch
- Default branch: `main`

### 2.2 Protection Rules (apply to `main`)
- Require pull request reviews before merging: **ON**
  - Required approvals: **1**
- Require status checks to pass before merging: **ON**
  - Required checks (minimum): **lint / test / eval**
  - All checks must be executed via **aaa-actions** reusable workflows.
- Dismiss stale pull request approvals when new commits are pushed: **ON**
- Prevent force pushes: **ON**
- Require linear history: **OPTIONAL** (recommended: **ON**)

### 2.3 Exceptions
Any exception must be documented in `<repo>/README.md` under `Governance Exceptions`,
and approved by `@aaa/architect`.

#### 2.3.1 Known Exception (v0.1)
Current AAA org repositories are **private** and the GitHub plan does not allow
branch protection on private repos. Until the org plan supports it, branch protection
is **not enforced** on AAA repos. This exception does **not** apply to new project
orgs; they should enable branch protection as soon as the plan allows.

## 3. Teams & Ownership (Minimum Set)

### 3.1 Teams
- `@aaa/architect`: governance decisions and templates
- `@aaa/platform`: actions/tools/infra
- `@aaa/qa`: eval suites and quality gates
- `@aaa/pm`: prompts and docs templates

### 3.2 Repo Ownership Baseline
- `.github` -> `@aaa/architect` + `@aaa/platform`
- `aaa-actions` -> `@aaa/platform`
- `aaa-tools` -> `@aaa/platform` + `@aaa/architect`
- `aaa-evals` -> `@aaa/qa` + `@aaa/architect`
- `aaa-prompts` -> `@aaa/pm` + `@aaa/architect`
- `aaa-tpl-docs` -> `@aaa/architect` + `@aaa/pm`
- `aaa-tpl-service` -> `@aaa/architect` + `@aaa/platform`
- `aaa-tpl-frontend` -> `@aaa/architect` + `@aaa/platform`

## 4. Required Workflow Source
All required status checks must use `aaa-actions` pinned by tag:
- Example: `uses: ai-asset-architecture/aaa-actions/.github/workflows/lint.yml@v0.1.0`

## 5. Bootstrap Order (MVP) — v0.1

1. **.github**: PR/Issue templates + GOVERNANCE + CODEOWNERS
2. **aaa-actions**: lint/test/eval/release workflows + tag `v0.1.0`
3. **aaa-tpl-docs**: ACC/PP + `.ai-context.md` + PRD/ADR templates
4. **aaa-tpl-service**: minimal service skeleton + CI calling `aaa-actions`
5. **aaa-tpl-frontend**: minimal frontend skeleton + CI calling `aaa-actions`
6. **aaa-tools**: CLI stub (version/sync/lint/eval)
7. **aaa-evals**: minimal eval suite + baseline
8. **aaa-prompts**: schema + example prompts

## 6. Change Management
Changes to this baseline require:
- PR review from `@aaa/architect` (mandatory)
- Announcement in `.github` (via PR description + change log note)
