# Profile Repository Design

> **Scope**: Structure and conventions for the `NWarila/NWarila` GitHub profile
> repository.
>
> **Audience**: Anyone reviewing this repo who wants to understand why it is
> structured the way it is.

## Purpose

This is the special GitHub profile repository whose `README.md` renders on the
public [github.com/NWarila](https://github.com/NWarila) profile page. It
serves as a professional landing page for recruiters, hiring managers, and
collaborators in the cleared defense DevSecOps space.

## Architecture

This repo is a lean publishing surface. It contains no source code, no build
tooling, and no editor configuration. The only content is the profile README,
synced resume artifacts, and the automation that keeps them current.

### Resume Sync

The resume builder lives in a separate private repository and publishes
artifacts via GitHub Releases. A workflow in this repo
(`resume-sync.yml`) checks for new releases, downloads the built artifacts
(RESUME.md, .docx files), and opens a pull request. This keeps the build
system private while publishing the outputs publicly.

### CI

The CI workflow (`ci.yml`) runs on every push and pull request:

- **Markdownlint**: validates all Markdown files against a shared
  configuration that matches the org-level config in `NWarila/.github`.
- **Link check**: verifies all URLs in Markdown files resolve, excluding
  LinkedIn (which blocks automated requests).

The CI badge in the README provides a live quality signal.

## Inheritance

Community health files (code of conduct, contributing guide, security policy,
support routing, issue templates, PR template, funding config) are inherited
from [`NWarila/.github`](https://github.com/NWarila/.github). This repo
intentionally does not duplicate them. See that repo's
[`DESIGN.md`](https://github.com/NWarila/.github/blob/main/DESIGN.md) for
governance rationale.

## File Hygiene

- **Deny-all `.gitignore`**: every tracked file is explicitly named. The only
  wildcard exception is `*.docx` for synced resume artifacts.
- **Self-documenting config**: every rule in `.gitignore` and `.gitattributes`
  has a comment explaining why it exists, matching the convention established
  in `NWarila/.github`.
- **LF normalization**: all text files are normalized to LF via
  `.gitattributes` for stable diffs across platforms.

## What Is Intentionally Absent

| Omission | Reason |
|----------|--------|
| `.vscode/` | No source code to edit in this repo |
| `pyproject.toml`, `Makefile` | No build tooling; resume is built elsewhere |
| Community health files | Inherited from `NWarila/.github` |
| GitHub stats widgets | Would misrepresent a career that is mostly classified |
| Badge walls | Low signal; one CI badge provides more credibility than twenty decorative shields |
| `CHANGELOG.md` | No value for a profile repo with squashed history |
