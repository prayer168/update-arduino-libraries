# Update Arduino and Libraries

Codex Skill for refreshing an existing Windows Arduino installation bundle, including official installers, Arduino CLI, ESP32 Core, libraries, scripts, manifests, checksums, and user documentation.

## Version

Current version: **1.0.0** (`VERSION`; Git tag `v1.0.0`).

## Use

Invoke the skill by asking Codex: **“Update Arduino and Libraries”** or **「更新 Arduino 及程式庫」**. Provide a folder path or cloud-drive location when you want to target a specific bundle. Otherwise, the skill searches the current project and, when needed on Windows, mounted user data drives for a uniquely identifiable `Arduino安裝` bundle.

The skill inspects the existing manifest, checksum list, documentation, scripts, and package files before updating. It checks official vendor sources, updates missing or outdated materials, aligns version and checksum metadata, and reports validation results and any remaining manual steps.

## Safety boundaries

- Prepares the installation bundle; it does not launch installers, elevate privileges, install software, or change system settings.
- Uses official vendor and maintainer sources and records source URLs.
- Preserves unrelated files and avoids guessing board-specific settings such as FQBN, GPIO, USB mode, or COM port.
- Marks hardware and target-computer checks as pending unless they were actually performed.

## Files

- `SKILL.md` — skill instructions and operating boundaries.
- `agents/openai.yaml` — Codex display name and invocation prompt.
- `VERSION` — current semantic version.

## Versioning

Versions use Semantic Versioning. The `VERSION` file, `SKILL.md` metadata, and Git release tag should agree. Use patch versions for compatible instruction fixes, minor versions for backward-compatible workflow additions, and major versions for incompatible behavior or boundary changes.
