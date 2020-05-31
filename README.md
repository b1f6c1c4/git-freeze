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
Usage: git-freeze [-h|--help] [-n|--dry-run]
        [--tree|--octopus] [--no-commit]
        [--keep-gitmodules]
        [--] <args-for-git-commit>

    Convert submodules to regular directories (of their HEADs)

    -n|--dry-run: Just list what commits will be freezed

    --tree: Don't modify anything, just give me the tree SHA-1
            (implies --no-commit)

    --octopus: Preserve history of all submodules by merging
        Warning: ENTIRE history of ALL submodules is a huge deal!

    --no-commit: Don't commit (like git merge --no-commit)

    --keep-git-modules: Do not remove the .gitmodules file
```

Note:
Submodules will be converted to directories of which content are wherever their HEADs point to,
**NOT** where the parent repo index points to.

If you wish to convert based on where the parent repo index points to, align the submodules HEADs with parent repo index first by:
```bash
git submodule update --init --recursive
```

Note:
This tool only modify the **parent repo**. All submodules' worktrees are **NOT touched**.

## License

MIT
