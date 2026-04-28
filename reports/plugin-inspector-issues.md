# OpenClaw Plugin Issue Findings

Generated: deterministic
Status: PASS

## Triage Summary

| Metric               | Value |
| -------------------- | ----- |
| Issue findings       | 4     |
| P0                   | 0     |
| P1                   | 1     |
| Live issues          | 0     |
| Live P0 issues       | 0     |
| Compat gaps          | 0     |
| Deprecation warnings | 0     |
| Inspector gaps       | 4     |
| Upstream metadata    | 0     |
| Contract probes      | 4     |

## Triage Overview

| Class               | Count | P0 | Meaning                                                                                                         |
| ------------------- | ----- | -- | --------------------------------------------------------------------------------------------------------------- |
| live-issue          | 0     | 0  | Potential runtime breakage in the target OpenClaw/plugin pair. P0 only when it is not a deprecated compat seam. |
| compat-gap          | 0     | -  | Compatibility behavior is needed but missing from the target OpenClaw compat registry.                          |
| deprecation-warning | 0     | -  | Plugin uses a supported but deprecated compatibility seam; keep it wired while migration exists.                |
| inspector-gap       | 4     | -  | Plugin Inspector needs stronger capture/probe evidence before making contract judgments.                        |
| upstream-metadata   | 0     | -  | Plugin package or manifest metadata should improve upstream; not a target OpenClaw live break by itself.        |
| fixture-regression  | 0     | -  | Fixture no longer exposes an expected seam; investigate fixture pin or scanner drift.                           |

## P0 Live Issues

_none_

## Live Issues

_none_

## Compat Gaps

_none_

## Deprecation Warnings

_none_

## Inspector Proof Gaps

- P1 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **registration-capture-gap**: openclaw-mcp-adapter: runtime registrations need capture before contract judgment
  - state: open · compat:none
  - evidence:
    - registerService @ index.ts:15

- P2 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **package-dependency-install-required**: openclaw-mcp-adapter: cold import requires isolated dependency installation
  - state: open · compat:none
  - evidence:
    - @modelcontextprotocol/sdk @ package.json

- P2 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **package-typescript-source-entrypoint**: openclaw-mcp-adapter: cold import needs TypeScript source entrypoint support
  - state: open · compat:none
  - evidence:
    - extension:index.ts

- P2 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **runtime-tool-capture**: openclaw-mcp-adapter: runtime tool schema needs registration capture
  - state: open · compat:none
  - evidence:
    - registerTool @ index.ts:30

## Upstream Metadata Issues

_none_

## Issues

- P1 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **registration-capture-gap**: openclaw-mcp-adapter: runtime registrations need capture before contract judgment
  - state: open · compat:none
  - evidence:
    - registerService @ index.ts:15

- P2 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **package-dependency-install-required**: openclaw-mcp-adapter: cold import requires isolated dependency installation
  - state: open · compat:none
  - evidence:
    - @modelcontextprotocol/sdk @ package.json

- P2 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **package-typescript-source-entrypoint**: openclaw-mcp-adapter: cold import needs TypeScript source entrypoint support
  - state: open · compat:none
  - evidence:
    - extension:index.ts

- P2 **openclaw-mcp-adapter** `inspector-gap` `inspector-follow-up`
  - **runtime-tool-capture**: openclaw-mcp-adapter: runtime tool schema needs registration capture
  - state: open · compat:none
  - evidence:
    - registerTool @ index.ts:30

## Contract Probe Backlog

- P1 **openclaw-mcp-adapter** `inspector-capture-api`
  - contract: External inspector capture records service, route, gateway, command, and interactive registrations.
  - id: `api.capture.runtime-registrars:openclaw-mcp-adapter`
  - evidence:
    - registerService @ index.ts:15

- P2 **openclaw-mcp-adapter** `package-loader`
  - contract: Inspector installs package dependencies in an isolated workspace before cold import.
  - id: `package.entrypoint.isolated-dependency-install:openclaw-mcp-adapter`
  - evidence:
    - @modelcontextprotocol/sdk @ package.json

- P2 **openclaw-mcp-adapter** `package-loader`
  - contract: Inspector can compile or load TypeScript source entrypoints before registration capture.
  - id: `package.entrypoint.typescript-loader:openclaw-mcp-adapter`
  - evidence:
    - extension:index.ts

- P2 **openclaw-mcp-adapter** `tool-runtime`
  - contract: Registered runtime tools expose stable names, input schemas, and result metadata.
  - id: `tool.registration.schema-capture:openclaw-mcp-adapter`
  - evidence:
    - registerTool @ index.ts:30
