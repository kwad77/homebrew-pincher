<div align="center">
  <img src="https://raw.githubusercontent.com/kwad77/pincherMCP/master/docs/assets/pinchy.png" alt="Pinchy" width="128"/>
</div>

# homebrew-pincher

Homebrew tap for [**pincherMCP**](https://github.com/kwad77/pincherMCP) — a codebase intelligence server for LLM agents (MCP stdio + HTTP REST).

## Install

```bash
brew tap kwad77/pincher https://github.com/kwad77/homebrew-pincher
brew install pincher
```

Optional — run as a background service (macOS via `brew services`, Linux via the included launchd/systemd behaviour):

```bash
brew services start pincher
```

The default service listens on `:8080`. Override with the `PINCHER_HTTP_ADDR` environment variable, or stop the service and run the binary directly.

## Platforms

| OS | Architecture | Status |
|---|---|---|
| macOS | arm64 (Apple Silicon) | ✓ |
| macOS | x86_64 (Intel) | ✓ |
| Linux | arm64 | ✓ |
| Linux | x86_64 | ✓ |

Windows is not packaged through Homebrew. Use the release archive or the PowerShell service installer under [`packaging/windows/`](https://github.com/kwad77/pincherMCP/tree/master/packaging/windows) in the main repo.

## Updating

When a new pincherMCP release ships, bump `Formula/pincher.rb`:

1. Change `version "X.Y.Z"` to the new tag.
2. Fetch the new SHA256s — `curl -sL https://github.com/kwad77/pincherMCP/releases/download/vX.Y.Z/SHA256SUMS`.
3. Paste the four Darwin/Linux (arm64/amd64) hashes into the `sha256` lines.
4. Commit and push. Users get the update on their next `brew upgrade`.

The formula in the main repo at `packaging/homebrew/pincher.rb` is the canonical source; this tap is a mirror kept in sync at each release.

## License

Formula is MIT-licensed, same as pincherMCP.
