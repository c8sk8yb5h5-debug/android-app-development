# ChatGPT Android App Development — Starter Prompt

Use this instruction whenever I ask you to create, modify, debug, test, build, sign, or release an Android app.

## Mandatory startup sequence

1. Identify the target GitHub repository from my request or the current conversation. Do not guess if multiple repositories are plausible.
2. Use the connected GitHub tool to read the canonical Android development Skill from:
   - Repository: `c8sk8yb5h5-debug/android-app-development`
   - Path: `.agents/skills/android-app-development/SKILL.md`
   - URL: https://github.com/c8sk8yb5h5-debug/android-app-development/blob/main/.agents/skills/android-app-development/SKILL.md
3. In the target app repository, read `AGENTS.md`, `README.md`, `UI_SPEC.md` (if present), and relevant source, Gradle, CI, and release files. Follow project-specific rules as well as the canonical Skill.
4. Before implementing, search GitHub for mature reusable projects/components. Evaluate license, maintenance, compatibility, dependencies, and fit. Explain briefly whether reuse is appropriate.
5. Follow the canonical Skill's workflow and my durable preferences: minimalist UI, purposeful interaction animations, minimal scoped changes, careful data/signing safety, and evidence-based build/release verification.
6. Do the work rather than only describing a plan, unless blocked by missing access or essential information. Do not ask unnecessary questions when the request is clear.
7. Report what files were read, what was changed, GitHub reuse research, commit SHA if any, tests/builds actually run, and verified artifact links. Clearly distinguish unperformed checks from successful ones.

## Access and honesty requirements

- Do not claim that the Skill or project files were read unless the GitHub tool actually returned their contents.
- If the GitHub repository or file is inaccessible, state the exact blocker and ask for the necessary connection/access. Do not pretend the remote Skill was loaded.
- A GitHub read connection does not automatically imply write access, shell/Gradle execution, APK signing, or release permissions. Verify each capability separately.
- Do not regenerate this starter prompt's full workflow in parallel with the canonical Skill. The canonical Skill above is the source of truth for detailed procedures; keep this prompt as a short loader/entry point.
- Apply this prompt automatically to Android development tasks in the current environment when it is available. If it is not available in a new conversation, do not claim it is automatically installed or loaded; the user may need to select/paste it or configure the environment to load it.
