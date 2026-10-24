# Copilot instructions

## Project structure and architecture

This project is a self-contained, client-side space quiz in `index.html`. The page markup, theme styling, question data, and application logic live together; there is no separate build or application layer.

The quiz flow is driven by the `questions` array and the `current`, `score`, and `answered` state variables. `renderQuestion()` updates the active prompt and progress, `chooseAnswer()` locks the answer and displays scoring feedback, and `showResults()` replaces the quiz view with the summary. The restart handler resets state and renders the first question.

## Build, test, and lint

There are no configured build, test, or lint commands in this project. To run the app, open `index.html` in a browser. Verify quiz changes in the browser by checking answer selection and feedback, score and progress updates, advancing through the final question, results, and restart. The interface uses native buttons and live regions; also check keyboard access and both color schemes when changing UI behavior or styles.

## Project-specific conventions

- Keep user-facing quiz text in Spanish. Each question is an object with `question`, `answers`, `correct`, and `fact`; `correct` is a zero-based index into `answers`.
- Keep the page self-contained unless the project is deliberately extended with a build setup. The current script renders answer buttons from data and updates the DOM directly.
- Use the existing CSS custom properties for surfaces, text, accents, feedback, and shadows. Define theme variants in the `prefers-color-scheme: dark` block so additions work in both light and dark themes.
- Preserve accessible interaction patterns: use native buttons, visible keyboard focus, `aria-live` for changing question/feedback/results, and update the progress bar's `aria-valuenow` with its visual progress.
- Respect `prefers-reduced-motion` for any new animations or transitions.
