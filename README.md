# QGroundZub-Releases

Public binary/update channel for QGroundZub.

This repository intentionally contains **no QGroundZub source code**. The application source remains in the private `Snip-21/QGroundZub` repository.

## Operator update channel

`latest.json` is the single manifest read by installed QGroundZub clients.

Only a Windows installer that has passed the normal QGroundZub validation and physical acceptance gate may be referenced by `latest.json`.

Publishing a build to this repository is a separate explicit release action. A branch build, failed build, or unvalidated Actions artifact must never become the operator `latest` version automatically.

For a new operator release:

1. bump `QGROUNDZUB_VERSION` in the private source repository;
2. build and validate `QGroundZub-installer-AMD64.exe`;
3. physically accept the candidate where required;
4. create a GitHub Release here, for example tag `v0.7.1`;
5. upload the validated installer asset;
6. calculate its SHA-256 and size;
7. update `latest.json` last, pointing to that exact release asset.

Updating `latest.json` is the moment the new version becomes visible to operators.
