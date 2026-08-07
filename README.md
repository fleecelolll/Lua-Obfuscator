<div align="center">

# lua obfuscator

A little tool I made with AI to quickly obfuscate Lua 5.4 and Roblox Luau scripts & code locally on 64-bit Windows.

</div>

<p align="center">
  <img src="Lua Obfuscator.png" alt="lua obfuscator" width="694">
</p>

## features

- target Lua 5.4 or Roblox Luau
- choose low, medium, or high obfuscation
- select a `.lua`, `.luau`, or `.txt` file or drag it into the app
- choose the output folder
- follow progress in the built-in log
- process every script locally without uploads or telemetry

Lua 5.4 can use the complete Hercules protection set. Luau automatically skips the VM and bytecode protections that are not compatible with the Luau runtime.

## installation

1. download the latest ZIP from the [releases page](../../releases/latest)
2. extract the complete folder
3. double-click `Installer.bat` and let every setup check pass
4. double-click the `Lua Obfuscator` shortcut created in the folder

Setup keeps the app runtime, pinned Hercules source, and Lua 5.4.8 inside the extracted folder. It uses a compatible 64-bit Python 3.10 through 3.14 already on the PC when possible. Otherwise, it offers to download official Python 3.14.7 privately into the tool folder. It does not need administrator access, change PATH, install global Python packages, or install a background service.

Setup also installs one small shared launcher in `%LOCALAPPDATA%\Fleece Tools\Python Launcher` and sets `.pyw` files to open with it for your Windows account. The launcher always uses the selected tool's sibling `.venv\Scripts\pythonw.exe`, then its sibling `.runtime\python\pythonw.exe`. It never uses another tool's private Python. You can copy the normal `Lua Obfuscator` shortcut to your Desktop or pin it to the taskbar.

Before the first Fleece Tools association change, setup exports any existing per-user `.pyw` settings to the shared folder. If the previous setting cannot be backed up safely, setup stops without overwriting it. A later non-Fleece choice is also left alone.

The private Python, PySide6, Hercules, and Lua components are pinned and checked before setup reports success. Downloaded runtime archives are verified with SHA-256. Run `Installer.bat` again to repair setup or after moving the complete folder so its shortcut is recreated for the new location.

## usage

1. choose a `.lua`, `.luau`, or `.txt` file
2. select Lua 5.4 or Roblox Luau
3. select low, medium, or high obfuscation
4. choose the output folder
5. click **Obfuscate**

Plain `.txt` files are treated as source for the selected target. Lua output is saved as `<name>.obfuscated.lua`. Luau output is saved as `<name>.obfuscated.luau`. The original file is never overwritten.

## built with

- [Hercules](https://github.com/zeusssz/hercules-obfuscator)
- [PySide6](https://doc.qt.io/qtforpython-6/)
- [Lua 5.4](https://www.lua.org/)
- [Python](https://www.python.org/)

## privacy and removal

The app has no telemetry, analytics, accounts, or usage tracking. Scripts are processed locally and are never uploaded. To remove Lua Obfuscator, close it and delete its folder.

The shared `.pyw` launcher can be used by every installed Fleece Tool, so removing one tool does not remove it. To restore the `.pyw` settings that existed before Fleece Tools first configured them, run `%LOCALAPPDATA%\Fleece Tools\Python Launcher\Restore pyw association.cmd`. The restore helper refuses to overwrite a newer non-Fleece choice. After restoring, and after removing every Fleece Tool that uses it, you can delete the shared `Python Launcher` folder. Its registry backup files can contain local application names and paths, so review them before sharing.

## note

This project was made with AI.

Obfuscation makes source harder to read but does not make it impossible to recover. Only obfuscate code you own or have permission to modify.
