# Project-specific agent instructions

## Product scope
- Describe this app's purpose and explicitly list in-scope and out-of-scope behavior.
- Document data-storage, privacy, network, account, analytics, advertising, and encryption requirements.
- Do not infer new product requirements; ask when a material ambiguity blocks implementation.

## Design specification
- Link or refer to the app's approved `UI_SPEC.md`.
- Preserve approved visual concepts and interaction patterns.
- Prefer purposeful motion and ensure it does not compromise touch handling, readability, accessibility, or small-screen layouts.

## Repository workflow
- Follow `.agents/skills/android-app-development/SKILL.md` for the general Android workflow when it is present and discoverable.
- Before editing, inspect the current source, Gradle configuration, Git history, and existing GitHub Actions workflows.
- Keep changes focused and preserve existing behavior outside the requested scope.
- Never commit credentials, signing keys, keystores, API tokens, `local.properties`, or private user data.
- Do not claim a build, release, or device test succeeded without verifying the corresponding evidence.

## App-specific constraints
- Add only requirements that are specific to this app. Do not copy generic workflow instructions here.
