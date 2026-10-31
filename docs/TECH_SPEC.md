# Technical Specification — NeuroShell

## Overview

macOS SwiftUI terminal assistant that structures command work into guided steps, session context recovery, and focus-oriented workflow pacing.

## Problem statement

Traditional terminal workflows can produce high cognitive load during multi-step troubleshooting, especially when operators lose session context between interruptions.

## Solution summary

A native macOS application that decomposes command tasks, surfaces recovery affordances, and provides optional pacing prompts without replacing the underlying shell.

## Architecture

```mermaid
flowchart LR
  User["Developer"] --> UI["SwiftUI App"]
  UI --> Assist["Task Guidance Layer"]
  Assist --> Context["Session Context + Recovery"]
  Assist --> Wellness["Focus/Break Prompts"]
```

### Components

| Component | Responsibility |
|-----------|----------------|
| `NeuroShell/` | Application sources and views |
| `NeuroShell.xcodeproj` | Xcode project and build settings |
| `PROJECT_OVERVIEW.md` | Extended architecture and feature notes |

## Tech stack

| Layer | Technology |
|-------|------------|
| Platform | macOS 14+ |
| Language | Swift 5 |
| UI | SwiftUI |
| Tooling | Full Xcode 16+ |

## Interfaces

### APIs / entry points

- Desktop application launched from Xcode or distributed `.app` binary
- Keyboard shortcuts documented in README

### Configuration

- Xcode scheme and project settings in `NeuroShell.xcodeproj`

## Data and persistence

- Session context stored in application state; see `PROJECT_OVERVIEW.md` for persistence details.

## Deployment

- **Target:** macOS desktop
- **Build:** `xcodebuild -scheme NeuroShell -configuration Debug build` or Xcode ⌘R
- **Run:** Open `NeuroShell.xcodeproj` in Xcode
- **Health:** Local manual validation; no remote health endpoint

## Testing strategy

| Layer | Command | Coverage |
|-------|---------|----------|
| Build | Xcode build / `xcodebuild` | Compile-time validation |
| Manual | In-app flows | Task guidance, recovery, shortcuts |

## Security and reliability notes

- Runs locally on operator workstation; no network dependency for core guidance flows.
- Builds do not stage or commit source files. The former automatic Git snapshot build phase was removed.

## Evidence map (reviewer paths)

| Concern | Path |
|---------|------|
| Application sources | `NeuroShell/` |
| Project configuration | `NeuroShell.xcodeproj` |
| Extended documentation | `PROJECT_OVERVIEW.md` |

## Architecture decisions

Record significant decisions in `docs/adr/`. Start with `docs/adr/0001-record-architecture-decisions.md`.

---

**Maintained by:** [Dark Heart Labs](https://darkheartlabs.technology)  
**Author:** Jennifer ([@jv-darkheartlabs](https://github.com/jv-darkheartlabs))  
**Site:** https://darkheartlabs.technology

## Verified source and release boundaries

Current suggestion and task-guidance logic uses deterministic local rules/templates. No hosted language-model or TARS integration was found in the inspected Swift source. App Sandbox remains enabled; unrestricted command execution and filesystem access are not established by compilation.

The existing v2.0 release archive was inspected without launching it: macOS14 minimum, Intel x86_64 only, unsigned. Repaired workflows target universal arm64/x86_64 builds, without signing/notarization. No replacement release is created merely by pushing source repairs.
