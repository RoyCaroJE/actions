# Setup Node & NPM installation

This action sets up a Node.js environment and installs npm dependencies.

## What this action does

1. Sets up Node.js using [actions/setup-node@v6.4.0](https://github.com/actions/setup-node)
2. Runs `npm install` to install project dependencies

## Inputs

### `node-version`

**Optional** — The version of Node.js to set up.

- **Default:** `26`

## Usage

### Basic usage (with default Node.js version 26)

```yaml
- uses: setup-node-npm@v1
```

### Specify a different Node.js version

```yaml
- uses: setup-node-npm@v1
  with:
    node-version: "20"
```

## Example workflow

```yaml
name: Build and Test

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: setup-node-npm@v1
        with:
          node-version: "18"
      # Your build and test commands here
      - run: npm run build
      - run: npm test
```

## Notes

- The action uses a composite run type, which means it runs directly without requiring a separate Docker container or Node.js environment.
- Dependencies are automatically installed after Node.js is set up.
