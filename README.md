# Card Target Sprint

A solo, timed card arithmetic game. You're dealt 7 or 8 playing cards and a random target number. Combine cards with + − × ÷ to hit the target as fast as you can.

Inspired by [beatwu.fun](https://beatwu.fun/), minus the head-to-head: you only race your own best time.

## How to play

1. Tap a card.
2. Tap an operator chip (+ − × ÷).
3. Tap another card. The two cards merge into one card holding the result.

Repeat until a card equals the target. Card values: A = 1, 2–10 at face value, J = 11, Q = 12, K = 13. Division only works when the answer is a whole number.

### Settings

- **Cards:** 7 or 8.
- **Target:** 100–999 or 1000–9999.
- **Use:** *Any cards* (win as soon as you make the target) or *All cards* (every card must be used, as in the original).

### Keyboard

| Key | Action |
| --- | --- |
| `1`–`8` | Select a card |
| `+` `-` `*` (or `x`) `/` | Pick an operator |
| `Backspace` | Undo |
| `Esc` | Clear the selection |
| `R` | Reset the deal |
| `S` | Show the solution (press twice) |
| `N` | New deal |

## Features

- **Every deal is solvable.** Before a deal is shown, a solver searches every possible sequence of moves and re-deals if none reaches the target.
- **Timer.** It starts when the cards are dealt and stops when you hit the target. Best and recent times are kept separately for each combination of settings.
- **Optimal solution.** Revealing it ends the timed run. "Optimal" means the fewest moves (in *Any cards* mode), then the smallest possible largest intermediate number, so the arithmetic stays easy. If the search hits its time budget before proving that, the game labels the answer "best found".

## Running it

It's one static file with no build step and no dependencies. Open `index.html` in a browser, or serve the folder with any static host (GitHub Pages works: Settings → Pages → deploy from the `main` branch).

The solver runs in a Web Worker so the page stays responsive. Times are stored in your browser's `localStorage` and are never sent anywhere. Fonts load from Google Fonts.
