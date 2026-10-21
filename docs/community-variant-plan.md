# Community Variant Plan

## Repository status

- This repository contains the upstream Cryptomator for Android source on the `develop` branch.
- The upstream README and its build instructions are preserved.
- The independent community-variant work is documented here rather than replacing upstream project documentation.
- No community-specific application ID has been configured yet.
- No APK from this repository has been built or tested yet.

## Product requirements

- Keep the original Cryptomator Android interface wherever practical.
- Retain upstream-supported local and cloud storage features, subject to their normal provider/API-key requirements.
- Preserve Cryptomator Hub entitlement checks. Do not bypass paid features, server-side checks, or access controls.
- Give the community variant a distinct application ID so it can coexist with the official app, after confirming the project’s Gradle flavor/build-type structure.
- Keep source, license notices, attribution, and third-party license obligations intact.
- Distribute an APK only after a successful build and device testing. Never commit signing keys, API credentials, or tokens.

## Next steps

1. Inspect the Gradle configuration and identify existing product flavors, application IDs, build types, and manifest placeholders.
2. Review the upstream license, branding/trademark guidance, dependency notices, and any provider API-key requirements.
3. Run the documented upstream baseline build before making code changes. The upstream README currently documents `./gradlew assembleApkstoreDebug` and requires JDK 21.
4. Add the smallest possible community variant configuration with a unique application ID; do not alter entitlement enforcement.
5. Build the community debug APK and run available tests.
6. Test install/coexistence with the official app, vault creation and unlock, file read/write, lock/reopen, and relevant storage integrations on a physical Android device.
7. Add or adapt CI to build the chosen variant and publish test artifacts. Keep credentials in repository secrets or local environment variables.
8. Publish source and APK together only after tests pass, with clear independent-project wording and attribution.

## Acceptance criteria

- The upstream baseline builds successfully.
- The community variant installs alongside the official app.
- Core vault flows pass device testing.
- Hub entitlement checks remain intact.
- No credentials or signing keys are committed.
- The APK is not described as tested or released until that is verified.

## Notes

This is an independent community project, not an official Cryptomator release. Re-check upstream documentation before releases because build instructions and provider integrations can change.
