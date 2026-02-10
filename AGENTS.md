# Agent Guidelines for Halcyon VS Code Theme v2

## Project Overview

This is a **VS Code Theme Extension** project called "Halcyon Theme v2" - a dark blue theme based on Ayu Mirage. The project targets VS Code ^1.18.0 and uses modern JavaScript tooling including ESLint, Prettier, and Babel.

## Build/Development Commands

### Required Tools
- Node.js 20.20.0 (specified in `.nvmrc`)
- VS Code Extension CLI (`vsce`)

### Package Management
```bash
# Install dependencies (if package.json exists in root)
npm install

# Use correct Node version
nvm use
```

### Development Commands
```bash
# Package the extension
npx vsce package

# Install locally for testing
code --install-extension halcyon-vscode-v2-0.1.0.vsix

# Debug extension (use VS Code's "Extension" launch configuration)
# Press F5 in VS Code to launch Extension Development Host
```

### Linting and Formatting
```bash
# Run ESLint
npx eslint .

# Run Prettier
npx prettier --check .
npx prettier --write .
```

### Testing
- **No automated test suite currently exists**
- Manual testing involves installing the extension and verifying theme colors
- Test with demo files in `demo/` directory for different languages

## Project Structure

```
├── package.json                     # Extension manifest (currently in VSIX only)
├── themes/
│   └── halcyon-color-theme.json    # Main theme definition (32KB)
├── images/                         # Logo and demo images
├── demo/                          # Sample files for theme testing
├── .eslintrc                      # ESLint configuration
├── .nvmrc                         # Node.js version specification
├── .vscode/launch.json            # VS Code debug configuration
└── prettier.config.js             # Prettier configuration
```

## Code Style Guidelines

### ESLint Configuration
- Extends `@upstatement` ESLint config
- Node.js and ES6 environment enabled
- Must fix all ESLint errors before committing

### Prettier Configuration
- Uses `@upstatement/prettier-config`
- Consistent formatting across all files
- Run Prettier before committing

### Import Conventions
```javascript
// Prefer ES6 imports
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

// Group imports: external modules first, then local modules
```

### Naming Conventions
- **Files**: kebab-case for theme files (`halcyon-color-theme.json`)
- **Classes**: PascalCase (`AppModule`, `AppComponent`)
- **Variables/Functions**: camelCase (`hello`, `doesNotExist`)
- **Constants**: camelCase (following project patterns)

### TypeScript/JavaScript Style
- Use ES6+ features (arrow functions, const/let, template literals)
- Prefer arrow functions for simple functions: `const brit = () => {}`
- Use proper class syntax with extends keyword
- Always use semicolons (enforced by Prettier)

### Theme Development Guidelines
- **Color Values**: Use 6-digit hex codes with lowercase letters
- **Theme Structure**: Follow VS Code theme schema exactly
- **Semantic Tokens**: Support semantic highlighting where applicable
- **Testing**: Test theme with all demo files in `demo/` directory

### Error Handling
- Handle theme loading errors gracefully
- Validate color values before theme compilation
- Ensure theme works across different VS Code versions

## File Operations

### Creating New Theme Variants
1. Copy base theme file
2. Modify color values following hex format
3. Update `package.json` contributes.themes array
4. Test with demo files

### Adding Demo Files
- Place in `demo/` directory
- Include variety of language constructs
- Test syntax highlighting thoroughly
- Follow existing demo file patterns

## Development Workflow

### Before Making Changes
1. Check current Node version matches `.nvmrc`
2. Ensure all dependencies installed
3. Run linting to check code quality

### During Development
1. Use VS Code's Extension Development Host for testing
2. Test theme with multiple demo files
3. Verify color contrast and accessibility
4. Check theme in different VS Code settings

### Before Committing
1. Run `npx eslint .` - must pass without errors
2. Run `npx prettier --check .` - must pass
3. Package extension: `npx vsce package`
4. Test packaged extension installation
5. Verify all theme colors render correctly

## Repository State Notes

**Current Issue**: The source files (package.json, themes/) exist only in the compiled VSIX file. For proper development:

1. Extract source files from VSIX or rebuild from original source
2. Ensure package.json exists in root directory
3. Verify themes/ directory exists with theme JSON files

## VS Code Extension Specific Guidelines

### Extension Manifest (package.json)
- Maintain version consistency
- Update changelog for each version
- Ensure proper categorization ("Themes")
- Include appropriate keywords for discovery

### Theme JSON Structure
- Follow VS Code color theme schema
- Use meaningful color names and descriptions
- Support both syntax and UI theming
- Maintain consistency across all token types

### Publishing
```bash
# Login to VS Code Marketplace (once)
npx vsce login <publisher>

# Publish new version
npx vsce publish [major|minor|patch]
```

## Dependencies

### Production
- None (theme extensions are pure JSON/configuration)

### Development
- `@babel/core`: ^7.22.5
- `@babel/eslint-parser`: ^7.22.5
- `@upstatement/eslint-config`: ^2.0.0
- `@upstatement/prettier-config`: ^1.1.0
- `@vscode/vsce`: ^3.6.0
- `eslint`: ^8.43.0
- `eslint-config-prettier`: ^8.8.0
- `prettier`: ^2.8.8

---

*This file serves as a comprehensive guide for AI agents working on the Halcyon VS Code Theme project. Follow these guidelines to maintain code quality and consistency.*