---
description: Let's start with the basics
sidebar_position: 1
---

# Setup

## Requirements
- Visual Studio Code v1.71.0+
- Tabletop Simulator v13.2.1+
- **External Editor API enabled in TTS** (Configuration → Interface → check "External Editor API")

## Install Extension
Launch VS Code Quick Open (<kbd class="kbc-button-sm">Ctrl</kbd>+<kbd class="kbc-button-sm">P</kbd>), paste the following command, and type enter.
```
ext install tabletopsimulator-lua
```
This will open the extension in the VS Code Marketplace. Click the `Install` button to install the extension.

## Configure Tabletop Simulator

Before using the extension, you need to enable the External Editor API in Tabletop Simulator:

1. Launch **Tabletop Simulator**
2. Go to **Configuration** → **Interface**
3. Check **"External Editor API"**
4. Restart TTS if prompted

This allows VSCode to communicate with Tabletop Simulator to get and send scripts.

## Working with the TTS API

This extension provides full integration with the **[Tabletop Simulator Lua API](https://github.com/Berserk-Games/Tabletop-Simulator-API)**:

- **IntelliSense/Autocomplete**: Type any TTS API function (e.g., `getObjectFromGUID`, `Player.getHandObjects`) to get autocomplete suggestions
- **API Documentation**: Hover over any function to see its documentation with a link to the official API docs
- **API Updates**: Use Command Palette → `TTS Lua: Update IntelliSense with latest TTS API` to get the latest API definitions without waiting for an extension update

### TTS API Resources
- **Official API Repository**: [github.com/Berserk-Games/Tabletop-Simulator-API](https://github.com/Berserk-Games/Tabletop-Simulator-API)
- **Hosted Documentation**: [api.tabletopsimulator.com](https://api.tabletopsimulator.com/)
- **Example Code**: [Official Examples on GitHub](https://github.com/Berserk-Games/Tabletop-Simulator-API/tree/master/example_code)
- **Community Forums**: [TTS Scripting on Steam](https://steamcommunity.com/app/286160/discussions/7/)

## Usage
- <kbd class="kbc-button-sm">Ctrl</kbd>+<kbd class="kbc-button-sm">Alt</kbd>+<kbd class="kbc-button-sm">`</kbd> Open TTS Console++
- <kbd class="kbc-button-sm">Ctrl</kbd>+<kbd class="kbc-button-sm">Alt</kbd>+<kbd class="kbc-button-sm">L</kbd> Get Lua Scripts
- <kbd class="kbc-button-sm">Ctrl</kbd>+<kbd class="kbc-button-sm">Alt</kbd>+<kbd class="kbc-button-sm">S</kbd> Save And Play

:::caution
Make sure Atom is closed if you are transitioning from the official editor as they will conflict with one another.
:::

## Other Installation Methods
### From package
You can also Install from the VSIX Package, you can find it under [Releases](https://github.com/rolandostar/tabletopsimulator-lua-vscode/releases/latest)

![VSIX Install Menu](https://raw.githubusercontent.com/rolandostar/tabletopsimulator-lua-vscode/main/media/docs/vsix.png)
### Manual Installation
Download or clone this repository and place it under:
- **Windows** `%USERPROFILE%\.vscode\extensions`
- **Mac** `$HOME/.vscode/extensions`
- **GNU/Linux** `$HOME/.vscode/extensions`
