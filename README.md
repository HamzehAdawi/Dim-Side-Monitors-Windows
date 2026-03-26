# Dim-Side-Monitors for Windows

A lightweight Windows utility to **dim side monitors** with hotkeys and a tray icon, with optional startup on login.

---

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
cd DimmerApp
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

---

## Hotkeys

| Hotkey      | Action               |
|------------|---------------------|
| Ctrl + 0    | Toggle dim on/off   |
| Ctrl + 1    | Set dim level 30%   |
| Ctrl + 2    | Set dim level 60%   |
| Ctrl + 3    | Set dim level 85%   |

---

## Notes

- Windows 10+ only
- Only dims **secondary monitors**, primary monitor is not affected
- The tray icon can be used to exit the app cleanly

---

## Optional Enhancements

- Replace the tray icon with your own `.ico` file (edit `trayIcon.Icon`)
- Adjust default dim opacity in `DimmerApp.cs`
