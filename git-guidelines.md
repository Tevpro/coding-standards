
### Commit Message Guidelines

- We utilize [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) and [commitlint](https://commitlint.js.org/#/) to help ensure commit message guidelines are met.
- This helps ensure easy to read commit history and allows for us to auto generate a changelog.

#### Coding Rules

To ensure consistency throughout the source code, keep these rules in mind as you are working:

- All features or bug fixes **must be tested** by one or more specs (unit-tests).
- All public API methods **must be documented**.
- We follow [Google's JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html), but wrap all code at **100 characters**.

#### Commit Message Format

_This specification is inspired by the [Angular commit-message-format](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit)._

We have very precise rules over how our Git commit messages must be formatted.
This format leads to **easier to read commit history**.

Each commit message consists of a **header**, a **body**, and a **footer**.

```plaintext
<header>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The `header` is mandatory and must conform to the [Commit Message Header](./README.md#commit-header) format.

The `body` is optional for all commits.
When the body is present it must be at least 20 characters long and must conform to the [Commit Message Body](./README.md#commit-body) format.

The `footer` is optional. The [Commit Message Footer](./README.md#commit-footer) format describes what the footer is used for and the structure it must have.

#### Commit Message Header<a name="commit-header"></a>

```plaintext
<type>(<scope>): <short summary>
  │       │             │
  │       │             └─⫸ Summary in present tense. Not capitalized. No period at the end.
  │       │
  │       └─⫸ Commit Scope: crane|load|documents|account|auth|core|analytics|api|
  │
  └─⫸ Commit Type: build|ci|docs|feat|fix|perf|refactor|test
```

The `<type>` and `<summary>` fields are mandatory, the `(<scope>)` field is optional.

#### Type

Must be one of the following:

- **build**: Changes that affect the build system or external dependencies (example scopes: npm, config)
- **ci**: Changes to our CI configuration files and scripts (examples: Azure DevOps, GitHub)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **test**: Adding missing tests or correcting existing tests
- **revert**: Adding missing tests or correcting existing tests

#### Scope

The scope should be the name of the part of the application that was affected (as perceived by the person reading the changelog generated from commit messages).

The following is the list of example scopes:

- `crane`
- `load`
- `documents`
- `account`
- `auth`
- `core`
- `analytics`
- `api`

There are currently a few exceptions to the supported scope rule:

- `changelog`: used for updating the release notes in CHANGELOG.md

- `devops`: used for devops related changes

- none/empty string: useful for `test` and `refactor` changes that are done across all packages (e.g. `test: add missing unit tests`) and for docs changes that are not related to a specific package (e.g. `docs: fix typo`).

#### Summary

Use the summary field to provide a succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- don't capitalize the first letter
- no dot (.) at the end

#### Commit Message Body<a name="commit-body"></a>

Just as in the summary, use the imperative, present tense: "fix" not "fixed" nor "fixes".

Explain the motivation for the change in the commit message body. This commit message should explain _why_ you are making the change.
You can include a comparison of the previous behavior with the new behavior in order to illustrate the impact of the change.

#### Commit Message Footer<a name="commit-footer"></a>

The footer can contain information about breaking changes and deprecations and is also the place to reference GitHub issues, Jira tickets, and other PRs that this commit closes or is related to.
For example:

```plaintext
BREAKING CHANGE: <breaking change summary>
<BLANK LINE>
<breaking change description + migration instructions>
<BLANK LINE>
<BLANK LINE>
Fixes #<issue number>
```

or

```plaintext
DEPRECATED: <what is deprecated>
<BLANK LINE>
<deprecation description + recommended update path>
<BLANK LINE>
<BLANK LINE>
Closes #<pr number>
```

Breaking Change section should start with the phrase "BREAKING CHANGE: " followed by a summary of the breaking change, a blank line, and a detailed description of the breaking change that also includes migration instructions.

Similarly, a Deprecation section should start with "DEPRECATED: " followed by a short description of what is deprecated, a blank line, and a detailed description of the deprecation that also mentions the recommended update path.

#### Revert commits

If the commit reverts a previous commit, it should begin with `revert:`, followed by the header of the reverted commit.

The content of the commit message body should contain:

- information about the SHA of the commit being reverted in the following format: `This reverts commit <SHA>`,
- a clear description of the reason for reverting the commit message.
