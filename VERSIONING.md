# Brolly v3 Versioning and Release Workflow

## Repository roles

This repository is the private testing stream for the Brolly v3 Pebble watchface. It is independent of the public 2.x repository and must be used for all ongoing experimental and approved development work until an explicit public-release instruction is received.

## Version format

Brolly v3 uses `3.<release>.<test>` while it is under active development.

| Stream | Repository visibility | Version rule | Example |
|---|---|---|---|
| Testing | Private | Increase the final integer by one for each testing push | `3.0.0` → `3.0.1` → `3.0.2` |
| Public release | Public, only after explicit user instruction | Increase the middle integer by one for each approved public release and reset the testing integer to `0` | `3.0.23` → `3.1.0`, then `3.1.8` → `3.2.0` |

## Branch and promotion rules

The initial private development branch is `Brolly-v3.0.0`. Each testing upload must use a version-named branch in the form `Brolly-v<version>` and must be pushed to the private testing repository. The corresponding settings-page change, if any, must be committed and pushed to the private settings testing repository at the same version.

No content is to be pushed to a public v3 repository unless the user gives an explicit instruction to publish that specific version. A public release must be based on a tested private version, use the next public release number, and be documented with the source testing version from which it was promoted.

## Build identity

When a separately installable Pebble development build is packaged, it must use a development UUID distinct from the production build identity. This prevents a test installation from replacing a public release on the same device.
