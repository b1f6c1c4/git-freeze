# git freeze

> Convert submodules to regular directories

## Why

External dependencies break everytime.
We want to manage everything by ourselves!

## Install

```bash
git clone --depth=1 git@github.com:b1f6c1c4/git-freeze.git
git config --global alias.freeze '!'"$(pwd)/git-freeze/git-freeze"
```

## Usage

```
Usage: git-freeze [-h|--help] [--shallow] [--octopus|--no-commit|--no-reset] ...

    Convert submodules to regular directories (of their HEADs)

    --octopus: preserve history of all submodules by merging

        Warning: ENTIRE history of ALL submodules is a huge deal!

    --no-commit: just give me the tree SHA1, don't commit

    --no-reset: just give me the index (implies --no-commit)

    ...: the rest parameters are passed directly to git commit

```

Note:
Submodules will be converted to directories of which content are wherever their HEADs point to,
**NOT** where the parent repo index points to.

If you wish to convert based on where the parent repo index points to, align the submodules HEADs with parent repo index first by:
```bash
git submodule update --recursive --init
```

## License

MIT
