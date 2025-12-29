---
name: release
description: Automates PR review, approval, and release for the current branch in Laravel projects. Includes CI checks, local tests, quick Laravel code review, approval, squash merge, branch cleanup, and Git tagging.
allowed-tools: Read, Grep, Glob, Bash, Edit, Write
---

You are a specialized Claude Code or Opencode or other agent that supports skill. This skill is for automating PR release workflows on Laravel projects.

## Core Functionality

### 1. Get PR for Current Branch

- Run `git branch --show-current` to identify the current branch
- Use `gh pr list --head <current-branch> --state open --json number -q '.[0].number'` to get the associated PR number
- Verify PR exists and is open; abort if none found

### 2. Quick Code Review (Laravel Way)

**Note**: This is a lightweight review for PR approval. For comprehensive code review, use the review skill first.

- Scan key Laravel files (app/Models/, app/Controllers/, database/migrations/) using Grep/Read
- Check for "Laravel Way" violations:
  - Raw SQL instead of Eloquent (`grep -r "DB::" app/`)
  - Missing policies for authorization (`grep -r "authorize(" app/Controllers/`)
  - Improper facade usage or missing Form Requests for validation
  - Security issues like mass assignment without $fillable
- Generate summary comment with findings (e.g., "Quick review: Code follows Laravel conventions. Minor suggestion: use Eloquent relationships instead of raw queries in Controller.php.")

### 3. CI and Local Test Checks

- Run `gh pr checks <PR-number>` to verify all CI checks pass
- Run `php artisan test` locally to ensure tests pass
- Abort if CI or tests fail
- **Note**: Comprehensive test coverage should be handled by review skill before PR creation

### 4. Update Changelog

- Read CHANGELOG.md to understand current format
- Determine release version: Check latest tag with `git describe --tags --abbrev=0` and increment (e.g., patch for fixes, minor for features)
- Add new release entry with current date: Update CHANGELOG.md with changes from PR (use PR description, commits, or review findings)
- Commit changelog update: `git add CHANGELOG.md && git commit -m 'chore: update changelog for v<next-version>'`
- Push changelog commit: `git push origin <current-branch>` (this updates the PR)

### 5. Leave Comment and Approve

- Post review summary: `gh pr review <PR-number> --comment -b "<review-summary>"`
- Approve PR: `gh pr review <PR-number> --approve`

### 6. Merge and Clean Up

- Squash merge: `gh pr merge <PR-number> --squash --delete-branch -t "feat: <brief-description from PR>" -b "Squashed commits for release."`
- Switch to main and pull: `git checkout main && git pull origin main`
- Delete PR branch: `git branch -D <PR-branch>` from github and local

### 7. Create Git Tag

- Use the version determined in step 4
- Create release: `gh release create v<next-version> --generate-notes --title "Release v<next-version>" --notes "Automated release from <branch>."`

## Task Approach

1. Identify current branch and PR
2. Perform quick Laravel code review (lightweight - comprehensive review should be done via review skill)
3. Verify CI and local tests pass
4. Update CHANGELOG.md with release entry (committed and pushed to PR)
5. Review, approve, and merge PR
6. Clean up and tag release
7. Provide summary with links

## Relationship to Review Skill

- **Review skill**: Development workflow - comprehensive code review, test creation/fixing, cleanup, creates/updates PR
- **Release skill**: Release workflow - assumes PR exists and was reviewed, performs quick validation, approves, merges, tags
- Use review skill first for new features/changes, then release skill for PR approval and release

## Return Format

Provide clear summary of:

- PR identified and status
- Review findings and CI/test results
- Changelog updated with version and date
- Approval and merge details
- Tag created and release link
- Any errors or aborts
- Link to github PR that can be clicked on
  