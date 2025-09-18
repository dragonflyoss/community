# Repository Guidelines

This document describes the scope and lifecycle of repositories in the [Dragonfly](https://github.com/dragonflyoss) project. You can find all repositories by scope in [REPOSITORIES.md](REPOSITORIES.md).

And this document is inspired from the [Cilium project's repository guidelines](https://github.com/cilium/community/blob/main/REPOSITORY-GUIDELINES.md). We appreciate the [Cilium community](https://github.com/cilium/community) for their excellent work.

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Repositories Scope](#repositories-scope)
  - [`Core` Repositories](#core-repositories)
  - [`Ecosystem` Repositories](#ecosystem-repositories)
  - [`Historical` Repositories](#historical-repositories)
- [Repositories Lifecycle](#repositories-lifecycle)
  - [Add a Repository](#add-a-repository)
- [Change of Repository Scope](#change-of-repository-scope)

## Repositories Scope

Each repository in the Dragonfly GitHub organization is assigned one of three scopes: [`Core`](#core-repositories), [`Ecosystem`](#ecosystem-repositories), or [`Historical`](#historical-repositories). The scope helps explain the role and responsibility of each repository in the project.

### `Core` Repositories

Core repositories are the most important part of the Dragonfly project. They provide the main and essential features. These repositories are the most active and are used most often by users.

You can find all `Core` repositories in [REPOSITORIES.md](REPOSITORIES.md#core-scope).

### `Ecosystem` Repositories

Ecosystem repositories are the most numerous. This scope is broad on purpose. These repositories have different levels of maturity and activity. Users should carefully check before using any end-user-facing repositories in this scope.

You can find all `Ecosystem` repositories in [REPOSITORIES.md](REPOSITORIES.md#ecosystem-scope).

### `Historical` Repositories

Historical repositories are considered deprecated and are no longer maintained. They are usually archived as read-only. Users are not advised to use these repositories.

Repositories that have not been active for a long time can be proposed for archiving. The process is the same as other [scope changes](#change-of-repository-scope). You can find all `Historical` repositories in [REPOSITORIES.md](./REPOSITORIES.md#historical-repositories).

## Repositories Lifecycle

### Add a Repository

New repositories can be proposed by Maintainers through creating an issue in the community repository. The proposal process must follow the decision-making rules in [COMMUNITY_MEMBERSHIP.md](./COMMUNITY_MEMBERSHIP.md#how-we-make-decisions). This includes creating new repositories, accepting donated repositories, or creating forks from existing repositories.

Once approved through the community voting process, the new repository must be added to the appropriate list in [REPOSITORIES.md](./REPOSITORIES.md).

## Change of Repository Scope

If a repository's activity level or purpose changes significantly, a scope change can be proposed by any Maintainer through creating an issue in the community repository. The change must be approved following the decision-making process described in [COMMUNITY_MEMBERSHIP.md](./COMMUNITY_MEMBERSHIP.md#how-we-make-decisions).

All repository scope changes should be documented in:

- The community meeting notes
- The original proposal issue
- Updated [REPOSITORIES.md](REPOSITORIES.md) file
