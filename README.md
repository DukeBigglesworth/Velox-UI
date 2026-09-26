Velox UI
Modern premium Roblox UI library.
Forced cinematic VELOX loading animation
Multi-theme (Obsidian, Midnight, TokyoPurple, Emerald, Crimson, Cyberpunk)
Optional nametags (`false` / `true` / `"custom"`)
Full element set + freehand `createUI` builder
Screen-clamped windows, bottom-right notifications
Load
```lua
local Velox = loadstring(game:HttpGet("https://raw.githubusercontent.com/DukeBigglesworth/Velox-UI/refs/heads/main/Creation"))()
```
Quick example
```lua
local Window = Velox:CreateWindow({
    Title = "My Script",
    Theme = "Obsidian",
    Nametags = false,
})

local Tab = Window:CreateTab("Main", Velox.Icons.Home)

Tab:CreateToggle({
    Name = "Example",
    Default = false,
    Callback = function(v) print(v) end
})

Velox:Notify({
    Title = "Loaded",
    Content = "Velox is ready",
    Type = "Success"
})
```
Docs
See WIKI.md for full API (CreateWindow, elements, themes, nametags, createUI).
Files
File	Purpose
`Creation` (raw)	Library module
`WIKI.md`	Full documentation
Test scripts	Vertical / Horizontal / Custom UI demos
Credits
Library by Schwein
