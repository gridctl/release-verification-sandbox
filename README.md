# Release Verification Sandbox

Disposable public infrastructure for testing Gridctl release tooling.

Release tags, drafts, published assets, and attestations created here are test
data, not official Gridctl releases. Do not install them as production software.

## Isolation

- Release destination: `gridctl/release-verification-sandbox` only.
- Test tap: `gridctl/homebrew-verification-sandbox` only.
- Never copy production credentials into this repository.
- Before importing release tooling, replace and verify all publication targets.
  The upstream GoReleaser configuration contains production destinations.
- Keep write and OIDC permissions scoped to the jobs that require them.
- Sandbox attestation identities cannot establish production release provenance.

The manual environment check validates hosted Linux/macOS runner access and
availability of job-scoped OIDC. It does not build, attest, or publish release
artifacts, and it does not satisfy release acceptance by itself.

Immutable releases are initially disabled. Enable them only when the test
publication sequence and recovery procedure are ready; immutable test assets
must not be treated as replaceable fixtures.
