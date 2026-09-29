# Professional Development Standards (The Ultimate Constitution)

## 1. Development Lifecycle
- **Value Proposition First:** No code before defining the problem solved and the unique value.
- **TDD Enforcement:** Tests (Integration/E2E) must be written and pass before code is considered complete.
- **Self-Healing Protocol:** If a test fails, the agent must diagnose, patch, and retry automatically up to 3 times before requesting user help.
- **Issue-First Development:** Every feature or task must be tracked via a GitHub Issue (`gh issue create`) and developed in a dedicated branch.

## 2. Quality Gates (QA) & Security
- **QA Pipeline:** All code must pass `qa_check.sh` (Ruff, Bandit, Vulture, Pytest).
- **UX Acceptance Criteria:** UI must support real-world usage patterns: Filtering, Search, Analytics, and Dark Mode. No "basic/dummy" UI is acceptable.
- **Security & Secrets Guard:** Zero hardcoded secrets allowed. Automated checks ensure no API keys or credentials are committed.

## 3. Operational Discipline & Deployment
- **Atomic Writes:** Use `read_file` then `write_file` (Full Overwrite). Avoid `patch` for complex files.
- **Audit Trail:** Maintain `CHANGELOG.md` and `HEALTH.md` for every batch delivery.
- **Rapid Rollback Strategy:** Features are merged via PRs only after passing all gates. In case of failure, immediate rollback (`git revert`) is enforced.
- **Impact vs Effort:** Prioritize high-impact user features over aesthetic-only additions.

## 4. Collaboration
- **Async Communication:** Report status as `[Status Report]` in batches. No mid-task waiting unless critical.
- **Error Transparency:** Report the root cause and the fix applied in the status report.
