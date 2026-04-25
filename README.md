# fun-commit-msg

An agent skill for generating Conventional Commit messages and safely creating
git commits from staged changes.

The canonical skill identifier is `fun-commit-msg`. The repository is
structured so it can be installed directly with GitHub CLI or copied manually
into an agent skill directory.

## What the skill does

The `fun-commit-msg` skill helps an agent:

- review staged changes before proposing a commit
- generate clean Conventional Commit subjects and bodies
- preserve the user's staging boundary
- perform non-interactive commits safely with shell-friendly input handling
- avoid common git pitfalls such as empty staged diffs or hook failures

## Repository layout

```text
skills/
  fun-commit-msg/
    SKILL.md
    references/
      MESSAGES.md
```

The main prompt lives at `skills/fun-commit-msg/SKILL.md`.
Supporting guidance lives under `references/`.

## Installing the skill

Primary path: install from GitHub CLI with `gh skill install`.

```bash
gh skill install madflojo/fun-commit-msg
```

Optional: pin to a tag or commit for reproducible installs:

```bash
gh skill install madflojo/fun-commit-msg@v1.0.0
gh skill install madflojo/fun-commit-msg@<commit-sha>
```

Fallback path: manually copy `skills/fun-commit-msg/` into either:

- `.agents/skills/` in a repository
- `~/.agents/skills/` for a user-level install

## Compatibility notes

This skill assumes:

- `git` is installed
- the current directory is inside a git worktree
- the user or agent has already decided the staged changes belong in one commit

## Example messages

These are examples of the kind of messages this skill should generate:

- `fix(auth): handle expired token refresh before retries`
- `docs: add gh skill install guidance without the treasure map`
- `refactor(config): split validation from defaults for calmer constructors`
- `test(cache): catch stale entry eviction before it starts free-range browsing`

That means most outputs stay clean and conventional, while lighter changes can
end with a single relevant emoji:

- `docs: add gh skill install guidance without the treasure map 🗺️`
- `test(cache): catch stale entry eviction before it starts free-range browsing 🧹`

For a non-trivial change, the skill can also produce a short body:

```text
feat(cli): add dry-run output for release command

Show the planned release actions without mutating tags or changelog files.
This keeps the command useful when the user wants a quick confidence check.
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution and release guidance.

## License

Licensed under [Apache-2.0](LICENSE).
