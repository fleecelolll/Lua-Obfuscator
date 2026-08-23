<div align="center">

# lua obfuscator

A little tool I made with AI to quickly obfuscate Lua 5.4 and Roblox Luau scripts and code locally on 64-bit Windows.

<img src="Lua%20Obfuscator.png" alt="Lua Obfuscator app window" width="760">

</div>

## features

- Target Lua 5.4 or Roblox Luau
- Choose low, medium, or high obfuscation
- Select or drag a `.lua`, `.luau`, or `.txt` source file
- Use the complete compatible Hercules protection set
- Choose the output folder and follow progress in the built-in log
- Keep the original source file unchanged
- Process every script locally without uploads or telemetry
- Validate the local engine before setup reports success

## requirements

- 64-bit x64 or ARM64 Windows
- An internet connection during first setup
- Source code you own or have permission to modify
- No internet connection while using the installed app

## installation

1. Download the latest release ZIP.
2. Extract the complete folder.
3. Double-click `Installer.bat`.
4. Press **Y** once to approve setup.
5. Leave the setup window open until every check passes.
6. Double-click the `Lua Obfuscator` shortcut created in the folder.

Keep the full extracted folder path at 72 characters or fewer so Windows can install the private packages reliably.

Setup keeps the private Python runtime and all app-specific components inside the extracted folder. It does not require administrator access, change PATH, or install global Python packages. The shortcut starts the app with that private runtime, so Microsoft Store or system Python is not required.

Setup pins and verifies official Python 3.14.7, pip, PySide6-Essentials, Hercules, and Lua 5.4.8. Downloaded runtime archives are checked against pinned SHA-256 hashes before use.

Setup also installs one small shared per-user launcher in `%LOCALAPPDATA%\Fleece Tools\Python Launcher` and safely associates `.pyw` files with it for the current Windows account. It backs up an existing per-user association before the first change and never borrows another tool's Python runtime.

Run `Installer.bat` again to repair the private components or after moving the complete folder. Setup preserves your source files and recreates the shortcut for the folder's current location.

## usage

1. Choose a `.lua`, `.luau`, or `.txt` source file.
2. Select Lua 5.4 or Roblox Luau.
3. Select low, medium, or high obfuscation.
4. Choose the output folder.
5. Click **Obfuscate**.

Lua output is saved as `<name>.obfuscated.lua`. Luau output is saved as `<name>.obfuscated.luau`. The original file is never overwritten.

## built with

- [Hercules](https://github.com/zeusssz/hercules-obfuscator)
- [PySide6](https://doc.qt.io/qtforpython-6/)
- [Lua 5.4](https://www.lua.org/)
- [Python](https://www.python.org/)

## privacy and removal

The app has no telemetry, analytics, advertisements, accounts, uploads, or runtime network requests. Scripts are processed locally. Setup logs can contain local folder paths, so review them before sharing.

To remove only Lua Obfuscator, close it and delete the extracted folder. The app does not install a background service, add itself to startup, or create an uninstaller entry.

The shared `.pyw` launcher can be used by every installed Fleece Tool, so removing one tool does not remove it. To restore the association that existed before Fleece Tools first configured it, run `%LOCALAPPDATA%\Fleece Tools\Python Launcher\Restore pyw association.cmd` after closing every Fleece Tool.

## troubleshooting

If setup stops, review `setup.log`, correct the listed problem, and run `Installer.bat` again. Setup reports success only after its dependencies, offline self-tests, and shortcut all pass.

If the `Lua Obfuscator` shortcut does not open, run `Installer.bat` again and keep the complete extracted folder together. Setup recreates and validates the shortcut for the folder's current location.

Lua and Hercules are installed privately by `Installer.bat`; a separate system-wide Lua installation is not required.

## source use

The source is public for transparency and security review. Copyright 2026 Fleece. All rights reserved. No permission is granted to use, copy, modify, redistribute, sell, or publish derivative versions. See [LICENSE](LICENSE).

## note

This project was made with AI.

Obfuscation makes source harder to read but cannot make recovery impossible. Only obfuscate code you own or have permission to modify.
