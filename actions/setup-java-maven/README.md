# Setup Java & Maven

This action sets up Temurin JDK and enables Maven caching for GitHub Actions workflows.

## What this action does

1. Installs a Temurin JDK using [actions/setup-java@v5.2.0](https://github.com/actions/setup-java)
2. Configures Maven cache support

## Inputs

### `java-version`

**Optional** — The version of Java to set up.

- **Default:** `21`

## Usage

### Basic usage (with default Java version 21)

```yaml
- uses: setup-java-maven@v1
```

### Specify a different Java version

```yaml
- uses: setup-java-maven@v1
  with:
    java-version: "17"
```

## Example workflow

```yaml
name: Java CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: setup-java-maven@v1
        with:
          java-version: "21"
      - run: mvn -B package --file pom.xml
```

## Notes

- The action uses a composite run type and runs entirely in the workflow context.
- Maven caching is enabled through `actions/setup-java` to speed up dependency downloads.
