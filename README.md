# Dim Side Monitors for Windows

A lightweight Windows utility to **dim side monitors** with hotkeys and a tray icon, with optional startup on login.



## Features

- Toggle dimming with **Ctrl + 0**
- Set dim levels with **Ctrl + 1 / 2 / 3**
- Tray icon for quick access
- Toggle **Start with Windows** from tray menu
- Works on multi-monitor setups, only dims secondary monitors

---

## Installation

### 1. Build from source

Requires **.NET SDK 8+**.

```powershell
git clone <your-repo-url>
cd Dim-Side-Monitors-Windows
dotnet build
```

- This creates `DimmerApp.exe` in `bin/Debug/net8.0/` (or `bin/Release/net8.0/` if using release build)

---

### 2. Run the program

```powershell
dotnet run
```

- The tray icon appears in the bottom-right corner of Windows
- Double-click tray icon or use **Ctrl + 0** to toggle dimming

---

### 3. Enable auto-start (optional)

1. Right-click the tray icon
2. Click **“Start with Windows”** to enable or disable startup
3. This writes a registry entry so the program automatically runs at login

> ⚠️ Startup only works after the program has been run at least once



## Hotkeys

| Hotkey      | Action               |
|------------|---------------------|
| Ctrl + 0    | Toggle dim on/off   |
| Ctrl + 1    | Set dim level 30%   |
| Ctrl + 2    | Set dim level 60%   |
| Ctrl + 3    | Set dim level 85%   |

CUSTOMIZING HOTKEYS

You can change the hotkeys to any keys or combo keys you like by editing the **hotkeys.txt** file.

STEPS TO CHANGE HOTKEYS

1. Open hotkeys.txt in a text editor (Notepad, VS Code, etc.)
2. Find the entry for the hotkey you want to change (Toggle, Dim1, Dim2, or Dim3)
3. Modify the modifier number and/or key
4. Save the file
5. Restart the app to apply the changes

UNDERSTANDING MODIFIERS AND KEYS

Modifier numbers:
0 = None
1 = Alt
2 = Ctrl
4 = Shift

Keys: Use the names from the Windows Keys enumeration.
Examples: D0, D1, F12, A, B, etc.

For a full list of key names you can use in hotkeys.txt, see the official Microsoft documentation:
https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.keys

EXAMPLES

Toggle=2,D0    -> Ctrl + 0 (toggle dim on/off)
Dim1=2,D1      -> Ctrl + 1 (set dim 30%)
Dim2=2,D2      -> Ctrl + 2 (set dim 60%)
Dim3=2,D3      -> Ctrl + 3 (set dim 85%)

TIP: You can combine modifiers. For example:
Toggle=6,D0    -> Ctrl + Shift + 0 (because 2 + 4 = 6)

---

## Notes

- Windows 10+ only
- Only dims **secondary monitors**, primary monitor is not affected
- The tray icon can be used to exit the app cleanly

---

## Optional Enhancements

- Replace the tray icon with your own `.ico` file (edit `trayIcon.Icon`)
- Adjust default dim opacity in `DimmerApp.cs`
