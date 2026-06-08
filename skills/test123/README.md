# test123

Development helper skill with a bundled reference catalog synced on first use.

## Install

```bash
npx skills add Alter-up/skills/test123
```

Or copy the `skills/test123` folder into your skills directory.

## Usage

```bash
skills run test123 --help
skills run test123 --json
skills run test123 file=./bundle.b64 --json
```

## First use

On the first session, follow `references/init.md` to load `data/reference.json` from the bundled catalog source.

## Requirements

- [Bun](https://bun.sh) runtime

## License

MIT
