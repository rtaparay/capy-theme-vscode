<p align="center">
  <img alt="capy Logo" src="https://raw.githubusercontent.com/rtaparay/capy-theme-vscode/main/images/logo.png" width="100" />
</p>
<h1 align="center">
  capy Theme for VS Code
</h1>
<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=rtaparay.capy-theme-vscode">
    <img alt="Version" src="https://img.shields.io/visual-studio-marketplace/v/rtaparay.capy-theme-vscode?color=brightgreen" />
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=rtaparay.capy-theme-vscode">
    <img alt="Downloads" src="https://img.shields.io/visual-studio-marketplace/d/rtaparay.capy-theme-vscode" />
  </a>
  <a href="https://marketplace.visualstudio.com/items?itemName=rtaparay.capy-theme-vscode">
    <img alt="Installs" src="https://img.shields.io/visual-studio-marketplace/i/rtaparay.capy-theme-vscode" />
  </a>
</p>

## Preview - Blackberry

![demo](https://raw.githubusercontent.com/rtaparay/capy-theme-vscode/main/images/demo_blackberry.png)

## Preview - Dark

![demo](https://raw.githubusercontent.com/rtaparay/capy-theme-vscode/main/images/demo_dark.png)

## Preview - Gray

![demo](https://raw.githubusercontent.com/rtaparay/capy-theme-vscode/main/images/demo_gray.png)

## Technologies Used

- [VS Code Color Theme](https://code.visualstudio.com/docs/extensions/themes-snippets-colorizers) - JSON theme format
- [Node.js 20.20.0](https://nodejs.org/) - Runtime
- [@vscode/vsce](https://github.com/microsoft/vscode-vsce) - Extension packaging
- [ESLint](https://eslint.org/) + [Prettier](https://prettier.io/) - Code quality

## Project Structure

```
├── package.json              # Extension manifest
├── themes/                   # Color theme JSON files
│   ├── capy-theme-blackberry-dark.json
│   ├── capy-theme-dark.json
│   └── capy-theme-gray.json
├── images/                   # Logo and demos
├── .eslintrc                # ESLint configuration
├── prettier.config.js       # Prettier configuration
├── .nvmrc                   # Node.js version
└── build.md                 # Build and installation 
```

## Installation via VS Code

1. Open **Extensions** sidebar panel in VS Code. `View → Extensions`
2. Search for `capy`
3. Click **Install** to install it
4. Click **Reload** to reload the editor
5. Code > Preferences > Color Theme > **capy**

## Manual Installation

For detailed installation instructions on different editors, see [build.md](build.md).

## Development

### Prerequisites

- Node.js 20.20.0 (use `nvm install`)

### Setup

```bash
npm install
```

### Testing Theme Changes

- Press `F5` to open a development window with the extension loaded
- Go to `File > Preferences > Color Themes` and select your theme
- Use `Inspect TM Scopes` command (Ctrl+Shift+P) to debug token colors
- Edit colors in `workbench.colorCustomizations` in VS Code settings for quick testing
- Run `Generate Color Theme From Current Settings` to export changes to JSON

### Code Quality

```bash
npx eslint .          # Lint code
npx prettier --write .  # Format code
```

### Build

```bash
npx vsce package     # Package extension as .vsix
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes following the code style guidelines
4. Test your changes using `F5`
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request
