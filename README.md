# Pre-commit Hooks Setup
This repository contains the templates and instructions to setup pre-commit hooks to prevent secrets committed to GitHub.  It uses the [Gitleaks](https://github.com/zricethezav/gitleaks) scanner in combination with a custom config to scan a wide range of secret types.  

## Instructions

1. Run the following commands in terminal 
```bash
brew install pre-commit
brew install golang
```

2. Copy the *.pre-commit-config.yaml* and *.gitleaks.toml* from this repo to working repository
```
repos:
- repo: local
  hooks:
  - id: gitleaks
    name: Gitleaks
    entry: zricethezav/gitleaks:v7.5.0
    args:
    - --config-path
    - .gitleaks.toml
    - --verbose
```
 


3. Run the following command to install the pre-commit config in the repository
```bash
pre-commit install
```

4. Gitleaks will now run before any file is committed 