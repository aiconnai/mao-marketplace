# Changelog

All notable changes to MAO will be documented in this file.

## [1.2.0] - 2026-03-13

### Added
- **Phase 0: Research** — optional codebase reconnaissance before decomposition for brownfield projects and unfamiliar APIs; produces `.orchestrator/state/context.md`
- **`/mao-resume` command** — resume interrupted MAO runs; loads task-graph.json, resets interrupted tasks, handles failed tasks (retry/skip/manual), re-enters execution loop
- **`acceptance` object in task specs** — replaces flat `verify` string with structured `done_state`, `verify_commands`, and `verify_criteria` fields
- **STATE.md** — live run snapshot written after each wave; enables session recovery and human-readable status
- **SUMMARY.md** — final run report written after integration with task table, escalations, and model distribution
- **Plan review hard gate** — ⛔ execution blocked until user explicitly confirms the decomposition plan; supports iteration

### Changed
- Architect agent now reads context.md from Phase 0 research before decomposing
- Architect responsibilities expanded: "Research first", "Analyze the codebase", "Define acceptance"
- Orchestrator responsibilities expanded: STATE.md and SUMMARY.md writing
- Executor prompt templates (worker + implementer) now receive full acceptance criteria
- Task decomposition reference adds Acceptance Criteria section with good/bad examples
- SKILL.md workflow updated with Phase 0, plan gate, STATE.md, and SUMMARY.md
- Directory structure in SKILL.md shows new state files

## [1.1.0] - 2026-03-08

### Added
- Landing page (GitHub Pages)
- CI/CD pipeline (JSON validation, structure checks, shell linting)
- Release workflow (npm publish + tar.gz assets)
- npm installer CLI (`npx mao-orchestrator init`)
- Bash installer (`curl | bash`)
- PowerShell installer (`irm | iex`)
- GitHub Action for task-graph validation
- `CHANGELOG.md`, `LICENSE`, `CONTRIBUTING.md`

## [1.0.0] - 2026-03-06

### Added
- Initial release: 8 agents, 3 slash commands, 1 skill
- Claude Code slash commands (`/mao`, `/mao-plan`, `/mao-status`)
- 7-phase workflow (Decompose, Schedule, Execute, Verify, Review, Reflect, Integrate)
- Model tiering (Opus/Sonnet/Haiku) with complexity scoring
- Git worktree isolation for parallel execution
- 5-layer self-correction protocol
- `USAGE.md` command usage guide
- `GUIDE.md` Claude Primer integration guide
