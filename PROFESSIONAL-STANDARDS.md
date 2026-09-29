# Professional Development Standards (The Ultimate Constitution)

## 1. Development Lifecycle
- **Value Proposition First:** No code before defining the problem solved and the unique value.
- **TDD Enforcement:** Tests (Integration/E2E) must be written and pass before code is considered complete.
- **Self-Healing Protocol:** If a test fails, the agent must diagnose, patch, and retry automatically up to 3 times before requesting user help.
- **Issue-First Development:** Every feature or task must be tracked via a GitHub Issue (`gh issue create`) and developed in a dedicated branch.

## 2. Quality Gates (QA) & Security
- **QA Pipeline:** All code must pass `qa_check.sh` (Ruff, Bandit, Vulture, Pytest).
- **UX Acceptance Criteria:** UI must support real-world usage patterns: Filtering, Search, Analytics, and Dark Mode.
- **Security & Secrets Guard:** Zero hardcoded secrets allowed. Automated checks ensure no API keys or credentials are committed.

## 3. Dependency & Vulnerability Management
- **Dependency Auditing:** Run `pip-audit` or `safety check` as part of CI to detect known CVEs.
- **Dependency Locking:** Pin all dependencies to ensure reproducible builds.

## 4. Operational Discipline & Deployment
- **Atomic Writes:** Use `read_file` then `write_file` (Full Overwrite).
- **Audit Trail:** Maintain `CHANGELOG.md` and `HEALTH.md` for every batch delivery.
- **Rapid Rollback Strategy:** Features are merged via PRs only after passing all gates. In case of failure, immediate rollback (`git revert`) is enforced.

## 5. Architecture & API Governance
- **Living API Contract:** Any backend change must update `API-CONTRACT.md` to keep Frontend/Backend in-sync.
- **Contract-First Design:** API endpoints documented before implementation.

## 6. Continuous Improvement & Data-Driven Growth
- **Post-Mortem & Retrospective Protocol:** At the end of every major phase, perform a "Retrospective" to identify wins, failures, and necessary changes to these standards. Update this document accordingly to ensure it is a living system.
- **Data-Driven Decisions:** If user-facing, implement lightweight logging to track usage patterns. New features must be prioritized based on real usage data/feedback, not assumptions.


## 7. Task Complexity Matrix (Operational Agility)
To balance speed and structure, tasks are categorized into two levels:
- **Level 1 (Micro-Fix / Script):** Small bug fixes, standalone scripts, or minor updates. Managed via a local `TODO.md` file (Fast, lightweight).
- **Level 2 (Feature / Epic):** New UI features, database migrations, architecture refactoring. Managed strictly via **GitHub Issues + Feature Branches + Pull Requests**.

## 8. Collaboration
- **Async Communication:** Report status as `[Status Report]` in batches.
- **Error Transparency:** Report the root cause and the fix applied in the status report.
