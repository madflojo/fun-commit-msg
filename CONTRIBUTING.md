# Contributing

Thanks for your interest in improving this repository.

This project is an opinionated git-commit skill. Contributions are welcome, but
changes should preserve the core balance: accurate Conventional Commits, safe
git behavior, and just enough personality to avoid sounding robotic.

## What contributions are useful

Good contributions include:

- clarifying ambiguous guidance
- fixing grammar, formatting, or broken links
- improving shell-safety examples
- tightening staging and hook-failure guidance
- improving consistency across the main skill and references

## Before you open a PR

For larger changes, open an issue or start a discussion first if the proposal
would:

- change the public skill behavior materially
- weaken safety around staging or committing
- add tool-specific assumptions that reduce portability
- change the public identity or install instructions

Small fixes and editorial improvements can go straight to a pull request.

## Contribution guidelines

1. Keep examples generic.
   Avoid company-specific repos, issue trackers, or internal workflows unless
   there is a strong reason to include them.

2. Preserve the opinionated voice.
   This repo is not trying to document every acceptable way to make a commit.
   It is documenting one reliable way to do it safely.

3. Keep docs and skill behavior aligned.
   If you change commit guidance, update the README and reference docs in the
   same pull request.

4. Prefer concrete, testable advice.
   Recommendations should lead to safer commits and clearer history.

5. Proofread carefully.
   Check formatting, heading structure, and Markdown links before submitting.

## Commit messages and releases

This repository uses Release Please to generate release pull requests, tags, and
GitHub Releases from conventional commit history.

Please prefer conventional commit prefixes for merged changes:

- `feat:` for new behavior or materially expanded guidance
- `fix:` for corrections to instructions, examples, or metadata
- `docs:` for user-visible documentation improvements worth noting in releases
- `refactor:` for structural cleanup that keeps the same guidance
- `perf:` for performance-oriented improvements in examples or workflows
- `chore:`, `ci:`, `build:`, and `test:` for internal maintenance changes

Release Please uses Git tags as the canonical repository version. The
`metadata.version` field in `skills/fun-commit-msg/SKILL.md` is informational
only and is not release-managed.

## Repository structure

```text
skills/
  fun-commit-msg/
    SKILL.md
    references/
      MESSAGES.md
```

The repository-level docs, workflows, and release configuration exist only to
make the skill easier to publish and maintain.
