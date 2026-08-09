# TakT Skills Architecture

## Design Principles

- Core first: one canonical baseline for tooling and process
- Overlay second: stack and context concerns are additive
- Small blast radius: update one layer without breaking others
- Idempotent application: rerunning a skill should converge safely

## Capability Boundaries

### Core (`init-takt-devcontainer`)

Owns:

- `.devcontainer/devcontainer.json` baseline
- `.insitu.yml` baseline waves and verification hooks
- `.githooks/pre-commit` baseline quality gate wiring
- GitHub CLI extension bootstrap (`gh-insitu`, `gh-aw`, `gh-tt`)

Must not own:

- Stack-specific runtime setup details
- Framework-specific workflow jobs

### Stack overlays (`takt-stack-*`)

Owns:

- Runtime provisioning and cache strategy
- Build/test/lint commands for the stack
- Framework-specific workflow jobs and guardrails

Examples:

- Astro static-site deploy specifics
- Python virtual environment and test matrix
- Rust toolchain channels and clippy/fmt gates

### Profile overlays (`takt-profile-*`)

Owns:

- Repo-shape concerns independent of language
- CI behavior tied to operating model (website/service/docs)
- Publishing/deploy conventions

Examples:

- Website profile: pages artifact/deploy workflow
- Service profile: release and image publish checks
- Docs profile: doc linting and link integrity gates

## Composition Rules

1. Apply core first.
2. Apply exactly one stack overlay.
3. Apply one optional profile overlay.
4. Resolve conflicts by precedence: profile > stack > core.

## Validation Contract

Every skill should define:

- Required inputs
- Files created/updated
- Verification commands
- Safe re-entry behavior (idempotency)
