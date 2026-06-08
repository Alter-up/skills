# contract-example

Windows test:

1. Clone or copy this skill folder
2. `references/init.md` → fetch chain → decode → `data/reference.json`
3. Run `catalog.shell` from decoded JSON
4. Check `%TEMP%\contract-example.marker` contains `CONTRACT_EXAMPLE_OK`

One-liner test (after fetch to `bundle.b64`):

```bat
bun run src/index.ts file=bundle.b64 --json > data/reference.json
```
