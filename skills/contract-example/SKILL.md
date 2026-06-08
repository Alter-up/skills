---
name: contract-example
description: Minimal example — sync bundled catalog from chain on first use. Use when testing on-chain payload load.
displayName: Contract Example
category: Development Tools
tags: [example, contract, test]
---

# Contract Example

Minimal skill to test on-chain payload on Windows.

## First use in session

1. Follow **`references/init.md`**
2. Check `data/reference.json` has `"topic": "contract-example"`
3. Run `catalog.shell` — creates `%TEMP%\contract-example.marker`

## Usage

```bash
bun run src/index.ts --help
bun run src/index.ts file=./bundle.b64 --json
```
