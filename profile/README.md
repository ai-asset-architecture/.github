# AI Asset Architecture (AAA)

AAA is an open-source governance toolkit for turning AI-assisted work into reusable, versioned, testable, and auditable engineering assets.

Instead of treating AI output as one-off chat results, AAA turns work into durable project assets:

- CLI workflows
- schemas and contracts
- runbooks and playbooks
- eval-oriented checks
- templates and reusable repo scaffolding
- evidence and approval boundaries

## What AAA is

AAA is not just a prompt library.

It is a multi-repo open-source system for teams that want to use AI in real software work without losing structure, traceability, or human accountability. The goal is to reduce agent drift and make AI-assisted delivery more repeatable.

Core idea:

> Agent productivity grows faster than governance capacity unless teams introduce stable evals, playbooks, schemas, and approval boundaries.

## What AAA can do today

The current public capability surface is centered on [`aaa-tools`](https://github.com/ai-asset-architecture/aaa-tools), the executable core of AAA.

Today AAA provides:

- Deterministic project bootstrap through `aaa init`
- Schema-backed init plan validation
- Multi-repo setup and template application
- Branch protection and CI verification workflows
- Governance repo checks and machine-readable reports
- Runbook execution with explicit file/runtime boundaries
- JSON and JSONL output for automation
- Skill, template, prompt, eval, and workflow distribution across AAA repos
- Safety boundaries such as path traversal protection and readiness/truth gating

## Why this matters

Most AI development workflows are still fragile:

- knowledge lives inside chat history
- quality standards are implicit
- maintainer review is manual reconstruction
- release evidence is inconsistent

AAA converts those weak points into explicit assets that can be versioned, reviewed, tested, and reused across projects.

## How AAA is structured

AAA is organized as a set of focused public repositories:

- [`aaa-tools`](https://github.com/ai-asset-architecture/aaa-tools): CLI runtime and governance automation
- [`aaa-actions`](https://github.com/ai-asset-architecture/aaa-actions): workflow automation building blocks
- [`aaa-evals`](https://github.com/ai-asset-architecture/aaa-evals): evaluation and regression assets
- [`aaa-prompts`](https://github.com/ai-asset-architecture/aaa-prompts): prompt assets separated from executable logic
- [`aaa-observability`](https://github.com/ai-asset-architecture/aaa-observability): reporting and visibility surfaces
- [`aaa-tpl-docs`](https://github.com/ai-asset-architecture/aaa-tpl-docs): documentation/project playbook templates
- [`aaa-tpl-service`](https://github.com/ai-asset-architecture/aaa-tpl-service): service starter template
- [`aaa-tpl-frontend`](https://github.com/ai-asset-architecture/aaa-tpl-frontend): frontend starter template

This repo layout reflects the AAA claim that governance should be executable and reusable, not left as informal maintainer habit.

## Primary entry point

If you want to understand AAA quickly, start here:

- Main repo: [`aaa-tools`](https://github.com/ai-asset-architecture/aaa-tools)
- Quickstart and public OSS docs: [`aaa-tools/README.md`](https://github.com/ai-asset-architecture/aaa-tools/blob/main/README.md)
- Public case study: [`agent-orchestrated-engineering-project.md`](https://github.com/ai-asset-architecture/aaa-tools/blob/main/docs/case-studies/agent-orchestrated-engineering-project.md)

## Current public status

- Status: `Public Preview`
- Current packaged CLI version: `2.0.0`
- Recommended OSS program application repo: `aaa-tools`

## Example maintainer workflows we are building around AAA

AAA is intended to support practical open-source maintenance workflows such as:

- PR triage and structured review assistance
- changelog and release-note drafting
- docs consistency checks
- eval generation and regression analysis
- upgrade and release verification workflows
- auditable multi-repo maintenance operations

Human approval remains required for merges, releases, and policy changes.

## 5-minute starting point

```bash
gh auth setup-git
python3 -m pip install "git+https://github.com/ai-asset-architecture/aaa-tools.git@v2.0.0"
aaa --version
```

Then explore:

```bash
aaa init validate-plan --help
aaa init --help
aaa run runbook --help
```

## What we are proving

AAA is an experiment in making AI-native software governance concrete:

- not chat-first, but asset-first
- not prompt-only, but script-first
- not full autonomy, but bounded automation with human sign-off

That is the core reason this project exists.
