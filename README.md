# gh-plate

**Thin shim for the official `gh plate` GitHub CLI extension.**

This repository exists solely to satisfy GitHub CLI's requirement that extension repository names start with `gh-`.

## Install

```sh
gh extension install akasper/gh-plate
gh plate health
gh plate release status
# etc.
```

## How it works

- `gh` clones this repo and executes the `gh-plate` script at the root.
- The launcher ensures the `plate-core` Python package is installed (via `pip install --user plate-core` if needed) and then delegates to the real implementation in `plate_core.cli`.
- All actual functionality, the `plate-core` package on PyPI, MCP server, plugins, source code, and documentation live in the main repository: https://github.com/akasper/plate

## Versioning

This shim is kept in sync with releases of the main `plate` repo by automation (see below). Matching tags (e.g. `vX.Y.Z`) are created here when the main repo releases plate-core vX.Y.Z.

- `gh extension install akasper/gh-plate` gets the latest.
- Pin a specific release: `gh extension install akasper/gh-plate@vX.Y.Z`

The runtime behavior comes from whatever version of `plate-core` is installed in your environment.

## Maintenance

This is **not** a full PLATE methodology repository. It is a minimal publishing shim.

Ongoing updates to the launcher and version markers are handled automatically from the main repo's release process.

See:
- Epic: https://github.com/akasper/plate/issues/596
- Task (creation of this repo): https://github.com/akasper/plate/issues/597
- Feature (sync automation): https://github.com/akasper/plate/issues/599

## License

Same as the main project (see https://github.com/akasper/plate).
