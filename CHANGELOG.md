# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [v1.0.0] - 2026-10-08

Targets EasyP v1 (verified against `v1.0.0-nightly.20261008.1`).

### Added

- `references/migration-v0-to-v1.md` — a v0 → v1 migration procedure built around `easyp migrate`:
  - inventory, including nested and hidden configs;
  - v0 baseline;
  - choosing the module identity;
  - preview, and a table of migrate errors with their fixes;
  - a dependency re-resolution fallback;
  - apply, then verification with a generated-code parity check;
  - behaviour changes, CI updates, rollback;
  - full key mapping.
- Step 0 in `SKILL.md`: detect v0 / v1.0-rc / v1 / buf before giving advice.
- v1 starters:
  - `easyp.gen-go-grpc.yaml`
  - `easyp.gen-remote.yaml`
  - `protobuf-example.mod`

### Changed

- All references rewritten for the v1 file model (`protobuf.mod`, `protobuf.lock`, `easyp.yaml`, `easyp.gen.yaml`):
  - commands: `get`, `mod tidy`, `migrate`, `--frozen`; `generate --project/--all` instead of `-p/-r`;
  - lint presets and breaking profiles;
  - CI and installation for nightly builds.
- Starter policies `easyp-minimal.yaml`, `easyp-go-grpc.yaml`, `easyp-strict.yaml` now use the v1 syntax.

### Fixed

- Lint groups were documented as cumulative in v0. They are disjoint: v0 `use: [DEFAULT]` enabled 8 rules, not 32. v1 presets are cumulative.
- The inline suppression syntax was documented as `// easyp:off` / `// easyp:on`. That form is invalid; it is a hard error in v1. Use `// easyp:disable RULE` / `// easyp:enable RULE`.

### Removed

- `PACKAGE_NO_IMPORT_CYCLE` (removed from EasyP v1).

## [v0.1.0] - 2026-03-30

### Added

- `protobuf-expert-skill` — Protocol Buffers expert with deep EasyP CLI knowledge
- References: CLI commands, lint rules (42 rules, 5 groups), breaking checks, config reference, protobuf best practices
- References: installation guide, migration from buf.build, troubleshooting, CI/CD integration
- Starter configs: `easyp-minimal.yaml`, `easyp-go-grpc.yaml`, `easyp-strict.yaml`

[v1.0.0]: https://github.com/easyp-tech/protobuf-expert-skill/releases/tag/v1.0.0
[v0.1.0]: https://github.com/easyp-tech/protobuf-expert-skill/releases/tag/v0.1.0
