# ewatch Scoop bucket

[Scoop](https://scoop.sh) bucket for [snow-cli](https://github.com/ewatch/snow-cli),
which installs `snow-cli` and its read-only companion `snow-cli-ro` on Windows.

## Install

```powershell
scoop bucket add ewatch https://github.com/ewatch/scoop-bucket
scoop install ewatch/snow-cli
```

## Upgrade

```powershell
scoop update
scoop update snow-cli
```

## How the manifest stays current

`.github/workflows/update-manifest.yml` updates `bucket/snow-cli.json` to the
latest snow-cli release. It takes the archive's SHA-256 from that release's
`SHA256SUMS`. It runs when snow-cli's release workflow dispatches a
`new-release` event, daily as a fallback, and on demand.
`.github/workflows/test.yml` installs the manifest with Scoop on Windows and
smoke-tests both binaries.
