# Android App Development Skill

A reusable workflow for Android app development with GitHub-first collaboration, reuse research, minimalist UI, purposeful interaction design, careful signing, and verifiable builds/releases.

## Contents

- `.agents/skills/android-app-development/SKILL.md`: the canonical reusable Skill.
- `templates/AGENTS.md`: starting point for project-specific rules.
- `templates/UI_SPEC.md`: starting point for a project's approved UI/interaction requirements.

## Use

1. Make this Skill available to the agent or coding environment that will perform the work.
2. At the start of an Android task, load `.agents/skills/android-app-development/SKILL.md`.
3. In the target app repository, read its `AGENTS.md`, `README.md`, UI spec, source/build files, and CI/release workflow.
4. Follow the mandatory GitHub reuse search and verification sequence in the Skill.

**Important:** creating or connecting this repository does not by itself make ChatGPT automatically load the Skill in every conversation. The execution environment must be configured to discover/load it.

## Maintenance

- Keep the canonical Skill here; do not create numbered copies or ZIP duplicates.
- Keep app-specific requirements in each app repository, not in this general Skill.
- Update this repository when a reusable workflow improvement is validated.
- Prefer small reviewed commits and avoid duplicating the full Skill into every app repo unless the environment requires a checked-in copy.

## License

Choose a license appropriate for your intended reuse before redistributing this repository.
