# Symbol renames

These are demangled-by-hand names for the Swift symbols in `Mac Activity Lab.app/Contents/MacOS/MacActivityLab`. The `33_<hash>LL` part of private symbols is omitted from the old names. Module prefix: `$s14MacActivityLab`.

| Old name (mangled) | New name | Location | Reason |
|---|---|---|---|
| `_main` | `main` (Swift `@main` entry) | `0x100007944` | LC_MAIN target |
| `0abC3AppV` | `MacActivityLabApp` (struct, `App`) | body `0x100006f64` | `0abC` = word substitutions Mac+Activity+Lab, then `3App` |
| `0B10ControllerC` | `ActivityController` (class, `ObservableObject`) | init `0x100001cdc` | `0B` = substituted word "Activity" + `10Controller` |
| `0B10ControllerC6ActionO` | `ActivityController.Action` (enum: move, scroll) | metadata `0x100014658` | private enum; cases from reflection strings `move`, `scroll` |
| `0B10ControllerC5startyyF` | `ActivityController.start()` | `0x100002974` | |
| `0B10ControllerC5startyyFyyYacfU_` | `ActivityController.start()` → `Task` loop closure | `0x100003268` (segments `TY0_ 0x100003320`, `TY2_ 0x1000036fc`, `TY3_ 0x100003c0c`) | async closure #1 in start |
| `0B10ControllerC4stopyyF` | `ActivityController.stop()` | `0x100003c80` | |
| `0B10ControllerC17requestPermissionyyF` | `ActivityController.requestPermission()` | `0x10000247c` | |
| `0B10ControllerC17normalizeSettings…yyF` | `ActivityController.normalizeSettings()` (private) | `0x100002f28` | |
| `0B10ControllerC16performMouseMove…yyF` | `ActivityController.performMouseMove()` (private) | `0x100003df8` | |
| `0B10ControllerC13performScroll…yyF` | `ActivityController.performScroll()` (private) | `0x100004140` | |
| `0B10ControllerC13performScroll…yyFTv_` | `performScroll.scrollDeltas` static `[Int]` = `[-3,-2,-1,1,2,3]` | data `0x100020ab0` (elements at `+0x28`) | static array literal |
| `0B10ControllerC16isFailSafeCorner…SbyFTf4d_n` | `ActivityController.isFailSafeCorner() -> Bool` (private, specialized) | `0x1000056c0` | |
| `0B10ControllerC9appendLog…yySSF` | `ActivityController.appendLog(_ message: String)` (private) | `0x1000025e8` | |
| `0B10ControllerC8minDelaySdvsTm` | `ActivityController.{minDelay,maxDelay,maxMove}.setter` (merged thunk) | `0x100001be0` | `Tm` = merged function |
| `12MenuBarPanelV` | `MenuBarPanel` (struct, `View`) | body `0x10000ed3c` | |
| `8MainViewV` | `MainView` (struct, `View`) | body `0x1000082e4` | |
| `8MainViewV10statusPill…` | `MainView.statusPill` (private computed view) | `0x10000978c` | |
| `8MainViewV14permissionCard…` | `MainView.permissionCard` | closure `0x100009dd4` | |
| `8MainViewV12settingsCard…` | `MainView.settingsCard` | closure `0x10000a96c` | |
| `8MainViewV8controls…` | `MainView.controls` | `0x10000c648` area | |
| `8MainViewV7logCard…` | `MainView.logCard` | `0x10000cda8` area | |
| `8MainViewV15syncDelayFields…yyF` | `MainView.syncDelayFields()` | `0x100008e34` | |
| `8MainViewV17commitDelayFields…yyF` | `MainView.commitDelayFields()` | `0x10000b784` | |
| `8MainViewV12prettyNumber…ySSSdF` | `MainView.prettyNumber(_: Double) -> String` | `0x10000daec` | |
| `14DelayTextFieldV` | `DelayTextField` (struct, `NSViewRepresentable`) | `makeNSView 0x100005ad8` | |
| `14DelayTextFieldV11CoordinatorC` | `DelayTextField.Coordinator` (`NSObject`, `NSTextFieldDelegate`) | `controlTextDidEndEditing 0x10000616c` | ObjC class name string `MacActivityLab.Coordinator` `@ 0x100017b30` |
