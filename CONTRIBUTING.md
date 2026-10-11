# Contributing

Thanks for taking an interest. These are personal projects, maintained in
spare time, so reviews may take a while. Small, focused pull requests are the
easiest to review.

A repository with its own `CONTRIBUTING.md` (for example, `driveway-counter`)
has project-specific notes that take precedence over this file.

## Getting started

1. Fork the repository and clone your fork.
2. Create a branch: `git checkout -b fix/short-description`.
3. Follow the repository's README for setup, running and testing.
4. Open a pull request against `main`.

## Testing

Several projects run on specific hardware (Raspberry Pi, Hailo, LattePanda,
a K3s cluster) or against cloud accounts, so not every change can be tested
everywhere. Say what you tested, and on what, in the PR description. A clearly
described untested change is more useful than a silently untested one.

Where a repository has tests (`pytest` for Python, `npm test` for the
Cloudflare Workers), run them before opening the PR.

## Code style

Match the style of the surrounding code. For Python, `black` and `ruff` keep
diffs small if you have them; for TypeScript, use the repository's Prettier
config. Comments should explain *why*, not *what*.

## Commit messages

[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/):

```
type(scope): short summary

Body explaining what changed and why, wrapped at 72 characters.
```

Types: `feat`, `fix`, `docs`, `refactor`, `perf`, `test`, `chore`.

## Pull requests

- One purpose per PR
- Describe what you tested and on what
- Update the README or `docs/` if behavior or configuration changes
- Add any new environment variable to `.env.example`
- Never commit secrets, tokens or real `.env` files

## Issues

- **Bugs:** steps to reproduce, expected and actual behavior, relevant logs
- **Features:** the use case, and any alternatives you considered

Security issues should not be reported in public issues. See
[SECURITY.md](SECURITY.md).
