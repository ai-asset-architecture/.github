# AAA Project Bootstrap Protocol
> Strict instruction set for AI Agents (Codex CLI) to initialize a new project based on ai-asset-architecture (aaa).

## 0. Pre-requisites Check
- Verify `gh` CLI is installed and authenticated (`gh auth status`).
- Verify `git` is installed.
- Ask user for:
  1. `PROJECT_NAME` (e.g., "Personal Body OS")
  2. `PROJECT_PREFIX` (e.g., "pbos")
  3. `TARGET_ORG` (e.g., "personal-body-os")

## 1. Directory Setup
1. Create workspace directory: `mkdir -p {PROJECT_PREFIX}_WORKSPACE`
2. Enter directory: `cd {PROJECT_PREFIX}_WORKSPACE`

## 2. Repo Creation (Using Templates)
Execute commands sequentially. If repo already exists, skip creation and continue with hydration.

### 2.1 Brain (Docs)
- Command: `gh repo create {TARGET_ORG}/{PROJECT_PREFIX}-docs --template ai-asset-architecture/aaa-tpl-docs --private --clone`
- Action:
  - Enter folder: `cd {PROJECT_PREFIX}-docs`
  - Replace template variables:
    - `{{PROJECT_NAME}}` -> `{PROJECT_NAME}`
    - `{{PROJECT_PREFIX}}` -> `{PROJECT_PREFIX}`
    - `{{GITHUB_ORG}}` -> `{TARGET_ORG}`
  - Commit: `git commit -am "chore: hydrate template variables"`
  - Push: `git push`
  - Return: `cd ..`

### 2.2 Body (Service)
- Command: `gh repo create {TARGET_ORG}/{PROJECT_PREFIX}-service --template ai-asset-architecture/aaa-tpl-service --private --clone`
- Action:
  - Enter folder: `cd {PROJECT_PREFIX}-service`
  - Replace template variables (same as above)
  - Ensure docs link points to `{PROJECT_PREFIX}-docs`
  - Commit & Push
  - Return: `cd ..`

### 2.3 Face (Frontend)
- Command: `gh repo create {TARGET_ORG}/{PROJECT_PREFIX}-frontend --template ai-asset-architecture/aaa-tpl-frontend --private --clone`
- Action:
  - Enter folder: `cd {PROJECT_PREFIX}-frontend`
  - Replace template variables (same as above)
  - Ensure docs link points to `{PROJECT_PREFIX}-docs`
  - Commit & Push
  - Return: `cd ..`

## 3. Local Context Injection (The Hook)
1. In the workspace root, create `.codex/context.md`.
2. Content:
```markdown
# Project Context
- Constitution: {PROJECT_PREFIX}-docs/AI_COMMAND_CENTER.md
- Laws: {PROJECT_PREFIX}-docs/PROJECT_PLAYBOOK.md
```

## 4. Verification
- List created directories.
- Print: "Bootstrap complete. Please review the created repos."

## 5. Reference
- Runbook: `aaa-tools/runbooks/init/INIT_PROJECT.md`
- Plan: `aaa-tools/runbooks/init/plan.v0.1.json`
- Output schema: `aaa-tools/runbooks/init/output.schema.json`
