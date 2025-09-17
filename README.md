# Taplo Formatting Bug Reproduction

This repository demonstrates an inconsistency in taplo formatting between local environments and CI.

## The Issue

When running `taplo format` (via pre-commit) locally vs in CI, different formatting results are produced for the same TOML files, even with identical taplo configurations.

## Files

- `.taplo.toml` - Taplo configuration with 4-space indentation
- `pyproject.toml` - Sample TOML file that triggers the formatting difference
- `.pre-commit-config.yaml` - Pre-commit configuration using taplo v0.9.3
- `.github/workflows/pre-commit.yml` - GitHub Actions workflow that reproduces the issue

## Expected Behavior

The same formatting should be applied regardless of environment.

## Actual Behavior

CI shows formatting differences that are not present when running locally.

## To Reproduce

1. Clone this repository
2. Run `pre-commit run taplo-format --files pyproject.toml` locally
3. Create a pull request and observe the CI behavior
4. Compare the diff shown in CI vs local behavior
