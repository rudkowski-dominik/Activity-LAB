# Architecture

## Target

- File: `MacActivityLab-V5-macOS-AppleSilicon.dmg` (currently at repo root; meant to live in `target/`)
- Size: 128,295 bytes. CONFIRMED (`ls -la`)
- SHA-256: `c1436cf7382b929c2507ac77288c6871bbab2e755b8c3ea7861a45c15dfde491`. CONFIRMED (`sha256sum`)
- `file` output: `zlib compressed data`. CONFIRMED
- It's probably a UDIF image whose first block is zlib-compressed rather than a raw zlib stream. GUESS: the `koly` trailer hasn't been checked yet.

## Entry points

_Not analyzed yet._

## Data flow

_Not analyzed yet._
