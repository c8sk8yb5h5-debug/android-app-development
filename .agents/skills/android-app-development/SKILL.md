---
name: android-app-development
description: Develop, modify, test, debug, and release Android apps using GitHub-first workflow, reusable-project research, minimal UI, and purposeful interaction design. Use whenever asked to build or modify an Android app, implement UI interactions, fix bugs, manage an Android GitHub repository, build an APK, or configure release signing.
---

# Android App Development Skill

Use this workflow whenever the user asks to develop, modify, test, debug, or release an Android app. Do the work rather than only proposing a plan, unless blocked by missing access or essential information.

## 1. Mandatory entry checks

1. Identify the active repository and branch, latest commit SHA, package ID, language/framework, build system, current version, and release process. Never guess repository names, paths, branch names, workflow names, run IDs, or asset URLs.
2. Read the repository's `AGENTS.md`, this Skill, `README.md`, applicable UI/design specs, relevant source/build files, and existing CI/release workflows before editing.
3. **Search GitHub for mature reusable projects before implementing a feature.** Check license, maintenance/activity, compatibility, dependencies, architecture, and behavior fit. Prefer appropriate reuse over rebuilding from scratch, but never copy blindly.
4. Extract the user's requested outcome and explicit constraints. Make the smallest scoped change and preserve behavior outside the requested scope.
5. If essential information or access is missing, state the specific blocker. Never claim an action succeeded without evidence.

## 2. GitHub-first workflow

When a repository is connected or the user asks to use GitHub, treat it as the source of truth. Do not treat each request as a fresh project or repeatedly generate unrelated source ZIPs.

1. Locate and inspect the repository, current files, recent commits, branches, Actions workflows, issues, and latest release as relevant.
2. Reuse the existing codebase. Preserve history, package ID, architecture, local data, signing configuration, versioning, and working behavior unless the user explicitly requests a change.
3. Search GitHub for reusable implementations before coding. Compare fit and license; do not add dependencies or broad refactors without a clear reason.
4. Make a focused change, then review the complete diff for compile-sensitive imports/configuration, stale or duplicate code, persistence/migration regressions, permissions, gesture conflicts, animation clipping, accessibility, and unintended network behavior.
5. Use a focused branch/commit when supported. Never force-push, rewrite history, delete branches, change repository visibility, or modify secrets/settings without explicit authorization. Never commit credentials, signing keys, keystores, `local.properties`, API tokens, or private user data.
6. Inspect and reuse existing Gradle and GitHub Actions workflows. If a build workflow is needed, keep it minimal: configure the required JDK/Android SDK, use the project's Gradle wrapper, run available tests, assemble the requested APK, and upload a real artifact. Do not add duplicate or racing release workflows.
7. Tie every build result to the exact source commit and Actions run. Wait for completion, inspect conclusions/logs, and verify the artifact or release asset exists and is downloadable.
8. Diagnose failures from actual logs, make a scoped fix, and verify the next run. Do not trigger duplicate builds while an equivalent run is active.
9. Report repository, branch/commit, exact checks performed, build status, and artifact/release links when available. Clearly state what has not been tested.

## 3. UI and interaction preferences

Treat these as durable user preferences unless the user explicitly overrides them. The project's own approved design spec takes precedence over generic preferences.

- **Minimalist UI:** clear hierarchy, breathing room, restrained color, few elements, concise labels. Avoid excessive explanatory copy, decorative blocks, nested cards, and unnecessary borders.
- **Purposeful interaction:** use intentional micro-interactions when they help, such as spring settling, subtle compression/stretch, shared motion, liquid fill, and smooth easing. Motion must not interfere with touch, scrolling, readability, accessibility, or performance.
- Prefer compact capsule controls and coherent radii, shadows, and transparency where appropriate.
- Use native platform/Compose animation, Canvas, and Path primitives when they meet the intent without unnecessary dependencies.
- Make gestures unambiguous. Check nested scrolling, click handling, touch interception, clipping, contrast, content descriptions, touch targets, and small-screen sizing.
- Preserve the user's approved visual concepts and project-specific UI specs. Do not carry a palette, icon concept, or product-specific design from one app into another unless requested.
- Do not assume a screenshot has been tested on a physical device. Distinguish source review, CI build, emulator testing, and real-device visual validation.

## 4. Signing and installable releases

Apply this section only when producing an installable release APK.

1. Before the first user-installable release, check whether a valid existing signing key is configured. Reuse it if available; never create a replacement key merely because a new version is being built.
2. If no key exists and tools permit, generate one persistent keystore in a secure working environment. Provide the keystore, Base64 representation, and Secrets setup instructions as files/bundle when useful. Do not ask the user to run commands that available tools can perform.
3. Never regenerate a key for routine releases. Keep keystore and credentials out of source control and public repositories. Do not print secrets in logs or ask the user to paste them into chat. Explain secure backup and the consequence of losing the key.
4. Use the exact documented GitHub Secrets names from the actual workflow. Derive Base64 from the exact keystore used by CI. Do not assume store password and private-key password are equal unless verified.
5. Before Gradle release packaging, fail fast if required secrets are missing; decode the keystore to a temporary location and validate the file, password, and alias with `keytool` without exposing secrets. Verify the actual workflow implements this; documentation alone is not proof.
6. Diagnose the exact failing stage from the latest relevant Actions run and logs: missing Secrets, decode issues, store-password errors, alias mismatch, key-password errors, build failures, or release-upload failures.
7. Verify package ID, versionCode, signing certificate, and release asset. Warn before uninstalling an older APK if it may erase app data or has a different signing certificate.
8. Distinguish CI compilation, signature verification, emulator testing, and physical-device installation/update testing.

## 5. Implementation and data safety

1. Prefer the simplest implementation that meets the request and keep dependencies minimal.
2. Preserve existing preferences/data when changing settings UI. Do not silently change defaults, persistence keys, endpoints, permissions, signing, or release behavior.
3. For local-only apps, inspect manifest permissions, backup/data-extraction rules, SDK behavior, and dependencies for unintended network, analytics, advertising, or cloud behavior.
4. Avoid unrelated refactors, disconnected replacement projects, and broad changes outside the requested scope.
5. Review destructive operations carefully and make confirmation text precise about which files/data are deleted. Never imply that deleting an app-private copy deletes the original file unless the implementation proves that.

## 6. Verification and delivery

1. Inspect the actual diff/source after editing for duplicate statements, stale code, incorrect listeners, accidental behavior changes, clipping/measurement issues, and persistence regressions.
2. Run available unit tests, lint, and Gradle build. If local Android tooling is unavailable, use accessible CI or state the blocker.
3. Verify the exact Actions run and source commit SHA. Inspect logs for failures and relevant warnings.
4. Verify the exact artifact or GitHub Release asset exists before linking it. A source archive is not an APK.
5. State what was implemented, what automated checks passed/failed, whether a release asset exists, and what still needs emulator/device testing.
6. Never claim code was committed/pushed, Actions succeeded, an APK was built, or a device was tested unless that specific outcome was verified.
7. Keep user-facing updates concise and practical, in Chinese unless the user switches languages.

## 7. Preferred sequence

Inspect repository and instructions → search GitHub for reusable implementations → review source/build/release workflow → plan the smallest change → implement → review diff → run tests/build → commit/push through the authorized workflow → inspect the exact Actions run and logs → verify artifact/release asset → report commit, build status, links, and remaining device checks.
