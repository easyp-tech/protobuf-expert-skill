# Protobuf Expert — EasyP CLI Skill

Agent skill for Protocol Buffers design and the [EasyP CLI](https://github.com/easyp-tech/easyp) **v1**: a Git-native protobuf toolkit and an alternative to buf. It includes a step-by-step procedure for migrating EasyP **v0** projects to v1.

## What it does

- Writes, reviews and refactors `.proto` files
- Configures the v1 files: `protobuf.mod`, `protobuf.lock`, `easyp.yaml` (lint/breaking policy) and `easyp.gen.yaml` (generation)
- Chooses lint presets and rules, and breaking profiles (FILE / PACKAGE / WIRE_JSON / WIRE)
- Manages dependencies with `easyp get` and `easyp mod tidy|download|update|vendor`
- Detects and resolves breaking API changes
- Debugs lint, dependency and generation errors
- **Migrates EasyP v0 → v1:**
  - detects the config version;
  - records a v0 baseline;
  - previews `easyp migrate` and fixes its blockers;
  - applies the migration and verifies generated-code parity;
  - updates CI.
- Migrates from buf

## Install

```bash
npx skills add easyp-tech/protobuf-expert-skill
```

## EasyP versions

| Skill | EasyP |
|---|---|
| 1.x | v1 (`v1.0.0-nightly.*` and later); reads v0 projects only to migrate them |
| 0.1.0 | v0.x (`easyp.yaml` with `deps`, `lint.use`, `generate.inputs`) |

Verified against `v1.0.0-nightly.20261008.1`.

## Skills included

| Skill | Description |
|-------|-------------|
| `protobuf-expert-skill` | Protocol Buffers expert with deep EasyP CLI v1 knowledge and v0 → v1 migration |
