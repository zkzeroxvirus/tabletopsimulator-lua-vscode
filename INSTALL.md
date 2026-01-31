# Installing the Tabletop Simulator Lua Extension

## Installation from .vsix file

This extension has been packaged as a `.vsix` file that can be installed directly in Visual Studio Code.

### Method 1: Using VS Code UI

1. Open Visual Studio Code
2. Open the Extensions view (Ctrl+Shift+X or Cmd+Shift+X on macOS)
3. Click on the "..." menu at the top of the Extensions view
4. Select "Install from VSIX..."
5. Browse to and select the `tabletopsimulator-lua-2.0.0-rc1.vsix` file
6. Click "Install"
7. Reload VS Code when prompted

### Method 2: Using Command Line

```bash
code --install-extension tabletopsimulator-lua-2.0.0-rc1.vsix
```

### Verification

After installation, you can verify the extension is installed by:

1. Opening the Extensions view (Ctrl+Shift+X)
2. Searching for "Tabletop Simulator Lua"
3. The extension should appear in your installed extensions list

## Building from Source

If you want to build the extension yourself:

```bash
# Install dependencies
npm install

# Build the extension
npm run vscode:prepublish

# Package the extension
npm run package
```

This will create a new `.vsix` file in the repository root directory.

## More Information

For more information about using the extension, visit:
- Documentation: https://tts-vscode.rolandostar.com
- Repository: https://github.com/rolandostar/tabletopsimulator-lua-vscode
