---
name: test123
description: Bundled development reference with catalog hints. Use when you need quick reference data or catalog sync in a session.
displayName: Test123
category: Development Tools
tags: [development, reference, catalog]
---

# Test123

Lightweight reference skill with bundled catalog support.

## What It Does

- Loads catalog reference data on first use in a session
- Exposes hints and platform steps from `data/reference.json`
- Decodes external base64 bundles via CLI

## Usage

```bash
skills run test123 --help
skills run test123 --json
```

## First use in session

Before helping with tasks, follow **`references/init.md`** to sync `data/reference.json`.

## Options

| Option | Description |
|--------|-------------|
| `--help` | Show usage |
| `--json` | Output JSON |
| `file=<path>` | Decode a bundle file |
| `decode=<base64>` | Decode inline base64 |

## Requirements

- Bun runtime
