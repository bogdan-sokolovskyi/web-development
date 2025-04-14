# SEMANTIC BRANCH NAMES AND COMMIT MESSAGES IN GIT

### Better Branch Naming Convention

```{type}/{sprint}-{ticket}-{short-description}```

Branch: 
- `fix/s61-PLAT-0001-header-overflow`
- `feat/s62-PLAT-1234-dark-mode-toggle`

Why?

fix/ or feat/ – Clearly indicates the type of work (bug fix, feature, chore, etc.).
* s61 – Short for Sprint 61 (avoids long names).
* PLAT-0001 – Keeps the ticket reference.
* header-overflow – Short description for quick recognition.
This is cleaner and works well with automation tools (like Jira integrations).

See how a minor change to your commit message style can make you a better programmer.


#### Commit Message Header

```
{type}({scope}): {ticket} {subject}
  │       │          |         └─⫸ Subject (Mandatory): Summary in present tense. Not capitalized. No period at the end.
  │       │          └─⫸ Ticket (Recommended): Include the ticket ID (e.g., PLAT-0001) for traceability.
  │       │
  │       └─⫸ Scope (Optional): animations|bazel|benchpress|common|compiler|compiler-cli|core|
  │                          elements|forms|http|language-service|localize|platform-browser|
  │                          platform-browser-dynamic|platform-server|router|service-worker|
  │                          upgrade|zone.js|packaging|changelog|docs-infra|migrations|
  │                          devtools
  │
  └─⫸ Type (Mandatory): build|ci|docs|feat|fix|perf|refactor|test
```

a. Type (Mandatory)
- Type	Use Case
- feat	New feature
- fix	Bug fix
- docs	Documentation changes
- style	UI/Cosmetic (e.g., CSS)
- refactor	Code restructuring (no behavior change)
- test	Test-related changes
- chore	Build/config tasks (e.g., npm, Git)

b. Scope (Optional)
- Module/component affected (e.g., (header), (auth), (config)).

c. Ticket (Recommended)
- Include the ticket ID (e.g., PLAT-0001) for traceability.

d. Subject (Mandatory)
- Imperative tense ("fix" not "fixed" or "fixes").

Short (≤50 chars), clear summary.


##### Type

Must be one of the following:

- `feat`: new feature for the user, not a new feature for build script
- `fix`: bug fix for the user, not a fix to a build script
- `docs`: changes to the documentation
- `style`: formatting, missing semi colons, etc; no production code change
- `refactor`: refactoring production code, eg. renaming a variable
- `test`: adding missing tests, refactoring tests; no production code change
- `chore`: updating grunt tasks etc; no production code change
-  `perf`: a code change that improves performance
-  `build`: changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
-  `ci`: changes to our CI configuration files and scripts (examples: CircleCi, SauceLabs)
-  `revert`: undo previous commits


##### Scope
The scope should be the name of the npm package affected (as perceived by the person reading the changelog generated from commit messages).

The following is the list of supported scopes:

* `animations`
* `bazel`
* `benchpress`
* `common`
* `compiler`
* `compiler-cli`
* `core`
* `elements`
* `forms`
* `http`
* `language-service`
* `localize`
* `platform-browser`
* `platform-browser-dynamic`
* `platform-server`
* `router`
* `service-worker`
* `upgrade`
* `zone.js`

There are currently a few exceptions to the "use package name" rule:

* `packaging`: used for changes that change the npm package layout in all of our packages, e.g. public path changes, package.json changes done to all packages, d.ts file/format changes, changes to bundles, etc.

* `changelog`: used for updating the release notes in CHANGELOG.md

* `dev-infra`: used for dev-infra related changes within the directories /scripts and /tools

* `docs-infra`: used for docs-app (angular.io) related changes within the /aio directory of the repo

* `migrations`: used for changes to the `ng update` migrations.

* `devtools`: used for changes in the [browser extension](./devtools/README.md).

* none/empty string: useful for `test` and `refactor` changes that are done across all packages (e.g. `test: add missing unit tests`) and for docs changes that are not related to a specific package (e.g. `docs: fix typo in tutorial`).


##### Summary

Use the summary field to provide a succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize the first letter
* no dot (.) at the end


## Example

#### NEW FEATURE
Branch: 
- `fix/s61-PLAT-0001`
- `fix/s61-PLAT-0002-header-overflow`
- `feat/s62-PLAT-1234-dark-mode-toggle`

Commit Message Structure:

```{type}({scope}): {ticket} {subject}```
- `fix(auth): PLAT-0001 prevent null token crash`
- `style(buttons): PLAT-0002 increase contrast for accessibility`

#### BUGFIX
Branch: 
- `fix/s61-PLAT-101`

Commit: 
- `fix: reduce spacing between link label and icon`
- `fix(icon-link): reduce spacing between link label and icon`



References:

- https://dev-tips.com/git/semantic-branch-names-and-commit-messages-in-git
- https://www.conventionalcommits.org/
- http://karma-runner.github.io/1.0/dev/git-commit-msg.html
