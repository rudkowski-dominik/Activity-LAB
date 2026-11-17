# Overview

Target: `target/MacActivityLab-V5-macOS-AppleSilicon.dmg` (128,295 bytes)
SHA-256: `c1436cf7382b929c2507ac77288c6871bbab2e755b8c3ea7861a45c15dfde491`

## Initial observations

- `file` identifies it as **zlib compressed data**, not a standard UDIF disk image. The `koly` trailer hasn't been checked yet. (confidence: confirmed for `file` output only)

## Next steps

- Check the last 512 bytes for a `koly` trailer.
- If it's raw zlib, decompress it into the scratchpad and identify the payload.
