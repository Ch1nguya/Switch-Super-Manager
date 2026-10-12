# SSI HTTP API (console, port 2003)

Plain HTTP, LAN only. Available while SSI is open.

| Method | Path | Purpose |
|---|---|---|
| GET | `/ping` | liveness |
| GET | `/status` | state of SSI |
| GET | `/album[?root=]` | list captures |
| GET | `/album/file?p=` | download a capture |
| PUT | `/cheats/<TID>/<BID>.txt` | write a cheat file |
| POST | `/cover` | cover shown during install |
| POST | `/options` | e.g. `{"keep_awake_ac": true}` |
| POST | `/netinstall[?target=sd\|nand]` | start a network install session |
| POST | `/session/end` | end a remote session |
| POST | `/backup` | back up a save |
| POST | `/uninstall` | uninstall a title |

Management actions require *remote management* to be enabled in SSI options.
