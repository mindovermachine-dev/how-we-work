---
name: init-takt-devcontainer
description: >-
  Initialize a minimal standalone devcontainer with TakT tooling
  (gh-aw, gh-insitu, gh-tt) and baseline process scaffolding.
---

# Init TakT Devcontainer

Use this skill to create the shared baseline used by all stack and profile overlays.

## Use when

- A repository needs TakT-compatible baseline scaffolding
- You want a process-first setup that does not depend on PR-only workflows

## Responsibilities

- Create baseline devcontainer and insitu wiring
- Install required GitHub CLI extensions
- Set up baseline quality gate hooks

## Output Contract

- Adds/updates core scaffolding files only
- Does not include stack-specific runtime details
- Leaves stack and profile concerns to overlay skills

## Validation

- Core waves execute successfully
- Baseline hooks run without stack-specific assumptions
