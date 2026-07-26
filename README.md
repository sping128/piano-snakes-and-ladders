# Piano Snakes & Ladders

A browser-based Snakes & Ladders game with piano and music-theory questions, built for group lessons at [Vorakarn's Piano Studio](https://www.facebook.com/VorakarnsPianoStudio).

**Play it here: https://sping128.github.io/piano-snakes-and-ladders/**

## How it works

Up to 15 students race across a 25-square board on one shared screen.
Students roll a real physical die and enter the result on screen, so the game stays a classroom activity rather than a screen activity.

- **Ladder** - answer the music question correctly to climb to the top of the ladder.
Miss it and you stay where you are.
- **Snake** - answer correctly to stay safe on your square.
Miss it and you slide down to the tail.
- **Square 25** - reaching the last square does not win the game on its own.
One final question decides it: answer correctly and you win, miss it and you go back to the square you came from and can try again on your next turn.
- Overshooting the end still lands you on 25, which keeps rounds short.

## Features

- Roster setup for 2 to 15 players, with a "fill demo names" shortcut for testing
- Configurable number of ladders (0 to 6) and snakes (0 to 6), randomly placed on each new game
- Board preview with a regenerate button, so you can reroll the layout before starting
- A bank of 30 music-theory questions in Thai, covering dynamics markings, solfège and letter note names, and staff reading, with SVG and typographic visuals rendered inline
- Full question preview on the setup screen, useful for checking coverage before a lesson
- Animated token movement, turn order panel, and move log
- Sound effects generated with the Web Audio API, with a mute toggle

## Running locally

The whole game is a single self-contained `index.html` file with no build step and no dependencies.
Open it directly in a browser:

```bash
open index.html
```

## Deployment

The site is served by GitHub Pages from the `main` branch root.
Any push to `main` redeploys it within about a minute.

## Customising the questions

Questions live in the `QUESTION_BANK` array in `index.html`.
Each entry looks like this:

```js
{
  q: "G คือเสียงโน้ตอะไร",
  options: ["Sol", "La", "Ti", "Re"],
  correct: 0
}
```

`correct` is the zero-based index of the right option.
An optional `visual` field takes an HTML or SVG string that is rendered above the answer choices, which is how the staff-notation and dynamics questions are drawn.
