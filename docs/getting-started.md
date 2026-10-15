# Getting started

1. Download the latest release zip from [Releases](https://github.com/Ch1nguya/Switch-Super-Manager/releases) and check it against `SHA256SUMS`.
2. Unzip anywhere. Put **your own `prod.keys`** (dumped from your console, never provided) in a `keys` folder next to `Switch-Super-Manager.exe`. SSM also looks in `C:\Users\<you>\.switch\prod.keys`. Without it, SSM does not start.
3. Start `Switch-Super-Manager.exe`. A start-up assistant helps you choose the language, check your `prod.keys`, pick your library folder and scan it (you can add more folders in the Settings).
4. Import your dumps in the Import tab.
5. On the console, install **Switch-Super-Installer** (`.nro` in `/switch/`) and launch it in full-memory mode: start a game while holding R (title override), not from the Album (applet mode has limited memory and is not supported).
6. In SSM, Console tab: enter the console IP, then send titles from the library.

Both devices must be on the same LAN; see [network.md](network.md).
