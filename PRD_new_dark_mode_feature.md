# Product Requirements Document: Dark Mode

## Summary

Add a user-controlled light/dark theme toggle to the Memory Game. The theme must remain consistent across the game, including its controls, cards, best scores, and completion dialog, and the layout must remain usable on desktop and mobile screens.

## Goals

- Let players switch between light and dark themes at any time, including during a game.
- Remember the player's selected theme across reloads in the same browser.
- Keep the existing light theme as the default for first-time players.
- Maintain readable contrast, keyboard access, and responsive layouts in both themes.

## Out of scope

- Changing game rules, scoring, grid sizes, or saved game scores.
- Adding a framework, external dependency, or system-preference auto-switching.

## User experience and behavior

1. Show a clearly labeled theme toggle in the game header.
2. Activating the toggle switches between light and dark themes without restarting or otherwise changing the current game.
3. The control communicates the available action (switch to dark or light mode) and exposes the current state to assistive technology.
4. Apply the selected theme to the page background, text, controls/statistics panel, card faces, best scores, and win dialog.
5. Use light theme when no valid saved preference exists. Save a new selection so it is restored on the next visit.

## Responsive and accessibility requirements

- The theme control remains visible and operable at narrow viewport widths without causing horizontal overflow.
- The control is keyboard operable and has a descriptive accessible name and pressed state.
- Text, buttons, and card faces remain distinguishable in both themes; preserve visible keyboard focus.
- Theme switching must not interfere with card interactions, timer, moves, scores, or grid selection.

## Acceptance criteria

- A first-time visit uses the existing light appearance.
- Toggling changes the page and all game surfaces to dark; toggling again restores light.
- The chosen theme remains selected after a page reload.
- The toggle's accessible label and pressed state reflect the current theme.
- Switching themes during a game leaves the board, moves, timer, and grid size unchanged.
- The page remains responsive and usable at mobile and desktop widths in either theme.
- Existing game functionality and score persistence continue to work.

## Implementation notes

- Implement with CSS custom properties and a root theme attribute in `memory-game.html`.
- Persist the theme separately from the existing best-score data in local storage.
- Update the project README feature list and usage guidance.
- Use a restrained, professional visual style with neutral surfaces, clear typography, and abstract card symbols that work in both themes.
