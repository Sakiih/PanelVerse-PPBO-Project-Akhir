# PanelVerse Integration Guide

**Owner:** Member 1
**Status:** Living document — update after each integration decision.
**Workflow source of truth:** `MASTER_PROJECT.md` and `docs/TEAM_ONBOARDING.md`.

## 1. Rules

- One GitHub repository and one Laravel application.
- `main` is the shared baseline and primary branch.
- Each member works on the assigned feature branch based on latest `main`.
- Members may push their own feature branches; no direct push to `main`.
- Member 1 alone creates and manages the `final` integration branch when feature work is ready.
- No feature Pull Request is needed until `final` exists. Then each feature PR targets `final`, never `main`.
- Member 1 reviews/merges feature PRs into `final`, verifies integration, and manages a PR from `final` to `main`.
- Do not create a `develop` branch or a separate Laravel/repository per module.
- Never commit `.env`, tokens, passwords, or credentials.

## 2. Member feature branches

| Member | Branch |
|---|---|
| 1 | `feature/member-1-project-management` |
| 2 | `feature/member-2-ui-foundation` |
| 3 | `feature/member-3-homepage-catalog` |
| 4 | `feature/member-4-detail-reader` |
| 5 | `feature/member-5-database` |
| 6 | `feature/member-6-rest-api` |
| 7 | `feature/member-7-oop-architecture` |

## 3. Integration sequence

1. Before work, update local `main` with `git pull --ff-only origin main`; create or switch to the assigned feature branch.
2. Keep changes within the assigned scope. Coordinate changes that affect another member's files or shared contracts.
3. Review staged files, commit, and push only to the assigned feature branch.
4. Report branch readiness to Member 1. Wait for Member 1 to create and announce `final` before opening a PR.
5. Open a PR from the feature branch to `final`; include purpose, files, checks actually run, integration needs, and screenshots/API evidence when relevant.
6. Member 1 reviews the change; the owner of a touched contract participates in review. Resolve conflicts without discarding another member's work.
7. Member 1 merges approved feature PRs into `final`, tests/inspects the integrated application, and records issues.
8. When integration is ready, Member 1 opens and manages a PR from `final` to `main`. No feature PR targets `main`.

## 4. Pull Request checklist

- [ ] Target branch is `final` (for feature work) or `main` (only Member 1's final integration PR).
- [ ] Purpose is clear and changes match the member's scope.
- [ ] No `.env`, secret, credential, or unrelated file is included.
- [ ] No duplicate/conflicting migration, route, contract, or component was introduced.
- [ ] Relevant checks/tests were run and reported truthfully.
- [ ] Documentation and integration requirements are described.
- [ ] Screenshot/API evidence is included when useful.

## 5. Integration log

| Date | PR / Branch | Summary | Reviewer | Status |
|---|---|---|---|---|
| | | | | Pending |

## 6. Cross-member decisions

| Date | Topic | Decision | Approved by |
|---|---|---|---|
| | Database contract | | |
| | Blade component contract | | |
| | API contract | | |
| | OOP architecture | | |

## 7. Checks after integration

Record the command actually run, environment, result, and any issue. Do not mark a test as passed if it was not run. Keep `final` as the integration candidate until Member 1's PR to `main` is approved and merged.
