# Open questions

1. **Resolved.** Is the DMG a real UDIF image or a bare zlib stream? It's UDIF: it has a `koly` trailer, and `file` only saw the first zlib chunk.
2. **The window id `"main"`** was decoded from split immediates at `BIN @ 0x100007218`. The lower 16 bits weren't checked explicitly. Verify with a full disassembly read around `0x100007200-0x100007220`.
3. **How does "Otwórz ustawienia" open System Settings?** There's no `NSWorkspace.open` import. Is it SwiftUI's `openURL` environment value, or `openWindow`? Look at the `MainView.permissionCard` closures around `0x10000a5a8` / `0x10000a8b0`.
4. **The exact `maxDelay ≥ minDelay` rule in `normalizeSettings()`** (`0x100002f28-0x100003268`): swap, clamp, or set equal?
5. **How does `commitDelayFields()` parse input?** Is `replacingOccurrences` a `,`→`.` swap for Polish decimals? What happens with invalid text (revert or ignore)?
6. **What does the `NSEvent` local monitor handler do** (`0x100006b0c`)? It compares `event.window` with the field's window; it probably calls `makeFirstResponder(nil)` on outside clicks. Confirm.
7. **Mapping of the `MenuBarPanel` closures** (`0x1000109b8`, `0x100010bc0`, `0x100010d8c`) to Start / Stop / Open window / Quit (`NSApp.terminate:`).
8. **Front insertion vs. append in `appendLog`**: check the `replaceSubrange` arguments at `0x1000028d0` and the earlier array write.
9. **Relevance of the linked doc** `rPlayAI/carcast-public/docs/icarcast-user-guide.md`. It wasn't fetched: it's outside this session's GitHub scope, and `WebFetch` is denied in `.claude/settings.json`. Nothing in the binary mentions CarCast or rPlay.
