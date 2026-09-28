# Velox UI

Velox is a Lua UI library for Roblox scripts. It includes four layouts, built-in themes, draggable windows, mobile controls, and a set of widgets for common script settings.

## Load Velox

```lua
local Velox = loadstring(game:HttpGet("https://gist.githubusercontent.com/DukeBigglesworth/656085fae540b03e3c33901b6b2274b5/raw/gistfile1.txt"))()
```

This URL loads the latest file in the Gist. If you use a URL with a commit hash in it, it stays on that older revision when the Gist changes.

## Make a window

```lua
local window = Velox:CreateWindow({
    Title = "My Script",
    SubTitle = "Settings and tools",
    Preset = "Classic",
    Theme = "Obsidian",
    Size = UDim2.fromOffset(760, 520),
})

local home = window:CreateTab("Home", Velox.Icons.Home)
home:CreateParagraph({
    Title = "Welcome",
    Content = "Choose a control below to get started.",
})
home:CreateButton({
    Text = "Run action",
    Callback = function()
        print("Action ran")
    end,
})
```

## Layouts and themes

Set `Preset` to `Classic`, `Topbar`, `Rail`, or `Command`. These change tab placement and window composition. Set `Theme` to `Obsidian`, `Midnight`, `TokyoPurple`, `Cyberpunk`, `Emerald`, `Crimson`, or `RGB`.

```lua
window:SetTheme("RGB")
```

RGB cycles the accent and outlines. A theme change also updates existing Velox windows, mini windows, custom UI windows, and the minimized bubble.

## Background images

Use a direct image address or a Google Images image address. A Google search page itself is not an image; copy the image address from the image result.

```lua
local window = Velox:CreateWindow({
    Title = "My Script",
    BackgroundImage = "https://example.com/background.jpg",
    BackgroundImageTransparency = 0.18,
})
```

You can also change it after creating the window:

```lua
window:SetBackgroundImage("https://example.com/background.jpg")
```

The Customizer has a main background image field as well. Velox resolves remote images through the same asset loader used by nametag images.

## Widgets

A tab can contain buttons, toggles, sliders, dropdowns, keybinds, labels, paragraphs, status rows, logs, progress bars, and module buttons. Classic and horizontal layouts include search fields that filter widget names and open the tab containing a match. Rail keeps navigation compact and leaves search out.

See the [Wiki pages](wiki/Home.md) for setup details and examples. The `showcase_*.lua` files show the same sample controls in each layout.
