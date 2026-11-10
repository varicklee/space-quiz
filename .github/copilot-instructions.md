# Copilot instructions

## Project shape

- `index.html` is the complete application: markup, styles, quiz data, and browser-side behavior are all inline in one file.
- The page renders one question at a time from the `questions` array. Each entry contains question text, four choices, a zero-based correct `answer` index, and an explanatory `fact`.
- Quiz state (`current`, `score`, and `answered`) drives answer feedback, progress, and the final results screen. Keep score and progress updates consistent when changing navigation or restart behavior.
- Theme colors are CSS custom properties. The initial theme follows the system preference unless the user has saved a choice in local storage; the theme button switches between explicit light and dark modes.

## Commands and validation

- There is no build system, package manifest, test runner, or linter. No build, test, or lint commands are defined.
- Open `index.html` directly in a browser to run the application; it does not require a server or external dependencies.
- For behavior changes, check both correct and incorrect answers, score and progress, completion and restart, and theme switching in the browser.

## Project-specific conventions

- Keep the quiz self-contained in `index.html`; do not introduce a framework, package manager, external assets, or runtime dependency for ordinary UI changes.
- Add or edit question content in the `questions` array. `answer` is a zero-based choice index; update it if choice order changes.
- Build answer buttons from the question data and use text content for dynamic question and answer copy.
- Preserve accessible native buttons, visible focus indicators, progress-bar values, live feedback announcements, and the reduced-motion preference when changing the interface.
- Keep both system-based theme selection and the manual toggle working. Browser storage may be unavailable, so the page must still work for the current visit.
