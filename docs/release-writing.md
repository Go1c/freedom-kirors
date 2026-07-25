# Release writing guidelines

Release notes and `CHANGELOG.md` are public project documentation. Write them
for users of the repository, not for a specific deployment.

## Terminology

- Refer to `ZyphrZero/kiro.rs` as the **upstream project** or **upstream
  repository**, not as the “official repository”.
- Use **upstream service** only when referring to the remote API called by
  kiro-rs.
- Describe model identifiers as **upstream model identifiers** unless a
  first-party API document explicitly defines them.
- Clearly label names created by this project. For example, `-thinking` model
  names are client-facing compatibility aliases, not separate upstream models.
- Do not imply affiliation with, authorization by, or endorsement from AWS,
  Kiro, Anthropic, or other vendors.

## Evidence and scope

- Separate implemented behavior from observed availability.
- Qualify environment-dependent results: model availability can vary by
  account, region, rollout, and upstream changes.
- State the exact validation performed (`cargo test`, `cargo check`, build
  target, protocol test) without generalizing it to every environment.
- Avoid “fully supported”, “all models”, “real limits”, “official behavior”,
  or “completely fixed” unless the claim is directly documented and remains
  stable.

## Public/private boundary

Do not include:

- production hostnames, service names, local paths, credential IDs, account
  status, or private deployment state;
- “current account pool”, “production binary”, “already deployed”, or similar
  instance-specific language;
- internal rollback notes, incident details, private monitoring results, or
  operational instructions unrelated to release users.

Keep deployment-specific evidence in private operations notes rather than the
public changelog.

## Recommended structure

```markdown
## Summary

One or two sentences describing the user-visible purpose of the release.

### Added
- New capabilities.

### Changed
- Behavior changes and compatibility notes.

### Fixed
- Defects corrected.

### Validation
- Reproducible tests and builds that completed successfully.

### Compatibility notes
- Rollout, account, region, migration, or backward-compatibility constraints.
```

Use only the sections that apply. Prefer concise technical language over
promotional wording.
