# Contributing to Dragonfly

We're thrilled that you're interested in hacking on Dragonfly! We welcome and encourage all contributions. Here’s a guide to help you get started.

## Topics

- [Reporting Security Issues](#reporting-security-issues)
- [Reporting General Issues](#reporting-general-issues)
- [Contributing Code and Docs](#contributing-code-and-docs)
- [Getting Involved](#getting-involved)
- [Becoming a Dragonfly Member](#becoming-a-dragonfly-member)

## Reporting Security Issues

We take security very seriously. To protect our community, we ask that you don't disclose security vulnerabilities publicly. If you discover a security issue in Dragonfly, please don't open a public issue or discuss it in public forums. Instead, send us a private email at [dragonfly-maintainers@googlegroups.com](mailto:dragonfly-maintainers@googlegroups.com) to report it.

## Reporting General Issues

We consider every Dragonfly user a valuable contributor. After trying out Dragonfly, you might have some feedback for us. Feel free to open an issue on GitHub by clicking [NEW ISSUE](https://github.com/dragonflyoss/dragonfly/issues/new).

Because we're a distributed team, we really appreciate **well-written**, **detailed**, and **clear** issue reports. To keep our communication efficient, please search existing issues to see if your problem has already been reported. If it has, please add your comments to the existing issue instead of creating a new one.

To help standardize our issue reports, we've created an [ISSUE TEMPLATE](./.github/ISSUE_TEMPLATE) with options for questions, bug reports, and feature requests. Please be sure to follow the template and fill in all the required fields.

You can open an issue for many reasons, including:

- Bug reports
- Feature requests
- Performance issues
- Feature proposals
- Feature design discussions
- Help wanted
- Incomplete documentation
- Test improvements
- Any questions about the project

Also, a friendly reminder: when you file a new issue, please make sure to remove any sensitive data from your post. This includes things like passwords, secret keys, network locations, and private business information.

## Contributing Code and Docs

Any action that makes Dragonfly better is encouraged! On GitHub, all improvements are made through Pull Requests (PRs).

- Find a typo? Fix it!
- Find a bug? Squash it!
- See redundant code? Remove it!
- Notice missing test cases? Add them!
- Have an idea to enhance a feature? Don't hesitate!
- Think the code is unclear? Add comments to clarify it!
- Find some code that could be better? Refactor it!
- Want to improve our documentation? We'd love that!
- Spot an error in the docs? Correct it!
- ...and so much more!

We can't list everything, but just remember this one principle:

> WE ARE EXCITED TO SEE ANY PR FROM YOU.

Before you submit a PR, please take a moment to review our PR guidelines.

- [Workspace Preparation](#workspace-preparation)
- [Branching Strategy](#branching-strategy)
- [Commit Rules](#commit-rules)
- [PR Description](#pr-description)
- [Development Environment](#development-environment)
- [Go Dependency Management](#go-dependency-management)

### Workspace Preparation

To submit a PR, you'll need a GitHub account. Once you have one, follow these steps to get your workspace ready:

1. **FORK** Dragonfly to your own repository.

   To do this, just click the "Fork" button in the top-right corner of the [dragonflyoss/dragonfly](https://github.com/dragonflyoss/dragonfly) main page. This will create a copy of the repository under your own account at `https://github.com/<your-username>/dragonfly`.

2. **CLONE** your forked repository to your local machine.

   Use `git clone --recurse-submodules https://github.com/<your-username>/dragonfly.git` to clone the repository locally. Now you can create new branches and make your changes.

3. **Set the remote upstream** to `https://github.com/dragonflyoss/dragonfly.git`.

   Run these two commands:

   ```bash
   git remote add upstream https://github.com/dragonflyoss/dragonfly.git
   git remote set-url --push upstream no-pushing
   ```

   With this remote setup, your git remote configuration should look like this:

   ```bash
   $ git remote -v
   origin     https://github.com/<your-username>/dragonfly.git (fetch)
   origin     https://github.com/<your-username>/dragonfly.git (push)
   upstream   https://github.com/dragonflyoss/dragonfly.git (fetch)
   upstream   no-pushing (push)
   ```

   This setup makes it easy to keep your local branches in sync with the main project.

4. **Create a branch** to add a new feature or fix an issue.

   First, update your local working directory:

   ```bash
   cd dragonfly
   git fetch upstream
   git checkout main
   git rebase upstream/main
   ```

   Then, create a new branch for your work:

   ```bash
   git checkout -b <new-branch>
   ```

   Now you can make your changes on the `new-branch`, then build and test your code.

### Branching Strategy

For now, we assume all contributions made via pull requests are intended for the `main` branch of Dragonfly. Understanding our branching strategy will help you contribute more effectively.

As a contributor, please remember that all pull requests should target the `main` branch. However, the Dragonfly project also uses other types of branches, such as release candidate (rc) branches, release branches, and backport branches.

Before a new version is officially released, we create a release candidate (rc) branch. This branch undergoes more rigorous testing than the `main` branch.

When we're ready to release a new version, we create a release branch just before tagging. After the version is tagged, we delete the release branch.

When we need to backport fixes to an existing released version, we create backport branches. These backported changes will be reflected in the PATCH number of our [SemVer](http://semver.org/) versioning (MAJOR.MINOR.PATCH).

### Commit Rules

In Dragonfly, we take two rules very seriously when it comes to commits:

- [Commit Message](#commit-message)
- [Commit Content](#commit-content)

#### Commit Message

A clear commit message helps reviewers understand the purpose of your PR and speeds up the code review process. We encourage you to use **explicit** and descriptive commit messages. We follow a conventional commit format:

- `feat`: A new feature (e.g., "feat: add support for sorted results").
- `fix`: A bug fix (e.g., "fix: prevent panic when input is nil").
- `docs`: Changes to documentation (e.g., "docs: add guide for storage installation").
- `style`: Code style changes (e.g., "style: format Constants.java").
- `refactor`: Code refactoring (e.g., "refactor: simplify code for readability").
- `test`: Adding or improving tests (e.g., "test: add unit test for InsertIntoArray").
- `chore`: Maintenance changes (e.g., "chore: integrate travis-ci").

On the other hand, we discourage ambiguous commit messages like:

- ~~fix bug~~
- ~~update~~
- ~~add doc~~

#### Commit Content

The content of a commit should include all the changes necessary for a complete and reviewable unit of work. Ideally, a single commit should be self-contained and pass CI on its own. Here are two simple rules to keep in mind:

- Avoid making very large changes in a single commit.
- Ensure each commit is complete and can be reviewed independently.

No matter the commit message or content, we place a strong emphasis on thorough code review.

### PR Description

A Pull Request (PR) is the only way to make changes to the Dragonfly project files. To help reviewers understand your contribution, please provide a detailed PR description. We encourage you to follow our [PR template](./.github/PULL_REQUEST_TEMPLATE.md) when creating your pull request.

### Development Environment

To ensure a smooth development process, all contributors should use the same versions of our development tools. Here are the dependencies and their required versions:

- **Go**: Check the `go.mod` file for the required version.
- **misspell**: latest
- **shellCheck**: latest
- **Docker**: latest

When developing locally, you can use the subcommands in our `Makefile` to build and check your code. We use Docker to build Dragonfly, which helps minimize environment-related issues.

### Go Dependency Management

The Dragonfly project uses [Go modules](https://golang.org/cmd/go/#hdr-Modules__module_versions__and_more) to manage external packages. You can find the required dependency versions in the `go.mod` file.

To add or update a dependency, use the `go get` command:

```bash
# Get the latest tagged release
go get example.com/some/module/pkg

# Get a specific version
go get example.com/some/module/pkg@vX.Y.Z
```

After updating dependencies, tidy up the `go.mod` and `go.sum` files:

```bash
go mod tidy
```

You'll need to commit the changes to `go.mod` and `go.sum` before submitting your pull request.

## Getting Involved

There are many ways to get involved and help the Dragonfly community. Whether you're a developer, a user, or just an enthusiast, we'd love to have you!

- **Join the discussion**: Participate in our community channels, ask questions, and share your ideas.
- **Help others**: Answer questions from other users and help them get started with Dragonfly.
- **Spread the word**: Tell your friends and colleagues about Dragonfly, write a blog post, or share your experience on social media.

## Becoming a Dragonfly Member

If you're a regular contributor and want to take on a more formal role in the community, you can become a Dragonfly Member. Members have additional privileges and responsibilities, and they play a key role in shaping the future of the project. To learn more about becoming a member, check out our [Contributor Ladder](COMMUNITY_LADDER.md).
