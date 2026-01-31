---
description: Complete guide to developing Tabletop Simulator mods with this extension
sidebar_position: 3
---

# Working with Tabletop Simulator Mods

This guide will walk you through everything you need to know to develop mods for Tabletop Simulator using this VSCode extension.

## Prerequisites

Before starting, ensure you have:
1. **Tabletop Simulator** installed and running (v13.2.1+)
2. **VSCode** with this extension installed
3. **External Editor API enabled** in TTS (Configuration → Interface → check "External Editor API")

## Understanding the TTS Lua API

Tabletop Simulator uses a custom Lua environment based on Lua 5.2 with specialized classes and functions. This extension provides full integration with the official TTS API.

### Official Documentation

- **Official API Repository**: [https://github.com/Berserk-Games/Tabletop-Simulator-API](https://github.com/Berserk-Games/Tabletop-Simulator-API)
- **Hosted Documentation**: [https://api.tabletopsimulator.com/](https://api.tabletopsimulator.com/) (GitHub Pages)
- **Example Code**: [Official Examples](https://github.com/Berserk-Games/Tabletop-Simulator-API/tree/master/example_code)

### Key TTS API Concepts

#### Global Scripting
Global scripts run once and can access all objects in the game. Common uses:
- Game setup and initialization
- Turn management
- Global UI
- Inter-object communication

#### Object Scripting
Each object (cards, dice, boards, etc.) can have its own script. Object scripts have access to:
- `self` - Reference to the object itself
- Object-specific functions like `getPosition()`, `setRotation()`, etc.
- Object events like `onLoad()`, `onPickUp()`, `onDrop()`

## Getting Started with a Mod

### 1. Load or Create Your Mod

1. Launch Tabletop Simulator
2. Either:
   - Load an existing mod/save file
   - Create a new game with objects

### 2. Get Scripts from TTS

In VSCode:
- Press `Ctrl+Alt+L` (or `Cmd+Alt+L` on Mac)
- Or: Command Palette → `TTS Lua: Get Lua Scripts`

This will download all scripts from your current TTS game into your workspace.

### 3. Explore Your Scripts

The extension creates a file structure matching your TTS objects:
```
workspace/
├── Global.-1.lua          # Global script
├── Global.-1.xml          # Global UI (if exists)
├── Object.xyz123.lua      # Individual object scripts
└── Object.xyz123.xml      # Object UIs (if exist)
```

### 4. Writing Code with API Support

#### IntelliSense and Autocomplete

Start typing any TTS function to get autocomplete:

```lua
-- Type 'get' and press Ctrl+Space to see all functions starting with 'get'
local obj = getObjectFromGUID('abc123')

-- Type 'obj.' to see all available methods for objects
obj.setPosition({x=0, y=5, z=0})

-- Access Player functions
local players = Player.getPlayers()
for _, player in ipairs(players) do
    player.broadcast("Hello!")
end
```

#### Hover Documentation

Hover over any function to see:
- Function signature
- Parameter descriptions
- Return values
- Link to official API documentation

#### Common TTS API Examples

**Getting and Manipulating Objects:**
```lua
function onLoad()
    -- Get object by GUID (use autocomplete inside quotes!)
    local myCard = getObjectFromGUID('abc123')
    
    -- Move object
    myCard.setPositionSmooth({x=0, y=2, z=5})
    
    -- Get all objects with a specific tag
    local objects = getObjectsWithTag('resource')
end
```

**Working with Players:**
```lua
function onPlayerConnect(player)
    player.broadcast("Welcome " .. player.steam_name .. "!", {1,1,1})
end

function dealCardsToPlayers()
    local players = Player.getPlayers()
    for _, player in ipairs(players) do
        local hand = player.getHandObjects()
        -- Do something with player's hand
    end
end
```

**Creating Objects:**
```lua
function spawnCustomObject()
    local params = {
        type = 'Custom_Model',
        position = {x=0, y=3, z=0},
        rotation = {x=0, y=180, z=0},
        scale = {x=2, y=2, z=2}
    }
    
    local obj = spawnObject(params)
    return obj
end
```

**Using Coroutines for Timing:**
```lua
function delayedAction()
    startLuaCoroutine(self, 'delayedActionRoutine')
end

function delayedActionRoutine()
    wait(2.0)  -- Wait 2 seconds
    print("Action executed after delay!")
    return 1
end
```

### 5. Save Changes Back to TTS

After editing your scripts:
- Press `Ctrl+Alt+S` (or `Cmd+Alt+S` on Mac)
- Or: Command Palette → `TTS Lua: Save And Play`

This will:
1. Upload your changes to TTS
2. Trigger a reload in the game
3. Apply your changes immediately

## Advanced Features

### Execute Lua Directly

You can execute Lua code without saving:
1. Select some Lua code in your editor
2. Press `Ctrl+Alt+E` or use Command Palette → `TTS Lua: Execute selected Lua`
3. The code runs immediately in TTS

### Console++

For advanced debugging:
1. Command Palette → `TTS Lua: Install Console++`
2. Press `Ctrl+Alt+\`` to open Console++
3. See live output from your scripts
4. Execute commands directly in TTS

### Module Support

You can split your code into modules using `require()`:

**Main Script:**
```lua
local utils = require("utils")

function onLoad()
    utils.setupGame()
end
```

**utils.lua (in your workspace):**
```lua
local utils = {}

function utils.setupGame()
    print("Setting up game...")
end

return utils
```

The extension will automatically bundle these files when saving to TTS.

### XML UI Development

TTS supports XML-based UI. This extension provides:
- XML tag autocomplete (type `<` and see suggestions)
- Attribute completion (type space after tag name)
- Links to XML UI documentation

**Example XML UI:**
```xml
<Panel>
    <Text>Score: {score}</Text>
    <Button onClick="onButtonClick">Click Me</Button>
</Panel>
```

Corresponding Lua:
```lua
function onButtonClick(player, value, id)
    print("Button clicked by " .. player.color)
end
```

## Keeping Your API Up to Date

TTS receives regular updates. To get the latest API definitions:

1. Command Palette → `TTS Lua: Update IntelliSense with latest TTS API`
2. The extension downloads the latest API from the official source
3. Autocomplete is updated immediately

This means you don't have to wait for an extension update to get new TTS features!

## Troubleshooting

### Connection Issues

If VSCode can't connect to TTS:
1. Verify External Editor API is enabled in TTS
2. Check that TTS is running
3. Ensure no other editor (like Atom) is connected
4. Check firewall settings for port 39998

### Scripts Not Loading

If scripts don't appear in TTS after Save:
1. Check the Console++ or TTS console for errors
2. Verify your Lua syntax is correct
3. Try using "Get Scripts" first to refresh the connection

### Autocomplete Not Working

If API autocomplete isn't showing:
1. Try `TTS Lua: Update IntelliSense with latest TTS API`
2. Reload VSCode window (Command Palette → "Reload Window")
3. Check that the file has `.lua` extension

## Additional Resources

- [TTS Lua API on GitHub](https://github.com/Berserk-Games/Tabletop-Simulator-API)
- [TTS API Documentation (hosted)](https://api.tabletopsimulator.com/)
- [TTS Scripting Forums](https://steamcommunity.com/app/286160/discussions/7/)
- [Example Mods and Scripts](https://github.com/Berserk-Games/Tabletop-Simulator-API/tree/master/example_code)
- [TTS Workshop](https://steamcommunity.com/app/286160/workshop/) - Browse mods for inspiration

## Best Practices

1. **Use Global Script Sparingly**: Put shared functionality in Global, keep object-specific logic in object scripts
2. **Test Incrementally**: Save and test small changes frequently
3. **Use Console++**: It's invaluable for debugging
4. **Comment Your Code**: Future you will thank you
5. **Version Control**: Use Git for your mod development (see [Version Control Guide](versionControl))
6. **Check the API**: When in doubt, hover over functions to see documentation

Happy modding! 🎲
