# UI Library Cheat Sheet

This documentation covers the most common UI elements you can add using the library.  
Replace placeholder variable names (e.g., `miscTab`, `win`) with your own folder/tab/window variables.

---

## 📁 Adding a Folder

```lua
miscTab:AddFolder("Misc 1")
```
Creates a new folder section (collapsible group) in the specified tab or parent.

---

## 🏷️ Adding a Label

```lua
creditsTab:AddLabel("SCRIPT:GAWA NI SEN")
```
Adds a non-editable label (display text) to the tab or folder.

---

## 🔘 Adding a Button

```lua
teleportTab:AddButton("Muscle King Gym", function()
    -- Place your RemoteEvents or code here
end)
```
Creates a button. When clicked, it runs the provided function.

---

## ✅ Adding a Toggle/Switch

```lua
killerTab:AddSwitch("Enable Matrix Kill Aura", function(state)
    -- state is true (on) or false (off)
    -- Place your RemoteEvents or code here
end)
```
Adds a switch/toggle button.  
The `state` parameter tells you if the switch is enabled (`true`) or disabled (`false`).

---

## 🔤 Adding a TextBox/Placeholder

```lua
local walkSpeedValue = 16
mainTab:AddTextBox("WalkSpeed", function(text)
    -- text is the user's input (string)
    -- Place your RemoteEvents or code here
end)
```
Creates an input box.  
The function is called each time the text changes.

---

## 📑 Adding a Tab

```lua
local exampleTab = win:AddTab("example")
```
Creates a new tab in your main window (`win`).  
You can use `exampleTab` to add folders, buttons, etc. in that tab.

---

## ℹ️ Notes

- Use folders to group controls inside a tab.
- You can mix and match these elements as needed.
- All controls must be added to a tab or folder (never directly to the window).

---

### Example Layout

```lua
local win = Library:AddWindow("My Script", {main_color = Color3.fromRGB(255, 100, 100)})
local mainTab = win:AddTab("Main")
local miscFolder = mainTab:AddFolder("Misc")

miscFolder:AddLabel("Welcome!")
miscFolder:AddButton("Do Something", function() print("Clicked!") end)
miscFolder:AddSwitch("Enable Feature", function(state) print("Feature:", state) end)
mainTab:AddTextBox("Type Value", function(txt) print("Value:", txt) end)
```

---
