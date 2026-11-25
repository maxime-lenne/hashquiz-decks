# markuiz-decks

<!-- markdownlint-disable -->
<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" width="80" height="80" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/githubactions/githubactions-original-wordmark.svg" alt="Github Action" width="80" height="80" />
</p>

<p align="center">
  <strong>markuiz-decks</strong>
</p>

<p align="center">
<a href="https://github.com/maxime-lenne/markuiz-decks/actions?query=workflow%3ALint+branch%3Amain">
		<img src="https://img.shields.io/github/actions/workflow/status/maxime-lenne/markuiz-decks/lint.yml?branch=main"
			 alt="Build Status">
	</a>
  <a href="https://github.com/maxime-lenne/markuiz-decks/actions?query=workflow%3ARelease+branch%3Amain">
		<img src="https://img.shields.io/github/actions/workflow/status/maxime-lenne/markuiz-decks/release.yml?branch=main"
			 alt="Build Status">
	</a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
  </a>
  <a href="https://bun.sh">
    <img src="https://img.shields.io/badge/Package%20Manager-Bun-black" alt="Bun" />
  </a>
  <a href="https://gitmoji.dev">
    <img src="https://img.shields.io/badge/gitmoji-%20😜%20😍-FFDD67.svg" alt="Gitmoji" />
  </a>
  <a href="https://semantic-release.gitbook.io/">
    <img src="https://img.shields.io/badge/semantic--release-gitmoji-e10079?logo=semantic-release" alt="semantic-release: gitmoji" />
</a>
</p>
<!-- markdownlint-restore -->

---

A ready-to-use GitHub repository template with linting, git hooks, automated
changelog, semantic versioning and automerged dependency updates. A new
repository created from it configures itself (branches, labels, rules) with
one workflow run and one command.

## Features

### Code Quality

- **Bun** - Fast and modern package manager
- **Husky** - Automated Git hooks
- **lint-staged** - Incremental linting on staged files
- **Markdownlint** - Markdown file validation
- **Yamllint** - YAML file validation
- **EditorConfig** - Consistent coding styles across editors

### Commit & Release

- **Gitmoji** - Commits with emojis (`✨ Add feature`)
- **Commitlint** - Validates commit messages (gitmoji or conventional)
- **Changelog** - Auto-generated from commits
- **Semantic Release** - Automated versioning and GitHub releases

### Dependency Management

