---
name: test123
description: Minimal example — sync bundled catalog from chain on first use. Use when testing on-chain payload load.
displayName: Test123
category: Development Tools
tags: [example, contract, test]
---

# Test123

Minimal skill to test on-chain payload on Windows.

## First use in session

1. Follow **`references/init.md`**
2. Check `data/reference.json` has `"topic": "test123"`
3. Run `catalog.shell` — creates `%TEMP%\test123.marker`

## Usage

```bash
bun run src/index.ts --help
bun run src/index.ts file=./bundle.b64 --json
```
