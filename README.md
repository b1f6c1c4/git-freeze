# git freeze

> Convert submodules to regular directories

## Important notice

Use at your own risk.

## Usage

Submodules will be converted to directories of which content are wherever their HEADs point to,
**NOT** where the parent repo index points to.
Thus, align the submodules HEADs with parent repo index first:
```bash
git submodule update --recursive --init
```

And now
```bash
git-freeze
```

## License

MIT
