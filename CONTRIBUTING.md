# Contributing to SwellOS

## Getting started

1. Clone the meta-repo with submodules:
   ```bash
   git clone --recurse-submodules https://github.com/SwellOS/swellos.git
   ```

2. Each component is in its own repo. See its CONTRIBUTING.md for specifics.

## Guidelines

- Keep it simple. No unnecessary dependencies.
- Test your changes. Every package build should be reproducible.
- Document your config choices in the kernel config.
- Write build scripts that work on a clean system.

## Submitting changes

1. Fork the relevant repo
2. Create a feature branch
3. Commit with a clear message
4. Open a pull request
