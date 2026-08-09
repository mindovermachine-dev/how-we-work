# skills

Shared TakT skill library for bootstrapping repositories with a consistent process-first foundation.

## Goals

- Keep a stable core setup for TakT workflows
- Layer stack-specific capabilities without copy-paste drift
- Add profile/context overlays for website, service, docs, and similar repo shapes

## Layering Model

1. `init-takt-devcontainer` (core, required)
2. `takt-stack-*` (runtime/framework overlays)
3. `takt-profile-*` (repo-context overlays)

## Initial Contents

- Core skill: `.github/skills/init-takt-devcontainer/SKILL.md`
- Stack stubs: Astro, Jekyll, Python, Golang, Rust
- Profile stubs: Website, Service, Docs
- Architecture notes: `docs/architecture.md`

## Next Steps

- Fill each stack skill with concrete file templates and validation checks
- Define a compatibility matrix between stacks and profiles
- Add smoke-test scripts for generated scaffolds
