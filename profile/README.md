# Frequency Labs

Frequency Labs develops technology that helps amateur musicians use AI to
generate sheet music and tabs from their art.

## Architecture Overview

As of the 2026-06-14 audit, the only repository visible to this automation in
the FrequencyLabs GitHub organization is `.github`, the special GitHub profile
repository that renders this organization-level README. No application service,
frontend, library, data pipeline, infrastructure, or internal tooling
repositories were visible through `gh repo list`, the GitHub repositories API,
or repository search scoped to `FrequencyLabsOrg`.

That means the public codebase currently exposes the organization's product
direction, but not the implementation architecture behind AI-generated sheet
music and tabs. From the available repository, there are no documented service
boundaries, runtime components, data flows, shared libraries, deployment
pipelines, or cross-repository imports to inspect. If production systems
exist, they are either private, outside this GitHub organization, archived in a
way not returned by the API, or otherwise unavailable to this audit token.

The visible technology footprint is intentionally minimal. The `.github`
repository contains Markdown documentation only: no `package.json`,
`pyproject.toml`, `go.mod`, GitHub Actions workflows, Dockerfiles, or
Compose files. A returning engineer should therefore avoid inferring that
Frequency Labs lacks application code; the safer conclusion is that this
organization profile repo is not enough to reconstruct the runtime stack.

The surprising part of the current organization shape is the gap between the
mission statement and the visible implementation surface. Engineers rejoining
after time away should first confirm whether repository access, repository
ownership, or organization visibility changed before using this README as a
complete technical map. The only concrete dependency relationship visible today
is GitHub's own dependency on `profile/README.md` to render the organization
landing page.

## Repository Index

### Organization Documentation

**[.github](https://github.com/FrequencyLabsOrg/.github)** · `Markdown` ·
`[STALE]`  
Hosts the organization profile README for Frequency Labs. It does not call or
ship application code; GitHub reads `profile/README.md` to render the org
landing page, and no package manifests, CI workflows, or Docker configs are
present.

### Application, Service, Frontend, Library, And Infrastructure Repositories

No repositories in these categories were visible during this audit. If these
repositories exist, they could not be inspected for language, framework,
runtime, CI/CD, Docker setup, activity, or cross-repository dependencies from
the available GitHub organization metadata.

## If You've Been Away For A While, Start Here

- Start with `.github`, because it is the only visible repository and the only
  current source for organization-level documentation.
- Confirm whether you should have access to private product repositories before
  treating this guide as a complete architecture inventory.
- Check whether service, frontend, data pipeline, or infrastructure repos moved
  to another organization, were renamed, or were archived outside the visible
  repository list.
- Treat `.github` as stale: its last visible commit was on 2025-05-03, more
  than six months before this 2026-06-14 refresh.
- Expect no local setup path from the visible repo; there are no package
  manifests, workflows, Dockerfiles, or Compose files to bootstrap.
- If new repositories are restored or made visible, update this README with
  their actual callers, dependencies, runtimes, and CI/CD entry points before
  relying on it for onboarding.
