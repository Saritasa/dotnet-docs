# Scripts Structure

## Basic Structure

- 📁 scripts
    - 📁 modules
    - 📄 BuildTasks.ps1
    - 📄 PublishTasks.ps1
    - 📄 Saritasa.PsakeExtensions.ps1
    - 📄 Saritasa.PsakeTasks.ps1
- 📄 Config.Development.ps1
- 📄 Config.Production.ps1
- 📄 Config.Staging.ps1
- 📄 Config.ps1
- 📄 psakefile.ps1

## Configuration Files

Files in Git:
Config.Development.ps1
Config.Production.ps1
Config.Staging.ps1

They contain non-secret settings for different environments.

Ignored files:
Config.ps1

It contains settings for local development. It can be copied from Config.Development.ps1.

- Config.Development.ps1 contains values for dev server.
- Config.ps1 contains values for local development.
