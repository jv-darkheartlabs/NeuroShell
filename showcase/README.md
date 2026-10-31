# NeuroShell illustrated showcase

Open `index.html` in a browser or serve this directory with a local static server. No build step, dependencies, account, network API or native application is required. The only external navigation is to Dark Heart Labs and the public NeuroShell repository/build evidence.

This is an illustrated browser presentation, not a native screenshot, native runtime test, real terminal or full port. It uses fictional sample output and page-memory-only interactions. No shell commands execute, no files are read, and no data is persisted.

## Source correspondence

- Three command suggestions use exact commands/descriptions from `NeuroShell/Services/CommandSuggestionEngine.swift`: file listing, Git changes and home-directory navigation. The browser limits selection to those examples rather than reproducing the complete engine.
- The four “new project” steps, commands and estimates mirror `createProjectSetupChunks()` in that service. Browser completion is independent from native task sessions.
- The context card illustrates the fields in `NeuroShell/Models/ContextMemory.swift`; its contents are fictional.
- Box breathing mirrors `NeuroShell/Views/BreathingExerciseView.swift`: four phases of four seconds, four cycles. Browser tab changes, hidden-page transitions and Stop cancel the timer. Reduced-motion preferences disable circle transition animation.
- Build evidence links to verified run 41215272149. Compilation is distinguished from native runtime and distribution readiness.

## Security and accessibility design

No user text is inserted as HTML, there is no executable command input, and all sample data is bundled locally. Native terminal privileges, credentials, private paths and account data are absent. Navigation uses semantic buttons with pressed state and explicit controlled sections. Forms use labels, checkboxes and a labeled progress element. Focus remains visible; controls work by keyboard; layout adapts to narrow screens; no animation starts automatically.

## Suggested captures

1. Hero and terminal suggestion — broad project introduction.
2. Task Chunker with two checked steps — task structure and progress.
3. Breathing Space at rest — optional pause feature.

Keep the “Illustrated browser preview” notice visible in exported promotional images or add an equivalent caption. Do not label these captures native screenshots. Native launch, command execution, sandbox behavior and audio must be verified separately before recording a native walkthrough.
