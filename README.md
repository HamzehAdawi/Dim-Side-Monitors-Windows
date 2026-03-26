# FocusMode

![dimmerIcon](https://github.com/user-attachments/assets/22759d26-03b5-46e5-ac57-dece602aa926) &nbsp;&nbsp;&nbsp;Windows utility to dim side monitors for multi monitor setups. Concentrate on your main screen while keeping peripharls on, but _dim_. 

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
cd FocusMode
dotnet build
```

- This creates `DimmerApp.exe` in `bin/Debug/net8.0/` (or `bin/Release/net8.0/` if using release build)


### 2. Run the program

```powershell
dotnet run
```

- The tray icon appears in the bottom-right corner of Windows
- Double-click tray icon or use **Ctrl + 0** to toggle dimming

<br>

### ⚠️ To Set the app to always on (keep on startup):

1. Right-click the tray icon
2. Check **“Start with Windows”** to enable or disable startup
3. Close the program (right click exit from tray icon) and restart your computer.
4. The app will now always launch automatically on startup, unless unchecked.



<img width="473" height="221" alt="image" src="https://github.com/user-attachments/assets/3d8507a6-5f2c-4db3-acfe-30f41aae4d25" />


> Startup only works after the program has been run at least once

---


## Hotkeys & Changing configuration

| Hotkey      | Action               |
|------------|---------------------|
| Ctrl + 0    | Toggle dim on/off   |
| Ctrl + 1    | Set dim level 30%   |
| Ctrl + 2    | Set dim level 60%   |
| Ctrl + 3    | Set dim level 85%   |



You can change the hotkeys to any keys or combo keys you like by editing the **hotkeys.txt** file:

1. Open hotkeys.txt located in FocusMode directory with a text editor (Notepad, VS Code, etc.) 
2. Find the entry for the hotkey you want to change (Toggle, Dim1, Dim2, or Dim3)
3. Modify the modifier number and/or key
4. Save the file
5. Restart the app to apply the changes

<br>

### How do I know which numbers correspond to which keys when editing hotkeys.txt?
The full list of corresponding numbers to keys here: 
- Microsoft Documentation: https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.keys

### Quick tips: 
    Modifier numbers:
        0 = None
        1 = Alt
        2 = Ctrl
        4 = Shift

Keys: Use the names from the Windows Keys enumeration.
- Examples: D0, D1, F12, A, B, etc.

        Toggle=2,D0    -> Ctrl + 0 (toggle dim on/off)
        Dim1=2,D1      -> Ctrl + 1 (set dim 30%)
        Dim2=2,D2      -> Ctrl + 2 (set dim 60%)
        Dim3=2,D3      -> Ctrl + 3 (set dim 85%)

You can combine modifiers:
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
