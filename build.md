## Development

If you want to modify the theme or build it from source:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/rtaparay/capy-theme-vscode.git
    cd capy-theme-vscode
    ```

2.  **Install dependencies:**
    This project requires Node.js 18 or 20.
    ```bash
    nvm install
    npm install
    ```

3.  **Build the extension:**
    To package the extension into a `.vsix` file:
    ```bash
    npx vsce package
    npx ovsx publish capy-theme-vscode-0.2.0.vsix -p <token>
    ```

4.  **Install the generated `.vsix`:**
    You can install the resulting file in VS Code by running:
    ```bash
    # VSCode
    code --install-extension capy-theme-vscode-0.2.0.vsix

    # Antigravity
    antigravity --install-extension  capy-theme-vscode-0.2.0.vsix

    # Cursor
    cursor --install-extension  capy-theme-vscode-0.2.0.vsix

    # Kiro
    kiro --install-extension  capy-theme-vscode-0.2.0.vsix

    # Trae
    trae --install-extension  capy-theme-vscode-0.2.0.vsix

    # Windsurf
    windsurf --install-extension  capy-theme-vscode-0.2.0.vsix

    ```
    *(Note: Replace `0.4.0` with the current version in `package.json` if it changes)*