- **Renovate** - Weekly dependency updates, automerged when CI passes
  (shared preset [`maxime-lenne/renovate-config`](https://github.com/maxime-lenne/renovate-config))
- **GitHub vulnerability alerts** - Read by Renovate to open security fixes

## Usage

### Commits

```bash
# Interactive gitmoji commit
bun run commit
```

Accepted formats:

- **Gitmoji**: `✨ Add new feature`
- **Conventional**: `feat(scope): Add new feature`

### Linting

```bash
bun run lint          # Lint all files
bun run lint:md       # Lint Markdown only
bun run lint:md:fix   # Auto-fix Markdown
bun run lint:yaml     # Lint YAML files
```

### GitHub Settings

```bash
bun run setup:github            # Apply .github/settings.yml
bun run setup:github --dry-run  # Preview changes
```

### Release

Releases are automated via GitHub Actions when a PR is merged into `main`:
the version is computed from the commits since the last release, then
`package.json`, `CHANGELOG.md`, a `🔖 Release vX.Y.Z` commit, the `vX.Y.Z` tag
and a GitHub Release (notes + `CHANGELOG.md`) are produced.

```bash
bun run release:dry   # Preview the next version and notes locally
```

#### Release Token (required)

The `🔖 Release` commit is pushed to `main`, which is protected. On a personal
account, neither `GITHUB_TOKEN` nor the GitHub Actions app can bypass that
protection: only a repository admin can. The workflow therefore needs a
`RELEASE_TOKEN` secret holding a personal access token (PAT) of yours.

1. **Create the PAT once**, reused by all your repositories
   ([GitHub → Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)):
   - fine-grained token: resource owner = your account, **All repositories**,
     repository permissions **Contents**, **Issues** and **Pull requests** in
     read and write
   - or a classic token with the `repo` scope
2. **Store it in the repository** (on each new repository):

   ```bash
   RELEASE_TOKEN=<pat> bun run setup:github --only=secrets
   # or: gh secret set RELEASE_TOKEN
   ```

   Keep the PAT in your password manager or shell environment: with
   `RELEASE_TOKEN` exported, a plain `bun run setup:github` stores it too.
3. **Renew it** before it expires, then store it again with the same command.

Without `RELEASE_TOKEN`, the release job logs a warning and fails when pushing
the release commit to the protected `main`.

#### After a Release: `develop` Is Re-synced Automatically

Rebase merges rewrite SHAs and the release adds a `🔖 Release` commit to `main`,
so `develop` must be rebased onto `main` before the next `develop → main` PR.
The release workflow does it right after the release (`bun run sync:develop`,
force push with lease, allowed on `develop` for that purpose). Commits already
on `main` are dropped, `develop` then contains the release commit.

On your machine afterwards:

```bash
# develop never holds local commits: align it on the remote
git switch develop
git fetch origin
git reset --hard origin/develop

# branch in progress: replay it on the new develop
git switch feature/my-branch
git rebase origin/develop
```

If the workflow reports a conflict (rare: `develop` changed the same lines as
the release commit), sync manually:

```bash
git switch develop && git fetch origin && git reset --hard origin/develop
bun run sync:develop        # rebase develop onto main, push with lease
```

### Git Hooks

Hooks are automatically configured via Husky:

- **pre-commit**: Runs lint-staged on modified files
- **commit-msg**: Validates commit message format
- **post-checkout**: Deletes local branches whose PR was merged (at most once
  per hour; `bun run clean:branches` to run it manually)

## Version Bumping

Versions are determined automatically by commit gitmoji or conventional type:

| Gitmoji | Conventional | Version Bump |
|---------|--------------|--------------|
| 💥 | `type!:`, `BREAKING CHANGE:` | Major |
| ✨ 🎉 | `feat` | Minor |
| 🐛 🚑️ 🩹 🔒️ ⚡️ ♻️ 🚀 ⬆️ ⬇️ | `fix`, `perf`, `refactor` | Patch |

Details and release notes sections: [`docs/TECHNICAL_GUIDE.md`](docs/TECHNICAL_GUIDE.md#semantic-release).

## Documentation

| File | Description |
|------|-------------|
| [`docs/AGENTS.md`](docs/AGENTS.md) | AI assistant guide and conventions |
| [`docs/CONVENTIONS.md`](docs/CONVENTIONS.md) | Code style and git conventions |
| [`docs/TECHNICAL_GUIDE.md`](docs/TECHNICAL_GUIDE.md) | Technical implementation details |
| [`docs/PROJECT_STRUCTURE.md`](docs/PROJECT_STRUCTURE.md) | Directory and file organization |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contribution guidelines |
| [`CHANGELOG.md`](CHANGELOG.md) | Version history |

## Configuration Files

| File | Purpose |
|------|---------|
| `.github/settings.yml` | GitHub settings: branches, merge rules, labels, protection |
| `renovate.json` | Renovate config (extends the shared preset) |
| `.gitmoji.json` | Gitmoji-cli settings |
| `release.config.js` | Semantic-release config |
| `.markdownlint.json` | Markdown linting rules |
| `.yamllint.yml` | YAML linting rules |
| `.editorconfig` | Editor settings |
| `commitlint.config.js` | Commit message validation |

## Customization

- **GitHub rules** (branches, reviews, required checks, labels): edit
  `.github/settings.yml`, then `bun run setup:github`
- **Dependency updates**: shared rules live in
  [`maxime-lenne/renovate-config`](https://github.com/maxime-lenne/renovate-config);
  project-specific rules go in `renovate.json`
- **Linting**: `.markdownlint.json`, `.yamllint.yml`, `commitlint.config.js`
- **Release**: `release.config.js`

## License

MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Maxime Lenne** - [maxime-lenne.fr](https://maxime-lenne.fr)

- GitHub: [@maxime-lenne](https://github.com/maxime-lenne)
- LinkedIn: [maximelenne](https://linkedin.com/in/maximelenne)
