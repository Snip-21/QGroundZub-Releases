# QGroundZub-Releases

Public binary/update channel for QGroundZub.

This repository intentionally contains **no QGroundZub source code**. The application source remains in the private `Snip-21/QGroundZub` repository.

## Operator update channel

`latest.json` is the single manifest read by installed QGroundZub clients.

Only a Windows installer that has passed the normal QGroundZub validation and physical acceptance gate may be referenced by `latest.json`.

Publishing a build to this repository is a separate explicit release action. A branch build, failed build, or unvalidated Actions artifact must never become the operator `latest` version automatically.

For a new operator release:

1. bump `QGROUNDZUB_VERSION` in the private source repository;
2. update the private `CHANGELOG.md` for the new version;
3. update the in-app Help/About **What's new** version heading/text so it matches the built product version;
4. build and validate `QGroundZub-installer-AMD64.exe`;
5. physically accept the candidate where required;
6. create a GitHub Release here, for example tag `v0.8.2`;
7. write a short GitHub Release description summarizing what changed in that exact version before publishing the release;
8. upload the exact validated installer asset;
9. calculate/verify its SHA-256 and size;
10. update `latest.json` last, pointing to that exact release asset and including concise operator-facing notes.

Before considering a release complete, the following four user-facing descriptions must agree on the version and key changes:

- private `CHANGELOG.md`;
- in-app Help/About **What's new** block;
- public GitHub Release description;
- public `latest.json` notes.

Updating `latest.json` is the moment the new version becomes visible to operators.
