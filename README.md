# Conventional commit introduction
## Semantic Versioning
1. `MAJOR`: version when you make incompatible API changes. 
2. `MINOR`: version when you add functionality in a backwards compatible manner. 
3. `PATCH`: version when you make backwards compatible bug fixes.  
## Conventional Commits
```
<type>[optional scope]: <description>
[optional body]
[optional footer(s)]
```
1. `fix`: A bug fix -> `PATCH`
2. `feat`: A new feature -> `MINOR`
3. `BREAKING CHANGE`: a breaking API change -> `MAJOR` ()
4. `build`: Changes that affect the build system or external dependencies
5. `docs`: Documentation only changes
6. `perf`: A code change that improves performance
7. `refactor`: A code change that neither fixes a bug nor adds a feature
8. `ci`: Changes to our CI configuration files and scripts
9. `test`: Adding missing tests or correcting existing tests
10. `style`: Changes that do not affect the meaning of the code
#### BREAKING CHANGE
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```
#### Commit message without body
`feat(lang): add polish language`
#### Commit message with multi-paragraph body and multiple footers
```
fix: correct minor typos in code

see the issue for details

on typos fixed.

Reviewed-by: Z
Refs #133
```
## Format check in cam-app
* Follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
* Commit title should be all lowercase, except when referencing tokens.
* Commit title should be written in the imperative, e.g. "fix", not "fixed" or "fixes".
* Commit title length should not exceed 50 characters.
* Use asterisks for bullet points in commit description.
* Scopes (when applicable) should be all lowercase, e.g. `feat(mini mode):`, `fix(profile sync):`
* Keep commits small.
* Each commit should contain one logical unit of change. Avoid unrelated changes in a commit.
#### type-enum
```
foo: some message // fails
fix: some message // passes
```
#### type-case
```
FIX: some message // fails
fix: some message // passes
```
#### type-empty
```
sunny // fails
fix: some message // passes
```
#### scope case
```
fix(SCOPE): some message // fails
fix(scope): some message // passes
```
#### subject-case
```
fix(SCOPE): Some message // fails
fix(SCOPE): Some Message // fails
fix(SCOPE): SomeMessage // fails
fix(SCOPE): SOMEMESSAGE // fails
fix(scope): some message // passes
fix(scope): some Message // passes
```
#### subject-empty
```
fix: // fails
fix: some message // passes
```
#### subject-full-stop
```
fix: some message. //fails
fix: some message // passes
```
#### max-length
```
fix: some message that is way too long and breaks the line max-length by several characters // fails
fix: some message // passes
```
