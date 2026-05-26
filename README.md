# Actions

A centralized repository for reusable GitHub Actions workflows.

## Available Actions

### [setup-java-maven](./actions/setup-java-maven/)

Sets up a Java environment with Maven for your GitHub Actions workflows.

- **What it does:** Installs Java and Maven
- **Use case:** Building and testing Java/Maven projects

### [setup-node-npm](./actions/setup-node-npm/)

Sets up a Node.js environment with npm dependencies for your GitHub Actions workflows.

- **What it does:** Installs Node.js and runs `npm install`
- **Default Node version:** 26
- **Use case:** Building and testing Node.js/npm projects

## Usage

To use any of these actions in your workflow, reference them in your GitHub Actions workflow file:

```yaml
- uses: your-username/actions/setup-node-npm@main
```

For more details and available inputs for each action, see the README in the respective action folder.

## Contributing

Feel free to add more actions to this repository. Each action should have:

- An `action.yml` file defining the action
- A `README.md` with usage instructions and documentation
