<div align="center">
<h2>Tabletop Simulator Lua Extension for VSCode</h2>
<br>
<img width="500" src="https://raw.githubusercontent.com/rolandostar/tabletopsimulator-lua-vscode/main/media/docs/banner.png" alt="VSCode-TabletopSimulator-Lua">
<br>
<br>
</div>

<p align="center" color="#6a737d">
Extension for VSCode to make writing Lua scripts for  <a href="https://store.steampowered.com/app/286160/Tabletop_Simulator/">Tabletop Simulator</a> easier.
</p>

<div align="center">

[![Build Documentation](https://github.com/rolandostar/tabletopsimulator-lua-vscode/actions/workflows/build-docs.yaml/badge.svg?branch=main)](https://github.com/rolandostar/tabletopsimulator-lua-vscode/actions/workflows/build-docs.yaml)
[![Deploy Extension](https://github.com/rolandostar/tabletopsimulator-lua-vscode/actions/workflows/deploy-to-marketplace.yaml/badge.svg?branch=main)](https://github.com/rolandostar/tabletopsimulator-lua-vscode/actions/workflows/deploy-to-marketplace.yaml)
</div>
<div align="center">
<img src="https://badgen.net/badge/uses/TS/blue"/>
<img src="https://badgen.net/badge/designed in/MS Paint/yellow"/>
<img src="https://badgen.net/badge/made%20with/%E2%9D%A4/red"/>
</div>

## Features

- Get/Send Scripts
- <img src="media/docs/new.png" width="80"/> Execute Lua without Save & Play
- <img src="media/docs/new.png" width="80"/> Improved Code autocompletion for Lua
  - Smart `GUID` suggestions which scans your save file, it even detects newly-created objects.
  - Update to latest available TTS API without waiting for manual updates. ([Learn More](here))
- <img src="media/docs/new.png" width="80"/> Added Code autocompletion for XML!
- <img src="media/docs/new.png" width="80"/> Added Version Control Support, you can now more easily use Git to manage your scripts!
- <img src="media/docs/new.png" width="80"/> Hover over a `GUID` in VSCode to Highlight the object In-Game
- Nested file support
  - `require("")` for Lua
  - `<Include src=""/>` for XML
  - Configurable search patterns and lookup directories (yes, plural)
  - Works with absolute directories, perfect for source controlled projects
  - <img src="media/docs/new.png" width="80"/> Debug module resolution issues right in VSCode (Never again wonder why your file isn't reachable)
- <img src="media/docs/new.png" width="80"/> Improved Configuration (Made them clearer and categorized)
- Built-in Console
  - Integration with [Console++](https://github.com/onelivesleft/Console) by onelivesleft ([Tutorial](http://blog.onelivesleft.com/2017/09/debugging-your-tts-mods-with-console.html)) with Automatic Installation!
  - Send commands from VSCode (Adds `onExternalCommand`)
  - Receive output and debug information on VSCode Panel
  - BBCode and nested colors support!
- <img src="media/docs/new.png" width="80"/> Improved and extensive documentation available at [tts-vscode.rolandostar.com](tts-vscode.rolandostar.com)
  - Learn how to use version control, step-by-step debugging, and more!
- <img src="media/docs/new.png" width="80"/> Added an experimental asset downloader, which helps you download and rehost assets via Github

<br/>

![Demo Reel](https://raw.githubusercontent.com/rolandostar/tabletopsimulator-lua-vscode/main/media/docs/demo.gif)

---

## [Installation & Usage](https://tts-vscode.rolandostar.com/extension/setup)

## Working with Tabletop Simulator Mods

This extension is fully integrated with the official **[Tabletop Simulator Lua API](https://github.com/Berserk-Games/Tabletop-Simulator-API)**.

### Features for Mod Development

- **API-Aware IntelliSense**: Get autocomplete suggestions for all TTS Lua functions, objects, and events based on the official API
- **Automatic API Updates**: Update to the latest TTS API without waiting for extension updates (Command: `TTS Lua: Update IntelliSense with latest TTS API`)
- **API Documentation Links**: Hover over functions to see documentation with direct links to the official TTS API documentation
- **Live Communication**: Connect directly to Tabletop Simulator to Get/Send scripts in real-time
- **XML UI Support**: Full autocomplete and documentation for TTS XML UI elements

### Quick Start for Mod Development

1. **Install the Extension** from the VSCode Marketplace
2. **Start Tabletop Simulator** and load your mod or create a new save
3. **Enable External Editor API** in TTS: Configuration → Interface → check "External Editor API"
4. **Get Scripts** in VSCode with `Ctrl+Alt+L` or Command Palette → `TTS Lua: Get Lua Scripts`
5. **Make Changes** to your Lua scripts in VSCode with full autocomplete support
6. **Save and Play** with `Ctrl+Alt+S` or Command Palette → `TTS Lua: Save And Play`

### TTS API Resources

- **Official API GitHub Repository**: [https://github.com/Berserk-Games/Tabletop-Simulator-API](https://github.com/Berserk-Games/Tabletop-Simulator-API)
- **Hosted API Documentation**: [https://api.tabletopsimulator.com/](https://api.tabletopsimulator.com/)
- **Scripting Community Help**: [Steam Community Forums](https://steamcommunity.com/app/286160/discussions/7/)
- **Example Code**: [Official Examples](https://github.com/Berserk-Games/Tabletop-Simulator-API/tree/master/example_code)

## Additional Documentation

- [Extension Configurations](https://tts-vscode.rolandostar.com/extension/configuration)
- [Extension Commands](https://tts-vscode.rolandostar.com/extension/commands)
- [Module Resolution (AKA Nested Files)](https://tts-vscode.rolandostar.com/extension/moduleResolution)
- [Console++](https://tts-vscode.rolandostar.com/extension/console++)
- [API Updates Guide](https://tts-vscode.rolandostar.com/extension/apiUpdates)

## Release Notes

Check [CHANGELOG.md](https://github.com/rolandostar/tabletopsimulator-lua-vscode/blob/main/CHANGELOG.md)

## About

This project was motivated on trying out different solutions to communicate VSCode with TTS and being rather unsuccessful at that. I tried using [OliPro007's Extension](https://github.com/OliPro007/tabletopsimulator-lua-vscode) and was a bit finicky for me, I also checked out [dustinlacewell's vatts](https://github.com/dustinlacewell/vatts) and was able to retrieve scripts but not send them. I guess I'm just inexperienced setting up these extensions which is why I wanted to dive into it by making my own and hoped to streamline the process for someone else.

I kind of ended up doing my own thing.

If you have any suggestions feel free to contact me or submit a PR.

<div align="center">
<h2>Contact</h2>
<p>You can find me on <a href="http://steamcommunity.com/id/rolandostar/">Steam</a> and <a href="https://www.reddit.com/user/rolandostar">Reddit</a>!</p>
<p>If you like this extension, please consider a small donation.</p>
<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7PK5YQ9HR3Z52"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" border="0" name="submit" title="PayPal - The safer, easier way to pay online!" alt="Donate with PayPal button"/></a>
</div>
